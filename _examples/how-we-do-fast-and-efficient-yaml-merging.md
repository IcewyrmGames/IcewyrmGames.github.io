---
layout: article
title: How We Do Fast And Efficient YAML Merging
author: Jonas Drewsen
source: http://blogs.unity3d.com/2015/06/02/how-we-do-fast-and-efficient-yaml-merging/
category: Programming
---

# Introduction
In Unity 5.0, we shipped the scene and prefab merge tool, and It’s been positively received by the Unity Community. However, we’ve since realized that it doesn’t handle large scenes optimally, especially with respect to memory usage and the time taken to execute processes.

We’ve now worked on a number of changes to improve this, and they will go into future Unity release. As a result, the system is both more memory efficient and faster than other popular merge tools. Here’s a look at what we did.

# How it works 10 mile overview
This is roughly how the tool worked to begin with: Three files are read from disk (e.g. mine, incoming and base scene/prefab files) into an in-memory yaml structure exactly like the one we have inside Unity itself.

Now a diff is made between mine and base, and that results in a form of diff-tree describing which operation to perform on the _base_ version yaml to get to the _mine_ version yaml (_mine/base diff_). The same diff-tree is created for _incoming_ and _base_ (_incoming/base diff_).

![ ][Diff Tree]

The two diff-trees are now merged into one unified diff-tree (_merged diff_). This is the first point where conflicts can happen and the conflicts can be resolved by the user. Since the merged diff consists mostly of content from the two source diffs it simply references data inside the source diffs and we make sure their lifetimes exceed that of the merged diff-tree. After this merge is done the source diffs are considered invalid because they may have been rearranged during the merge.

Having the merged diff we can apply that to the _base_ yaml in order to get the end result. This is done by traversing the diff tree and perform its operations on the _base_ yaml. Operations that add new content simply adds a reference to content in the diff and we make sure the diff lifetime exceeds that of the end result. This final step can also result in conflicts because we are doing an additional semantic pass at this point fixing things like circular references created etc.

![ ][Base To Merged]

At this point we can output the result if there are no conflicts. In case there actually are conflicts we need to do some extra work. Since we have no specialized GUI to present the conflicts we prepare three files (mine’, incoming’ and base’) that can be fed into a fallback merge tool e.g. araxis merge. The purpose of these files is to nurse the fallback tool so that it presents as few conflicts as possible. The base’ is simply the result we just created but using values from _base_ where there are conflicts. The mine’ and incoming’ are constructed by doing exactly the same as for getting base’ ie. reading three files, diffing, merging and applying. But instead of using base values we use _mine_ or _incoming_ values respectfully.

# Let’s optimize!
To get things going a reasonably large scene (~3 MB) with conflicts was selected. Three other popular merge tools were picked for comparison of speed and memory usage: Diffmerge, k3diff and p4merge. These merge tools can’t do any semantic merging but were, nonetheless, suitable for our purposes (_measurements were performed on a debug build of our merge tool_).

From the chart below, we can see that worst tool with regard to memory is _diffmerge_ which uses just as much memory as our baseline (the merge tool) with the best tool using 1/8th of the baseline. With regard to time spent, all the other tools perform way better than the baseline with the fastest being _diffmerge_ which uses only 3% of the time of the baseline. The optimization target was __to use same amount of time as the fastest tool__ (diffmerge) and __same memory as the tool that used the least memory__ (k3diff). Ready.. set.. go!

![ ][Optimization 1]

The first glaring issue is that three merges are being done from scratch in the situation where a conflict is present. Much of the setup done by the first can be reused by the next two: Reading and parsing the files, creating mine/base and incoming/base diff. Merging cannot be shared since that is where the outcome differs for the three.

## Immutable diffs
Unfortunately, as stated above, the source diffs are rendered invalid when doing a merge and, as such, cannot be reused. This was fixed by making the diff structure immutable. Since c++ doesn’t have built in support for immutability (like e.g. [dlang](http://dlang.org/const3.html)) only logical immutability is used and this works just fine. With immutability comes the issue of having to copy content from source diffs when creating the merged diff instead of simply referencing. However, the fact that the source diffs could now be reused for the two other merges more than doubled the speed of the process, and generated a slight decrease in memory usage.

## Float/int removal
Now that merge time had been improved, we moved our attention to memory consumption. The YAML structure replicated the one used inside Unity itself, and it contains a distinction between int,float and string values for leaf nodes in the yaml tree. The is not stored as a union but a int,float and string field. Since the smart merge works on strings most of the time, it makes no sense to keep the former two around. Removing float and int from the leaf struct cut memory usage by 40%.

![ ][Optimization 2]

## Threading diffs
Back to improving merge time again. When you have immutability present you have to consider threading since they are a perfect match. By making sure that source structures are also immutable when creating the source diffs it is possible to reuse the source structure for the base and put the creation of the mine/base and incoming/base diffs in two threads.

## Threading reads
An extra threading improvement step was to first read and parse the base file and then at that point make a thread for each of the two diffs. Those threads could then share the base file structure but read the mine and incoming file in separate threads.

## YAMLScalar* table
Noticing the impact on memory that removing int and float fields had, it seemed to make sense to look in that direction for more memory savings. At that time, realizing that many of the leaf node strings and keys strings in the scene/prefab files are actually the same gave us an idea. It looked very much like a trick that compiler makers have been using forever would fit here: string tables. The idea is to simply keep an array of all strings that are present and have each usage point to that string, thereby removing duplicates. If there are a number of duplicates this can save a lot of space. In our case it wasn’t really a string table but a YAMLScalar table, however the idea is the same.

## Pooling
The next idea was to pool yaml nodes instead of simply using new/delete all the time. It speeded up the process, but unfortunately also consumed a bit more memory.

## Cloning base
When applying the merged diff on the base yaml the base is modified as the end result. Since we needed to do three merges, that meant reading the base file three times so that each could be modified. Instead of re-reading the base file support for cloning the base in-memory structure was implemented. This speeded up the process significantly.

## Subtree hashing
Usually most of the objects in a prefab/scene are unaltered. In order to leverage this subtree, hashing was implemented. During parsing of the yaml files a hash of each subtree is calculated, and that can be used to quickly check if a common subtree has changed when comparing yaml documents.

## Map -> vector map
Again, in the name of making the yaml structure a bit more lightweight all std::maps in a yaml node (i.e. maps from yaml node keys to it values) were replaced with std::vectors. This makes perfect sense in that there are usually few fields in a GameObject, or any other class represented in the yaml files, which render the std::map too heavy to use. This also cut down on the time, but, to my surprise, it had an even more positive effect on memory usage.

Thanks to these changes, the merge tool delivered comparable performance to the three tools we tested against. Indeed, once we’d made a release build it outperformed them on both memory and time. Note that the merge tool is performing 3x merges where the other tools are doing 1. It would be very nice to make an in editor GUI for this so that we would only have to do a single merge. Furthermore, a GUI would make it possible to show conflicts that the fallback merge tools cannot such as circular references etc.

# Next steps
There is still room for further optimizations, but at this point it is probably not worth working on. Please hit us with any feedback about unhandled conflict cases to the “smart” of the tool. We will then integrate that feedback into the tool as a longer running maintenance task.

As mentioned above, it would _really_ make sense to put a GUI on top of the tool.

Doing all this optimization and refactoring would not have been possible, or would at least have been very troublesome, without an existing test suite to ensure that no regressions were happening after each optimization step.
Thanks for reading!

[Diff Tree]: ./diff-tree.png
[Base To Merged]: ./base-to-merged.png
[Optimization 1]: ./optimization1.png
[Optimization 2]: ./optimization2.png