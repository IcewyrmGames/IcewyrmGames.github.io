---
layout: article
title: "Scroll Back: The Theory and Practice of Cameras In Side Scrollers"
author: Itay Keren
source: http://gamasutra.com/blogs/ItayKeren/20150511/243083/Scroll_Back_The_Theory_and_Practice_of_Cameras_in_SideScrollers.php
category: User Interface
priority: 1
---

# Overview
Working on my game Mushroom 11, I was faced with many different design and technology challenges. I wasn’t expecting to find references to issues like dynamically changing shapes or vertex animation, but I was quite surprised that camera work, a subject with more than 30 years of history in games, was hardly discussed.

I decided to start a journey through the history of 2D gaming, documenting their challenges, approaches and how the evolution of their solutions. Also, since there’s a lack of proper terminology for the many different solutions, I started gathering and categorizing them into groups, providing my own glossary, if only for my personal reference.

# Scrolling
Scrolling or Panning refers to any attempt to display a scene that is larger than what fits in a single screen. There are many potential challenges with scrolling, like choosing what the player needs to see, what we as designers would like the player to focus on, and how to do it in a way that’s fluid and comfortable for the player.

While I’m going to focus on 2D camera systems, many of these general concepts apply to 3D as well.

# Neural Background
Before we examine these games, let’s touch on the neural background of scrolling so we can understand our vision and perception better. By doing this we can understand how scrolling can go wrong.

![ ][Eye]

The fovea-centralis is the receptor inside our eyeball responsible for sharp and detailed central vision. The second and third receptor belts, the parafovea and perifovea, excel in reducing images and motions to patterns allowing changes to be quickly recognized, including recognizing familiar alarming shapes and changes in motion speed or direction.

This visual input uses the fast track straight to the Amygdala, allowing an alert response while the Visual Cortex is deciphering the input. Training your brain, especially by tying the shift in peripheral vision to the controls, proves useful over time.

![ ][Ear]

The Vestibular system located in our inner ear, is responsible for maintaining balance and providing spatial orientation. The signals it sends allow the body to maintain its balance, while keeping visual focus on specific details.

When some people, like me, try to read in a car, the acceleration combined with the lack of visual corresponding feedback, can lead to nausea and vertigo.

The opposite is also true: as the Perifovea quickly picks up a change in the background, it expects a corresponding feedback from the Vestibular system. When there is none (as you’re sitting firmly in front of your computer), the result can be the same.

So, conflicting sensory signals (Visual vs. Vestibular) may lead to discomfort and nausea, and though it’s worse in 3D (especially VR), it is still very much in effect in 2D games.

# Attention, Interaction and Comfort
To help understanding the problems in scrolling, I’ve categorized its elements into three major challenges:

![ ][Elements]

- __Attention:__ Use the camera to provide sufficient game info and feedback (what the player needs to see)
- __Interaction:__ Provide clear player control on what’s displayed, make background changes predictable and tightly bound to controls (what the player wants to see)
- __Comfort:__ Ease and contextualize background changes (how to reconcile those needs smoothly and comfortably)

# Scrolling Nostalgia

![ ][Nostalgia]

So let’s start our journey back to the 1980s, when designers were inventing completely new design schemes while overcoming technical limitations that are hard to imagine 30 years later.

You’ll also notice references to several leading indie games, mostly from the last 10 years or so, which tend to always to display the innovation, attention and care that can be expected from independent artists, and camera work is certainly no different.

# Follow The Action

## Keep attention on your control subject
Starting with the basics. Generally speaking, your player has authority over the main character. This dictates that the attention should be directed at that character by closely following it with the camera.

In the early 80s, scrolling was a difficult task, and the developer had to face limitations such as CPU, memory capacity and segmentation. Even with those challenges, some great side-scrollers were released, gracefully overcoming these limitations. However, in many cases the motion was understandably simplistic or low-resolution.

It’s remarkable that back in 1980, a game like Rally-X was able to overcome technology limitations and present a true dual axis camera. It uses the default position-locking mechanism, keeping the car in focus at all times and the camera motion completely predictable.

![ ][Rally-X]
<cite>Rally-X © 1980 Namco</cite>

- __position-locking__ - camera is locked to the player’s position

_Note:_ the terms presented throughout this talk were created for my own reference and work, but I’d be delighted if others find them useful, make improvements, and provide me with feedback.

Kung-Fu Master is another good example for position-locking, designed by Takashi Nishiyama, the designer who made Moon Patrol, and would later make Street Fighter.

This game uses another basic mechanism which I call edge-snapping, which simply snaps the camera to the edge of the level, allowing the character to move away from its anchor point.

![ ][Kung-Fu Master]
<cite>Kung-Fu Master © 1984 Irem</cite>

- __position-locking__
- __edge-snapping__ - set a hard edge for camera positioning
  - edge-snapping is too common to mention per each game, and will be ignored from now on

Position-locking is basic but still very useful. For a crafting adventure game like Terraria, with a small character relative to the screen with pretty small jumps, it works very well, providing plenty of view space in all directions.

![ ][Terraria]
<cite>Terraria © 2011 Re-Logic</cite>

- __position-locking__

# Curb Camera Motion

## Avoid unnecessary or unpredictable bumps
How do we avoid moving the camera if it’s not absolutely necessary? 30 years ago, scrolling had several issues: it was CPU intensive, requiring a major part of the screen to be refreshed. And even when successful, the large pixels of the time made scrolling choppy. Best approach was to keep scrolling to the necessary minimum. One way is to allow the character to move within a certain window, and only scroll when it pushes against the edges of that window.

Jump Bug is considered by many as the first platformer, although technically the player is automatically jumping repeatedly, and control is limited to jump height as well as left/right motion. Most of the game as an automatically moving camera, forcing players to keep up while avoiding obstacles, like many other scrolling games of the time.

![ ][Jump Bug]
<cite>Jump Bug © 1981 Hoei/Coreland (Alpha Denshi)</cite>

- __camera-window__ - push camera position as the player hits the window edge

But the camera-window technique used in the last level, solved a problem that many designers didn’t even know existed, and set the standard for thousands of platformers to follow. The camera-window technique also introduced some issues, like having very little view of what’s coming forward or up ahead as the player jumps towards the exit.

One of my favorites, Rastan Saga, introduced movement in 2 axes with various paths to take. It was also one of the first games to really evolve the relationship between the camera and the mechanics. This camera-window is as high as a standard jump, so jumps don’t cause vertical camera motion unless Rastan has already moved within the window. This eliminates the need in rapid camera jerks.

A major flaw with this method is that enemies coming from above are less noticeable, especially if Rastan has already moved vertically within the window. Also moving left, which happens a lot in castles, is really uncomfortable as it leaves a very narrow lookahead margin.

![ ][Rastan Saga]
<cite>Rastan Saga © 1987 Taito</cite>

- __camera-window__

The camera-window technique is still used in modern games. See how in Fez, the horizontal camera-window is maintained through dimension shifts, and in fact, the shift axis is chosen to keep the character within the window. The choice of camera-window in Fez is far from default, and represents the ideal camera solution for such unique game mechanics, as we’ll show later. Vertically, the camera maintains a straightforward position-locking, smooth using lerp-smoothing, which we’ll define later.

![ ][Fez]
<cite>Fez © 2012 Polytron Corporation</cite>

- __camera-window__ (horiz.)
  - Also enforced during dimension shifts
- __position-locking__ (vert.)
- lerp-smoothing
- region-based-anchors
- manual-control
  - Right-stick provides extra panning

_Note:_ unbolded terms represent camera techniques that are defined later in the article.

# Snapping

## Fix camera drift within window
We showed the use of camera window to reduce camera movement, but as we’ve seen in Jump Bug and Rastan, it has some flaws as the player drifts away within the window. Here are a few ways we can fix it.

Maybe my favorite classic game, Shinobi, has some very high jumps between multiple platforms. The designers came up with a unique camera system: vertically, due to the many platforms the character jumps between, Shinobi uses a very wide vertical camera window. As always, the window pulls the camera with it immediately. The problem with a wide (or tall) window is that after a small jump, the character could be stuck at the top of the window with very little top-view, as we’ve seen in Rastan Saga. Shinobi simply continuously aligns the camera, slowly, to the Ninja, keeping the focus on the action and in most cases keeping rapid camera motion to the minimum.

![ ][Shinobi]
<cite>Shinobi © 1987 Sega</cite>

- __position-snapping__ (vert.) - constantly reduce window drift by focusing the camera back on the player
- __camera-window__ (vert.)
- __position-locking__ (horiz.)
- static-forward-focus

One of the many features that Super Mario World introduced was platform-snapping. As with any camera-window, the camera would stay stationary until the character hits the edge. But since mario inevitably lands on a platform, as soon as he does, the camera would immediately snap to its position.

![ ][Super Mario World]
<cite>Super Mario World © 1990 Nintendo</cite>

- region-based-anchors
- __platform-snapping__ - camera snaps to the player only as it lands on a platform
  - Where applicable
- __camera-window__ (vert.)
  - Where applicable
- dual-forward-focus
  - Threshold triggered
- manual-control (horiz.)
  - Controller provides extra panning

This is the first mention of the work of Miyamoto and certainly not the last. The awareness and the attention to the smallest details is what really makes a true great designer, and not just clever game mechanics.

You can see the same idea in the original Rayman. The top of the screen serves as the top of the camera-window. Notice how the camera does not move as Rayman jumps, but rather gently snaps when he lands. This is a clever solution since the camera-window is just over the height of Rayman’s jump, showing once again how camera system is an integral part of game design.

![ ][Rayman]
<cite>Rayman © 1995 Ubisoft</cite>

- __platform-snapping__
  - Where applicable
- __camera-window__ (vert.)
  - Where applicable
- region-based-anchors
- dual-forward-focus
  - Where applicable
- lerp-smoothing

This technique is very effective even today, allowing the designers to keep the camera smooth during jumps, and center the camera only when the jump is complete, or if it pushes a camera-window. Note that platform-snapping is naturally only effective when the player can land on platforms. In other cases, like the Jetpack character in Awesomenauts, the player is pre-snapped, i.e. position-locked.

![ ][Awesomenauts]
<cite>Awesomenauts © 2012 Ronimo Games</cite>

- __camera-window__ (vert.)
- __platform-snapping__
  - Jetpack character is always snapped (=vert. position-locking)
- __position-locking__ (horiz.)

# Smoothing

## Avoid sudden camera speed and direction changes
We talked before on the role of our peripheral vision, and its effect on visual comfort. In the olden days, with the large pixels of the time, even simple tweening would look jumpy due to the large pixels.

![ ][80s Pixel]
<cite>80s Pixel (NES: 256x240 resolution)</cite>

![ ][Indie Pixel]
<cite>Indie Pixel (Contains multiple screen pixels)</cite>

So how can we smooth the camera motion, when we are confined by a really strict and crude grid of large pixels? Nowadays, we can design beautiful pixel art, and then move it across the actual pixels that are much finer than the pixel-art. And if you choose to avoid going pixel-perfect, you can even make use of the sub-pixel space as most modern engines offer.

## Smoothing with (Pseudo) Physics

Pseudo-physics can come into play to help smoothing a position-locked camera (and you could argue that any engine physics is in fact pseudo).

Pac-Land is arguably the first modern platformer. It has many of the elements that helped defining this genre, such as jumping on platforms, avoiding enemies and picking up bonuses. With regard to smoothing, its Speed goes from 0 pixels per frame to 1, 2, 3, all the way to the maximum speed, and then damped down to 0. And with the camera being locked on the player’s position, the results are clear and smooth. But Pac-Land doesn’t have to scroll vertically, where the real smoothing challenge lies, with fast acceleration and deceleration when jumping and landing.

![ ][Pac-land]
<cite>Pac-Land © 1984 Namco</cite>

- __position-locking__
- static-forward-focus

## Shigeru Miyamoto
At this point I’d like to give a quick hat tip Shigeru Miyamoto and show some of his early works. His invaluable contribution to the industry, and attention to the smallest details of game design cannot be exaggerated.

In 1984 he started experimenting with scrolling, designing two games that used it in completely different ways. In both these games, the player has very little control of the scrolling, if any. It was more like a room with a shifting background.

![ ][Excitebike]
<cite>Excitebike © 1984 Nintendo</cite>

![ ][Devil World]
<cite>Devil World © 1984 Nintendo</cite>

Excitebike had a modern scrolling action, affected by the speed of the bike. Scrolling was smooth enough, but had no real effect on the game.

Devil World’s gameplay however had everything to do with scrolling. In this Pac-Man clone, you play as a Christian dragon fighting the devil, whose role was limited to changing the scrolling direction, pushing you closer to the edge. It’s also the only Miyamoto game that was denied release in North America due to the use of religious icons, but compared to the quality of his decades of work, it doesn’t seem like a huge loss. However, it is important, and even inspiring at times, to look from time to time at the early and often less successful work of modern day geniuses. Even the greatest artists experiment, and often fail.

Moving forward one year, it’s hard to exaggerate the brilliance of Super Mario Bros. The gameplay itself incorporates a pretty simple left-to-right, horizontal only approach. Also, it does not allow backtracking beyond the edge of the screen, which is a common platformer trait (technically it can be defined as a one-sided camera-window).

![ ][Super Mario Bros]
<cite>Super Mario Bros. © 1985 Nintendo</cite>

- __speedup-push-zone__ - when inside the push-zone, gradually accelerate the camera to catch up with player’s speed
- __camera-window__
  - One-sided
- static-forward-focus

So when Mario goes all the way back, then speeds up to cross the camera-window edge, it would move from 0 to full-speed in one frame, causing a major change in background speed and the inevitable discomfort that follows. The designers solved this by adding a virtual point, around 25% off-center, where the camera speeds up to catch up with Mario, so when he hits the edge, the camera speed would already be caught up.

Metroid was a groundbreaking game that helped coin a genre, combining platforming with exploration. (Its genre-brother Castlevania had a very basic position-locking camera, by the way.)

Metroid used a multi-axis progression, one at a time. It introduced a different way of easing the camera into motion by allowing the character to step out of the window span, while speeding up the camera to catch up. How far across that line the player ends up depends on how fast it hit that line, but the result is a smooth camera behavior.

![ ][Metroid 1]
![ ][Metroid 2]
<cite>Metroid © 1986 Nintendo</cite>

- __camera-window__ (horiz./vert.)
- __speedup-pull-zone__ - pull the camera to catch up with player’s speed after it crosses over window’s edge

With the advancement of technology, with more pixels and robust CPUs. This allowed for more freedom in moving the camera freely, without the low-resolution jitter that characterized the camera motion, especially in slow speed which could lead to one every few frames.

Donkey Kong Country had plenty of innovative camera solutions, and it was among the first to use lerp (Linear Interpolation) smoothing, allowing smooth enough jumps and forward-focus switch (more on that later).

![ ][Donkey Kong Country]
<cite>Donkey Kong Country © 1994 Nintendo (Rare Ltd)</cite>

- __lerp-smoothing__ - continuously reduce the distance between camera and active player using Linear Interpolation
- __position-locking__ (vert.)
- region-based-anchors
- dual-forward-focus

Lerp-smoothing doesn’t sound like a major accomplishment and it’s become a standard tool in reducing jarring camera speeds, particularly jumps.

``` csharp
float lerp (float a, float b, float t) { return a + t * (b - a); }
```

This is probably the most effective and ubiquitous smoothing technique. It works well for for slow or fast moving characters like in Super Meat Boy. However for large characters moving extremely fast, it can easily hit the edges of screen before the camera can catch up, keeping incoming enemies hidden till the last minute.

![ ][Super Meat Boy]
<cite>Super Meat Boy © 2010 Team Meat</cite>

- __lerp-smoothing__
- __position-locking__

Never Alone is a beautiful game that came out in 2014, and has many different elements which we’ll cover later. Its main smoothing technique takes into account existing camera speed, which means that it moves into action slightly slower and can over overrun its target point. The result is smooth, organic though obviously less reactive to rapid player motion.

![ ][Never Alone]
<cite>Never Alone © 2014 Upper One Games</cite>

- __physics-smoothing__ - camera is a physics enabled entity, constantly closing on the focus target
- position-averaging
- cinematic-paths
- region-based-anchors
- cue-focus

In code terms, if Lerp is EaseOut, then physics-smoothing is EaseInOut. Where available, check out the SmoothDamp method for details, or tailor your own implementation that takes into consideration the distance to the target as well as the current velocity.

If you’re simply using pixel-perfect shaders, you’ll see that sometimes your sprites seem to shift a pixel, compared to other sprites or to the background, due to math division inconsistencies.

Hyper Light Drifter uses a clever solution to enable smooth scrolling, even though it has a low-res pixel art. It pre-renders on a game-pixel-perfect canvas, and then shifts the canvas on a screen pixel-perfect to reflect the remainder of the position after the division by game-pixel size. This game also has a bunch of other interesting camera features which we’ll talk about later.

![ ][Hyper Light Drifter]
<cite>Hyper Light Drifter © [Release TBA] Heart Machine</cite>

- __physics-smoothing__
  - Game canvas resolution is 480x270. Camera scrolling uses full resolution
- region-based-anchors
- target-focus
- cue-focus
- gesture-focus

# Framing

## Keep the important details in the frame
auto-scroll is beyond the scope of this talk since, by definition, it provides no player control over the scrolling motion. However it gives us a good reference on where players would ideally like to be positioned, providing a good balance between threats coming ahead, and leaving some room for threats coming from behind.

![ ][Scramble]
<cite>Scramble © 1981 Konami</cite>

- __auto-scroll__ - player only has no control over the scrolling (but has full authority over its placement in the frame)

As we’ve seen in Pac-Land, if you tie the camera to the player and provide directional control, you can focus the camera ahead of the player. This provides plenty of room to look ahead, and still keep track of what’s behind - and also marks as a guideline on where to go, since we strive to aim to the center.

![ ][Pac-land]
<cite>Pac-Land © 1984 Namco</cite>

- __position-locking__
- __static-forward-focus__ - extra view space in the principal progression direction

Going back even further, and way ahead of its time, early 1981 saw the release of Defender, a shoot-em up which inspired an entire new genre. The way it presented a bidirectional forward focus, almost went under the radar. Defender always tries to focus the screen on an imaginary point in front of the spaceship, around 25% screen-width forward. This system works well for a fast paced game, where most enemies come from the front.

![ ][Defender]
<cite>Defender © 1981 Williams Electronics</cite>

- __dual-forward-focus__ - player direction changes switch camera focus to enable wide forward view

Bonanza Bros. is a delightful side-scrolling heist game released for the arcades by Sega in 1990. It has a split screen feature for the unique one-on-one co-op mode where the two brothers work together to complete the heist.

Of course, a clear forward view is essential for a heist scenario so a dual forward view is enabled. However, it takes a few steps for the camera to catch up with the new target point, making this entire motion feel extra smooth while supplying plenty of space. The switch speed is around double of the player’s, which also means that the camera only moves when the player moves. Check out Red in the figure below.

![ ][Bonanza Bros]
<cite>Bonanza Bros. © 1990 Sega</cite>

- __dual-forward-focus__
  - Focus switch is based on walking speed

The following camera trick from Super Mario World, is one of my favorite 2D camera techniques, with an overwhelming attention to the specific gameplay details of the game.

![ ][Super Mario World 2]
<cite>Super Mario World © 1990 Nintendo</cite>

- region-based-anchors
- __platform-snapping__ - camera snaps to the player only as it lands on a platform
  - Where applicable
- __camera-window__ (vert.)
  - Where applicable
- __dual-forward-focus__
  - Threshold triggered
- manual-control (horiz.)
  - Controller provides extra panning

Once again, there are two anchors allowing wide forward view in whatever direction the player chooses to go. However even as the player starts heading back (which happens constantly in SMW), the camera will keep the target point until Mario hits a predefined threshold, and only then will it lock to the other anchor. This is extremely helpful with SMW’s frequent left/right motion that does not warrant a direction change.

More recently, Cave Story uses dual-forward-focus to slowly move the focus point from side to side, based on the walking speed. A bit like what we’ve seen in Bonanza Bros, though in this case the camera moves towards the new anchor point at all times, but speeds up as the player moves.

![ ][Cave Story]
<cite>Cave Story © 2004 Studio Pixel</cite>

- __position-locking__ (vert.)
- __dual-forward-focus__
- __physics-smoothing__
- manual-control
  - Controller provides extra vertical panning

Jazz Jackrabbit 2 is a beautiful platformer from the early days of Epic Games. It had one truly unique camera element: it moved the camera away from the player based on controller input, both horizontally and vertically.

This is a perfect representation of what I call target-focus, where the players provide cues on where to shift the camera, based on their actual destination or target. When you walk left, you want to see more to the left. When the controller is released, focus is centered back on the player.

![ ][Jazz Jackrabbit 2]
<cite>Jazz Jackrabbit 2 © 1998 Epic Games</cite>

- __lerp-smoothing__ (vert.)
- __target-focus__ - camera follows controller input to provide true visual forward focus
  - Stick/cursor-keys push the focus point in the desired direction
- manual-control
  - Manual vertical look is an extension of target-focus

Target-focus can reflect an even more literal visual target, as seen in pointer controlled games. In Snapshot, you use the mouse to capture snapshots of elements in the scene and release them elsewhere to complete puzzles. The pointer essentially acts as an extension of your view, and the camera focus is the average position between the player and the pointer.

![ ][Snapshot]
<cite>Snapshot © 2012 Retro Affect</cite>

- __target-focus__
  - Average between player and pointer
- __lerp-smoothing__

The Swapper has some very advanced camera techniques that we’ll touch later. With regard to target-focus, the cloning device’s target spot serves as a representation of the player’s view and makes a perfect visual focus. This works well for any game with individually targeted weapons or devices. Players can even walk backwards and still view ahead if they wish, which provides a versatile camera behavior, but also requires a secondary control for the camera.

![ ][The Swapper]
<cite>The Swapper © 2013 Facepalm Games</cite>

- __target-focus__
- __physics-smoothing__
- region-based-anchors
- cue-focus
- cinematic-paths

Secrets of Rætikon has plenty of interesting camera features, but in terms of basic framing, it uses projected-focus which is a simple extrapolation of the character’s position based on its current speed.

Note that this technique may not work well in platforms, especially vertically, where jumps and especially landing don’t extrapolate well.

![ ][Secrets of Raetikon]
<cite>Secrets of Rætikon © 2014 Broken Rules</cite>

- __projected-focus__ - camera follows the projected (extrapolated) position of the player
- __physics-smoothing__
- cue-focus
  - Position and zoom based on attractors
- gesture-focus
  - Certain actions invoke preset camera behaviors, e.g. zoom-out when flying
- cinematic-paths

Luftrausers incorporates some great camera features with a very interesting combination of focus on where the plane is pointing to (target-focus), where’s it’s actually heading (projected-focus), and some other cues such as the water, battleships and flying bullets that draw the focus while in proximity (cue-focus, see below).

![ ][Luftrausers]
<cite>Luftrausers © 2014 Vlambeer</cite>

- __target-focus__ / __projected-focus__
- __physics-smoothing__
- cue-focus

# Direction

## Set up scene cues, context and progression
So far we’ve looked at how to provide the players with an accurate representation of their view and control, and in general, what the players want to see (Interaction, in our original diagram). We’ve also covered many different ways of making the view comfortable and effective (Comfort).

But as the directors of our game, we’d also like to set players’ attention on what’s we know is important for them to see, for reasons of context, progression and even drama and narrative.

Wonder Boy, another one of my favorites, is a high speed platformer, allowing forward progression only using good old ones-sided camera-window. Unlike Super Mario Bros., it has no speedup zone to curb camera acceleration, but it introduces another interesting camera technique which I call camera-path. The camera will be placed and moved to provide foreshadowing of upcoming challenges.

![ ][Wonder Boy]
<cite>Wonder Boy © 1986 Sega</cite>

- __camera-path__ - predefined progression path throughout the level
- __camera-window__
  - One-sided
- __static-forward-focus__

The 5th generation of consoles, with Playstation and N64 among others, opened up new capabilities backed up by better hardware and the inception of true 3D gaming. 3D camera techniques is a fascinating and huge subject in its own merit, but 3D support had a vast influence on 2D gaming as well. Designers could make use of zooming, tiling and even combine 2D and 3D in what we call now 2.5D, where the game takes place on a 2D plane, in a 3D world.

Playstation’s Klonoa is one of those games. The player has basic 2D controls, but the game takes place in an elaborate 3D world. Klonoa follows a 3D camera-path that provides direction and attention to gameplay and narrative details. that path provides positioning, tilting and zooming throughout all levels, and actually serves as a hint path on which forward focus and jumps can be applied.

![ ][Klonoa]
<cite>Klonoa: Door to Phantomile © 1997 Namco</cite>

- __camera-path__
  - Path hint, actually. Includes zooming and tilting.
- camera-window (vert.)
- lerp-smoothing
- dual-forward-focus

This type of control gives a rich set of tools to enable foreshadowing, surprise or even alarm in our games. When the camera in Klonoa zooms out to show the boss, it is clear what you need to do next.

Donkey Kong Country introduced some interesting characteristics which became standard in platformers: provide level designer with tools to change the camera behavior according to the content of the individual level, and even the individual region within level. Faster, runner style regions require a wide forward view at the expense of seeing what’s behind. Some exploratory regions require a wider view on both sides.

![ ][Donkey Kong Country 1]
![ ][Donkey Kong Country 2]
<cite>Donkey Kong Country © 1994 Nintendo (Rare Ltd)</cite>

- __lerp-smoothing__
- __position-locking__ (vert.)
- __region-based-anchors__ - different regions (even within levels) set different anchors for position and focus
- __dual-forward-focus__

As we’ve seen with Klonoa, the technology that allows presentation of 3D environments can be used to provide various direction tools, such as the use of zoom/dolly. Zoom is the act of changing the field-of-view angle (FOV), and Dolly is the film term for moving the camera forward or backward in relation to the target. They both achieve a similar goal of reframing the scene, albeit with a completely different approach, with dolly providing a strong physical presence (where applicable). More information on the difference between dolly and zoom can be acquired in film sites and databases. However for the sake of simplicity we’ll refer to both techniques as zoom-to-fit.

In Yoshi’s Story for example, the scene is framed around the Yoshi, the boss and the pillar, highlighting all the elements that require player’s attention: the target and the end of the field. The camera not only centers around these elements, it even zooms out (dollies out, actually) to provide the necessary focus.

![ ][Yoshis Story]
<cite>Yoshi’s Story © 1997 Nintendo (N64)</cite>

- __zoom-to-fit__ - change zoom or move forward/back to provide a close-up view of relevant elements
- dual-forward-focus
- camera-window (vert.)
- platform-snapping
- manual-control

Insanely Twisted Shadow Planet has a very influential camera system which takes into account the player’s speed (projected-focus), your target (target-focus), and most importantly is among the first to use attractors to help setting players’ attention to external cues. Check out ITSP’s [blog post](http://www.google.com/url?q=http%3A%2F%2Fmichelgagne.blogspot.com%2F2012%2F07%2Fitsp-camera-explained.html&sa=D&sntz=1&usg=AFQjCNEaBqw21c0H-4qjDgd1f3RGGUbJzg) for more information on this outstanding camera system.

![ ][Insanely Twisted]
<cite>Insanely Twisted Shadow Planet © 2011 Shadow Planet Productions</cite>

- __cue-focus__ - focus is influenced by game world cues (e.g. attractors)
  - Position and Zoom based on Double-Ring Attractors for various cues such as enemies and checkpoints
- __projected-focus__
- __target-focus__
- __physics-smoothing__

![ ][Double Ring]

ITSP uses double-ring attractor cues around various game cues such as checkpoints and enemies. The outer ring gradually shifts the camera focus towards the cue, using weighted average. When inside the inner ring, the position of the ship is completely ignored, and the camera focuses solely on the cue. Different cues have different rings, and those can overlap, which allows a smooth shift between different attractors.

There are different ways of attracting attention to game cues, but a Ring Attractors is a robust way of providing attention to gameplay elements that require it. This could also be used for the opposite reason: driving attention away from gameplay elements using Detractors that repel the camera away. This could be useful when trying to provide a sense of suspense and secrecy as to hidden elements.

Aether is a beautiful Flash game made in 2008 by Edmund McMillen and Tyler Glaiel, and it introduces a unique approach to cueing: it spins the world to indicate proximity to a planet, which communicates a sense of safety and guidance, where downwards inevitably leads to the ground. As you fly through space and get caught in a gravity field, the screen will start turning toward that gravity element.

![ ][Aether]
<cite>Aether © 2008 Armor Games (Edmund McMillen, Tyler Glaiel)</cite>

- __cue-focus__
  - Camera orientation shifts with gravity
- __position-locking__
- __lerp-smoothing__

No discussion on camera systems would be complete without talking about Limbo. By manipulating exposure, positioning and zooming, it creates a truly unique ambience. In Limbo, every region has unique characteristics, anchoring the positioning to a certain spot on the screen, and allowing certain objects to provide further camera cues, e.g. attractor objects on enemies.

![ ][Limbo]
<cite>Limbo © 2010 Playdead</cite>

- __region-based-anchors__
  - Zoom, position (and exposure)
- __position-locking__
  - Changes per region
- __cue-focus__
  - Certain actions trigger cues, e.g. enemy attacks, etc.
- __physics-smoothing__

Another simple yet effective approach is using region-focus, as used in Geometry Wars. It combines the position of the ship with the center of the field. This means that the screen is always in motion, the direction as the ship’s, at half the speed. Players always know where they are in the field by implicitly observing the offset from the center. This system work perfectly with enclosed, limited play fields, especially when threats are more likely to congregate in the center.

![ ][Geometry Wars]
<cite>Geometry Wars © 2003 Bizarre Creations</cite>

- __region-focus__ - focus on a region anchor (e.g. center of play field), combined with the player’s position
  - Camera position is the average of the ship and the center of the field

Vessel is a classic puzzle game where the player is required to notice many different elements in order to solve its liquid based puzzles, so camera regions even more significant. Just like in Geometry Wars, Strange Loop solved it by giving more emphasis to the regions, keeping the camera almost stationary while working on a puzzle. This is a modern interpretation of the old room-based puzzle games, but in Vessel the idea of room is much more flexible, with different sizes and characteristics.

![ ][Vessel]
<cite>Vessel © 2012 Strange Loop Games</cite>

- __region-focus__
  - Camera position is based mostly on region anchor point, but shifts slightly as the player moves
- __region-based-anchors__
  - Different regions provide different anchor positions and zoom factors
- __cue-focus__
- __physics-smoothing__
- cinematic-paths

One of the most clever ideas in Vessel is that even when confined to a region, the camera still follows the player with minor movements. This provides a strong sense of control, even in a confined area. Furthermore, as the player solves the puzzle and leaves the region, the camera is already in motion which minimizes the jarring camera acceleration as it shift to the next region.

Another way to use the camera to provide attention and drama is by using players’ behaviors to trigger predefined camera gestures. Tomba is an interesting game, from the first crop of 2.5D Playstation games. The camera here usually maintains the straight shooting angle, but it shifts into different angles when the player performs certain actions, like climbing or moving between depths. A unique sense of control is achieved when the camera shifts behind the player, while also providing a better view of what’s ahead.

![ ][Tomba]
<cite>Tomba! © 1997 Whoopee Camp</cite>

- __gesture-focus__ - gameplay triggered camera gestures
  - Camera shifts to positions reflecting gestures and states
- __dual-forward-focus__ (horiz.)
- __platform-snapping__
- __camera-window__ (vert.)

Gameplay triggered gestures can be used in different ways - various motion types and axes, reactive, predictive and so on. I believe that we’re still scratching the surface when it comes to the relationship between player driven actions and subsequent camera behavior.

A great example of the potential of gesture-focus can be found in Aztez, an upcoming fighting game. It uses different camera gestures such as zooming (moving forward and backward) or tilting, to add drama and context to certain fighting events such close encounters and final blows.

![ ][Aztez]
<cite>Aztez © [Release TBA] Team Colorblind</cite>

- __gesture-focus__
  - Zooming (move forward/back) and tilting triggered by gameplay actions
- __position-locking__ (vert.)
- __lerp-smoothing__
- __zoom-to-fit__

In Sega’s classic brawler Streets of Rage, the camera mostly follows the action using the one-sided camera-window, a standard brawler behavior. However, from time to time, the camera would step out-of-screen (or rather, away from the player) to provide an additional narrative or dramatic context.

![ ][Streets of Rage]
<cite>Streets of Rage © 1991 Sega</cite>

- __cinematic-paths__ - camera suspends normal function to provide an out-of-screen narrative context
- __region-based-anchors__
- __camera-window__
  - Standard brawler behavior: One-sided camera-window, effective between fights only

This system is very powerful, allowing the designers to provide a cinematic break without breaking the gameplay context, like a cut-less cutscene.

Cinematic paths are used well in The Behemoth’s Alien Hominid and Castle Crashers. In many different cases normal gameplay would be suspended and the camera would shift towards a boss or a story element. This achieves two goals - providing a narrative context as well as gameplay guidance - without drawing players’ focus from the action.

![ ][Alien Hominid]
<cite>Alien Hominid © 2004 The Behemoth</cite>

- __region-based-anchors__
- __cinematic-paths__
- __camera-window__
  - Standard brawler behavior: One-sided camera-window, effective between fights only

# Multi-focal Camera

## Focusing on multiple objects
As we’ve seen, even a single focal target presents a considerable challenge. So how do we address multiple players or targets?

Gauntlet was a groundbreaking dungeon crawler which with a highly advanced technology and design for its time. With multiple players on the screen, it simply locked the camera to their average positions. However, unless all players walked in the same direction, and as soon as the distance between the players reached the size of the screen, no player could move. In fact, if a player decided to leave but their character remained in play, everybody was stuck as players could could not cross (or push) the edges of the screen.

![ ][Gauntlet]
<cite>Gauntlet © 1985 Atari Games</cite>

- __position-averaging__ - focus on the average position of all targets

Samurai Gunn uses the same technique, but deliberately pushes it to the edge to form its hectic environment. This is even further emphasized with the frequent screen freezes and fadeouts. When it comes to the camera, as players frequently respawn or teleport, the average position immediately shifts, causing rapid changes of focus. In fact, even the basic edge-snapping is avoided, which allows the camera to step out level boundaries. This works well with the atmosphere, but can be uncomfortable to watch, especially for spectators. Naturally, when it gets to controlling your character, while uncommon, players can simply step out of the screen if they so choose so they’re never blocked by the screen edge.

![ ][Samurai Gunn]
<cite>Samurai Gunn © 2013 Teknopants</cite>

- __position-averaging__
- __lerp-smoothing__
- ~~__edge-snapping__~~
  - To achieve its hectic atmosphere, edge-snapping is unusually avoided, so the screen is almost constantly moving

Another approach can be found in good old Street Fighter, and throughout the franchise. It uses a horizontal camera window which keeps the camera steady for the most part. As with any camera-window, players hitting the window edge will pull the camera with them. When the camera moves, it may pull the other player with it, keeping all the players within the window. The camera (and the players) can only be stuck if both try to push the window in the opposite direction.

![ ][Street Fighter]
<cite>Street Fighter © 1987 Capcom</cite>

- __camera-window__ (horiz.)
  - Hitting the window edge pulls the camera, and may pull the other characters with it

Another franchise that redefined multiplayer is Nintendo’s Super Smash Bros. Even the first in the series had an outstanding camera treatment. SSB looks towards the average position of all players, and zooms out as much as needed when the distance between them grows.

![ ][Super Smash Bros]
<cite>Super Smash Bros. © 1999 Nintendo (HAL Laboratory)</cite>

- __zoom-to-fit__
- __position-averaging__
  - Technically look-to average position
- __lerp-smoothing__

This system still works well, and in the case of ROCKETSROCKETSROCKETS it serves a double purpose: fit everything in one frame, and also direct the players towards the center, punishing the players if they try to avoid close encounters.

![ ][RocketsRocketsRockets]
<cite>ROCKETSROCKETSROCKETS © 2014 Radial Games</cite>

- __zoom-to-fit__
- __position-averaging__

As previously shown in Never Alone, you can average the positions of any set of actors, single or multiplayer, possibly providing different averaging weight.

![ ][Never Alone]
<cite>Never Alone © 2014 Upper One Games</cite>

- __physics-smoothing__
- __position-averaging__
- __cinematic-paths__
- __region-based-anchors__
- __cue-focus__

Spelunky takes a different approach to the problem of conflicting positions by focusing on only one player at a time. If the player dies, the torch (the white flag) is passed to another player. This actually becomes a gameplay element by actually starting a death countdown to players out of the screen.

![ ][Spelunky]
<cite>Spelunky © 2008-2012 Mossmouth (Derek Yu)</cite>

- __position-locking__
- __lerp-smoothing__
- manual-control
  - Up/Down for extended vertical panning

# Manual Control

## Providing additional camera control to the player
In some cases, designers might need to provide additional visual information based on user choices. One way to do it is to tie camera to the controls.

Super Mario World was, once again, among the first to add extra camera control. Shoulder buttons would push the camera to the respective direction. While this might have been a clever idea, it’s often criticized as useless, and anyway most players don’t notice this feature to begin with.

![ ][Super Mario World 2]
<cite>Super Mario World © 1990 Nintendo</cite>

- __region-based-anchors__
- __platform-snapping__
  - Where applicable
- __camera-window__ (vert.)
  - Where applicable
- __dual-forward-focus__
  - Threshold triggered
- __manual-control__ (horiz.)
  - Controller provides extra panning

The problem with SMW’s additional manual control is exactly its unintuitive nature. The standard walking controls don’t provide any connection with the shoulder buttons.

A good example of providing intuitive manual camera control can be found in Osmos. Not exactly your standard scroller, but Osmos used a much more implicit way to change the camera. Mouse-wheel on desktops or pinch-to-zoom on tablets provide a clear connection between the control and its action.

![ ][Osmos]
<cite>Osmos © 2009 Hemisphere Games</cite>

- __position-locking__
- __manual-control__
  - Mouse-wheel / multi-touch pinch to change zoom

As seen above, in Jazz Jackrabbit 2 the extra controls for vertical panning perfectly correlate to their horizontal counterparts, and are thus predictable and clear.

![ ][Jazz Jackrabbit 2]
<cite>Jazz Jackrabbit 2 © 1998 Epic Games</cite>

- __lerp-smoothing__ (vert.)
- __target-focus__ - camera follows controller input to provide true visual forward focus
  - Stick/cursor-keys push the focus point in the desired direction
- __manual-control__
  - Manual vertical look is an extension of target-focus

If manual focus extension is required, use the controls that are already in effect, like in Spelunky, where crouching or looking up shifts the camera focus respectively.

![ ][Spelunky 2]
<cite>Spelunky © 2008-2012 Mossmouth (Derek Yu)</cite>

- __position-locking__
- __lerp-smoothing__
- __manual-control__
  - Up/Down for extended vertical panning

# Camera Shake

## All control is lost
As we’ve seen throughout this research, providing true and clear camera controls invokes a sense of unity between the player and the virtual world behind the screen. The opposite is also true: a disconnection between the camera and the controls, as achieved by a camera/screen shake, can provide a sense of drama as an action that’s more powerful than the player itself.

In my research I tried to find the first game to use camera shake. It wasn’t surprising to find that it lead to another Miyamoto title, back in 1983: Mario Bros. The screen shake only occurs in the arcade version, probably due to technical or time constraints on the NES.

![ ][Mario Bros]
<cite>Mario Bros. © 1983 Nintendo</cite>

Screen shakes (and freezes, which achieve a similar effect) have been used in countless games and can be seen in practically all of Vlambeer’s work through the years. Check out Vlambeer’s designer JW [talk about this issue at length](http://www.youtube.com/watch?v=AJdEqssNZ-U).

![ ][Super Crate Box]
<cite>Super Crate Box © 2010 Vlambeer</cite>

# Custom-Made Camera

## Putting it all together: Tailoring the camera to your game
The level of details and attention put in your game is vast. As much as any other element, the camera deserves your attention. Before you set up the default target-locked camera, try to characterize how you would ideally want your camera to work in your game.

Here are some basic ground rules that served me well when making my own game, and obviously led into this research.

- Find the unique and significant characteristics of your game
- Get inspired by other games facing similar challenges
- Make it your own

Clearly, this does not end at camera work. This applies to any facet of your game, be it art, audio, tech, and so on.

Here’s a great example of tailoring the camera to the gameplay. Taito’s The Legend of Kage was one of the first dual-axis platformers. (Fun fact: it’s also one of the first, and only, games to make the principal progress direction right to left.) Note the use of the horizontal camera-window. Many epic battles happen on trees, so the camera window is set to exactly a width of a tree, stabilizing the camera to avoid the rapid direction changes while in battle.

![ ][The Legend of Kage]
<cite>The Legend of Kage © 1985 Taito</cite>

- __position-locking__ (vert.)
- __camera-window__ (horiz.)
  - Window size is based on the width of a tree

Another good example of tailoring existing systems to your design is Shinobi. To enable its high jumps, it provides a tall camera-window, almost the height of the entire screen. Then, to avoid drifting off the center, a slow position snapping occurs.

![ ][Shinobi]
<cite>Shinobi © 1987 Sega</cite>

- __position-snapping__ (vert.)
- __camera-window__ (vert.)
- __position-locking__ (horiz.)
- __static-forward-focus__

Sonic the Hedgehog is a multi-axis high-speed platformer. The narrow window is designed to keep Sonic in the center of the screen at all time, as the player must always maintain a clear vision of what’s quickly coming ahead. The window is taller to further limit the vertical motion produced by smaller jumps. This is countered by the use of platform-snapping which maintains vertical alignment as long as Sonic is on a platform.

However, hitting the edge of the small window at such high speeds can get a bit jarring at times, especially in loops, or when descending to the bottom of the window with full gravitational speed.

![ ][Sonic The Hedgehog]
<cite>Sonic the Hedgehog © 1991 Sega</cite>

- __platform-snapping__
- __camera-window__
- __static-forward-focus__
- __manual-control__

Sonic 2 solved this very problem by using the old SMB trick: as Sonic moves back within the window, its speed is decelerates and accelerates to the opposite direction so when it hits the edge, the camera is already moving in the right direction. As seen below, this transition feels smooth even in high speed loops.

This also means that the camera would always be in motion, which defeats the original purpose of camera-window, but it is clear that in a fast-paced game like Sonic it is already the case.

![ ][Sonic The Hedgehog 2]
<cite>Sonic the Hedgehog 2 © 1992 Sega</cite>

- __platform-snapping__
- __camera-window__
- __speedup-push-zone__
  - Decelerate and accelerate as movement direction changes
- __forward-focus__
- __manual-control__

When a wide forward view is required, but motion is not limited to any direction, dual-forward-view is a natural choice. There are different ways to snap the view to the desired anchor following a direction change. Cave Story does a great job, dynamically changing the snapping speed based on the player’s walking speed (e.g. base snapping speed plus walking speed). Bonanza Bros. used a slightly different method, limiting the movement only to when the player walked, which worked for a heist game, but not necessarily to an enemy-packed platformer like Cave Story.

![ ][Cave Story]
<cite>Cave Story © 2004 Studio Pixel</cite>

- __position-locking__ (vert.)
- __dual-forward-focus__
- __physics-smoothing__
- __manual-control__
  - Controller provides extra vertical panning

Fez doesn’t have armies of enemies coming at you, so a basic camera-window makes sense. But Fez designer cleverly repurposed this classic technique to closely fit the unique design of the game. You could argue that with corners being a common spot for dimension shifts, what’s behind you is actually more important than what’s ahead. Furthermore, during a dimension shift, the camera is refocused to provide a maximum forward distance to the window edge, post dimension shift.

![ ][Fez]
<cite>Fez © 2012 Polytron Corporation</cite>

- __camera-window__ (horiz.)
  - Also enforced during dimension shifts
- __position-locking__ (vert.)
- __lerp-smoothing__
- __region-based-anchors__
- __manual-control__
  - Right-stick provides extra panning

The approach taken in Vessel represents a perfect design solution for a puzzle game that could otherwise be based on one puzzle per room. The use of region-focus to frame (and zoom) the camera around all necessary puzzle element provides a clear presentation to the player. The added player-based shifts provides a better sense of control, and eases the camera into motion when moving between regions, overall achieving a good combination of preset framing with solid perceived control.

![ ][Vessel]
<cite>Vessel © 2012 Strange Loop Games</cite>

- __region-focus__
  - Camera position is based mostly on region anchor point, but shifts slightly as the player moves
- __region-based-anchors__
  - Different regions provide different anchor positions and zoom factors
- __cue-focus__
- __physics-smoothing__
- __cinematic-paths__

As we’ve seen, The Swapper tells a very elaborate story with its unique ambience, achieved with just manipulating the camera across different cinematic paths. This keeps the player in the game at all times, providing drama while not losing the sense of direction that is sometimes lost with cut-scenes.

![ ][The Swapper 2]
<cite>The Swapper © 2013 Facepalm Games</cite>

- __target-focus__
- __physics-smoothing__
- __region-based-anchors__
- __cue-focus__
- __cinematic-paths__

# Mushroom 11

## The camera choices I’m making
The camera system in Mushroom 11 is based on meticulous per-region camera direction. Each level is comprised of dozens of different regions, and each region has a dedicated rectangular path which the camera is confined to. That area also has a preset zoom (FOV factor).

![ ][Mushroom 11 1]
<cite>Mushroom 11 © [Release TBA] Untame</cite>

- __region-based-anchors__
  - Preset rectangular path and zoom factor per region
- position-averaging
  - In applicable regions only
- static-forward-focus
  - In applicable regions only
- cue-focus
  - In applicable regions only
- projected-focus
- physics-smoothing
  - Speed based smoothing-factor

Regions are carefully ordered, and the camera is controlled by the mushroom piece(s) in the highest numbered region. As soon as any piece, even a single cell, reaches a higher numbered region, the camera would shift to follow that piece.

![ ][Mushroom 11 2]
<cite>Mushroom 11 © [Release TBA] Untame</cite>

- __region-based-anchors__
  - Preset rectangular path and zoom factor per region
- position-averaging
  - In applicable regions only
- static-forward-focus
  - In applicable regions only
- cue-focus
  - In applicable regions only
- projected-focus
- physics-smoothing
  - Speed based smoothing-factor

Note that the camera borders destroy any cells on touch, which makes the stakes for camera accuracy even higher. This is illustrated well in the above example, which provides enough room for the player to devise a solution, followed by a quick camera shift as a piece reaches the new region. All this is achieved without letting the screen edge destroy any significant cell.

Regions come in two major types: Average-Oriented and Progression-Oriented. The region type dictates where the camera tries to focus. After the focal point is determined, the camera would try to move toward that point while being confined to the region’s rectangular path.

## Average-Oriented Region
Some regions use position-averaging between all the cells, naturally focusing the camera towards the larger mushroom piece. This is effective in areas where the player is required to handle multiple pieces or when there is no single progression direction. This region type lends itself well to confined puzzle areas, where the pieces remain in acceptable proximity (or otherwise could be hit by the screen edge).

![ ][Mushroom 11 3]
<cite>Mushroom 11 © [Release TBA] Untame</cite>

- __region-based-anchors__
  - Preset rectangular path and zoom factor per region
- __position-averaging__
  - In applicable regions only
- static-forward-focus
  - In applicable regions only
- cue-focus
  - In applicable regions only
- projected-focus
- physics-smoothing
  - Speed based smoothing-factor

## Progression-Oriented Region
Regions with a more linear nature need to focus on most progressed mushroom. At any given moment, the most progressed mushroom piece (according to the region’s preset linear progression path) controls the camera, while pieces left behind are ignored. An additional static-forward-focus distance is then applied, which fits this type of region well.

![ ][Mushroom 11 4]
<cite>Mushroom 11 © [Release TBA] Untame</cite>

- __region-based-anchors__
  - Preset rectangular path and zoom factor per region
- __position-averaging__
  - In applicable regions only
- __static-forward-focus__
  - In applicable regions only
- cue-focus
  - In applicable regions only
- projected-focus
- physics-smoothing
  - Speed based smoothing-factor

## Cues
Either region type can be used in conjunction with cue-focus. While controlled by this region, certain objects and creatures can serve as camera attractors, with specified/dynamic attraction factor. As seen below, boss battles are obvious candidates for this approach.

![ ][Mushroom 11 5]
<cite>Mushroom 11 © [Release TBA] Untame</cite>

- __region-based-anchors__
  - Preset rectangular path and zoom factor per region
- __position-averaging__
  - In applicable regions only
- __static-forward-focus__
  - In applicable regions only
- __cue-focus__
  - In applicable regions only
- projected-focus
- physics-smoothing
  - Speed based smoothing-factor

## Smoothing
Smoothing is done using a combination of projected-focus and physics-smoothing. What works well is using a smoothing factor that is based on the velocity of the mushroom: if player moves fast, the camera is accurate (and jumpy) and if player gently trims the mushroom, it cruises gently.

Since there are no jumps in the game, the use of projected-focus is natural. By aiming the camera at where the mushroom piece (or the average of all pieces) is projected to be in a few milliseconds, a more accurate and predictive behavior is achieved.

![ ][Mushroom 11 6]
<cite>Mushroom 11 © [Release TBA] Untame</cite>

- __region-based-anchors__
  - Preset rectangular path and zoom factor per region
- __position-averaging__
  - In applicable regions only
- __static-forward-focus__
  - In applicable regions only
- __cue-focus__
  - In applicable regions only
- __projected-focus__
- __physics-smoothing__
  - Speed based smoothing-factor

Once all these behaviors are defined, the camera system is equipped to handle multiple dynamically changing pieces with different sizes and speeds, moving quickly across regions.

![ ][Mushroom 11 7]
<cite>Mushroom 11 © [Release TBA] Untame</cite>

- __region-based-anchors__
  - Preset rectangular path and zoom factor per region
- __position-averaging__
  - In applicable regions only
- __static-forward-focus__
  - In applicable regions only
- __cue-focus__
  - In applicable regions only
- __projected-focus__
- __physics-smoothing__
  - Speed based smoothing-factor

# Glossary
- __auto-scroll__ - Player only has no control over scrolling
- __camera-path__ - Predefined progression path throughout the level
- __camera-window__ - Push camera position as the player hits the window edge
- __cinematic-paths__ - Camera suspends normal function to provide an out-of-screen narrative context
- __cue-focus__ - Focus is influenced by game world cues (e.g. attractors)
- __dual-forward-focus__ - Player direction changes switch camera focus to enable wide forward view
- __edge-snapping__ - Set a hard edge for camera positioning
- __gesture-focus__ - Gameplay triggered camera gestures
- __lerp-smoothing__ - Continuously reduce the distance between camera and active player using Linear Interpolation
- __physics-smoothing__ - Camera is a physics enabled entity, constantly closing on the focus target
- __platform-snapping__ - Camera snaps to the player only as it lands on a platform
- __position-averaging__ - Focus on the average position of all relevant targets
- __position-locking__ - Camera is locked to the player’s position
- __position-snapping__ - Constantly reduce window drift by focusing the camera back on the player
- __projected-focus__ - Camera follows the projected (extrapolated) position of the player
- __region-based-anchors__ - Different regions (even within levels) set different anchors for position and focus
- __region-focus__ - Focus on a region anchor, combined with player’s position
- __speedup-pull-zone__ - Pull the camera to catch up with player’s speed after it crosses over window’s edge
- __speedup-push-zone__ - When inside the push-zone, gradually accelerate the camera to catch up with player’s speed
- __static-forward-focus__ - Extra view space in the principal progression direction
- __target-focus__ - Camera follows controller input to provide true visual forward focus
- __zoom-to-fit__ - Change zoom or move forward/back to provide a close-up view of relevant elements

# Thanks!
I want to thank the wonderful independent gaming community for their extensive help in this research, and a special thank you goes to the [NYU Game Center](https://www.google.com/url?q=https%3A%2F%2Ftwitter.com%2Fnyugamecenter&sa=D&sntz=1&usg=AFQjCNH4YstV3zWeBqK1Bx2gMFg3D_qGdw) for their tremendous support.

[Eye]: ./eye.jpg
[Ear]: ./ear.jpg
[Elements]: ./elements.jpg
[Nostalgia]: ./nostalgia.jpg
[Rally-X]: ./rally-x.gif
[Kung-Fu Master]: ./kung-fu-master.gif
[Terraria]: ./terraria.gif
[Jump Bug]: ./jump-bug.gif
[Rastan Saga]: ./rastan-saga.gif
[Fez]: ./fez.gif
[Shinobi]: ./shinobi.gif
[Super Mario World]: ./super-mario-world.gif
[Rayman]: ./rayman.gif
[Awesomenauts]: ./awesomenauts.gif
[80s Pixel]: ./80s-pixel.jpg
[Indie Pixel]: ./indie-pixel.jpg
[Pac-land]: ./pac-land.gif
[Excitebike]: ./excitebike.jpg
[Devil World]: ./devil-world.jpg
[Super Mario Bros]: ./super-mario-bros.gif
[Metroid 1]: ./metroid-1.gif
[Metroid 2]: ./metroid-2.gif
[Donkey Kong Country]: ./donkey-kong-country.gif
[Super Meat Boy]: ./super-meat-boy.gif
[Never Alone]: ./never-alone.gif
[Hyper Light Drifter]: ./hyper-light-drifter.gif
[Scramble]: ./scramble.gif
[Defender]: ./defender.gif
[Bonanza Bros]: ./bonanza-bros.gif
[Super Mario World 2]: ./super-mario-world-2.gif
[Cave Story]: ./cave-story.gif
[Jazz Jackrabbit 2]: ./jazz-jackrabbit-2.gif
[Snapshot]: ./snapshot.gif
[The Swapper]: ./the-swapper.gif
[Secrets of Raetikon]: ./secrets-of-raetikon.gif
[Luftrausers]: ./luftrausers.gif
[Wonder Boy]: ./wonder-boy.gif
[Klonoa]: ./klonoa.gif
[Donkey Kong Country 1]: ./donkey-kong-country-1.gif
[Donkey Kong Country 2]: ./donkey-kong-country-2.gif
[Yoshis Story]: ./yoshis-story.gif
[Double Ring]: ./double-ring.jpg
[Insanely Twisted]: ./insanely-twisted.gif
[Aether]: ./aether.gif
[Limbo]: ./limbo.gif
[Geometry Wars]: ./geometry-wars.gif
[Vessel]: ./vessel.gif
[Tomba]: ./tomba.gif
[Aztez]: ./aztez.gif
[Streets of Rage]: ./streets-of-rage.gif
[Alien Hominid]: ./alien-hominid.gif
[Gauntlet]: ./gauntlet.gif
[Samurai Gunn]: ./samurai-gunn.gif
[Street Fighter]: ./street-fighter.gif
[Super Smash Bros]: ./super-smash-bros.gif
[RocketsRocketsRockets]: ./rocketsrocketsrockets.gif
[Spelunky]: ./spelunky.gif
[Osmos]: ./osmos.gif
[Spelunky 2]: ./spelunky-2.gif
[Mario Bros]: ./mario-bros.gif
[Super Crate Box]: ./super-crate-box.gif
[The Legend of Kage]: ./the-legend-of-kage.gif
[Sonic The Hedgehog]: ./sonic-the-hedgehog.gif
[Sonic The Hedgehog 2]: ./sonic-the-hedgehog-2.gif
[The Swapper 2]: ./the-swapper-2.gif
[Mushroom 11 1]: ./mushroom-11-1.jpg
[Mushroom 11 2]: ./mushroom-11-2.gif
[Mushroom 11 3]: ./mushroom-11-3.gif
[Mushroom 11 4]: ./mushroom-11-4.gif
[Mushroom 11 5]: ./mushroom-11-5.gif
[Mushroom 11 6]: ./mushroom-11-6.gif
[Mushroom 11 7]: ./mushroom-11-7.gif