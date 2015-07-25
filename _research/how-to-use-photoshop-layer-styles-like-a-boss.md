---
layout: article
title: How To Use Photoshop Layer Styles Like a Boss
author: Dave Bleja
source: http://www.volnaiskra.com/volblog/how-to-use-layer-styles-for-efficient-and-versatile-game-illustration-advanced-guide
priority: 4
---

# Introduction
If you're like many Photoshop users, you might not use Layer Styles much. Or maybe you think that they're only good for cheesy bevel and drop shadow effects. Actually, Layer Styles can be very powerful and surprisingly versatile. In fact, I do almost all of Spryke's graphics using Layer Styles (applied onto vector shapes).

![ ][Spryke Screenshot]
<cite>Some 80% of the elements in this screenshot are comprised of Layer Styles applied onto vector shapes. Basically everything except for the sky, fog, and some windows.</cite>

# Quick Rehash: What are Layer Styles Again?
To access Layer Styles, double-click a layer in photoshop. From there, you can tweak various settings to alter the appearance of the layer. Layers that contain Layer Styles have an "fx" icon on them. If you make a Layer Style that you think you'll reuse, you can save it in the "Styles" palette.

![ ][Vector Shapes]
<cite>These six identical vector shapes (well, twelve actually, including the little ones in the corners) each have a different Layer Style that greatly affects how it appears.</cite>

Below is one of the above layers shown with all of its Layer Style attributes. Not every Layer Style needs to be this complex of course, but by stacking multiple attributes like this, you can achieve a great deal of variety and visual subtlety.

This particular Layer Style is used for lights and other illuminated objects. It has a round inner glow (from __Gradient Overlay__), intense coloring (__Color Overlay__ and __Satin__, both using _Overlay Blend Mode_),  noise (__Inner Glow__),  and a somewhat intense reddish glow (__Stroke__, __Outer Glow__, __Drop Shadow__).

![ ][Light Layer]

This next Layer Style provides a worn diamond metal plate look. The foundation of the Layer Style is the __Pattern Overlay__, which provides the diamond plate texture. The colour is first neutralised somewhat (__Color Overlay__), then intensified (__Satin__ with _Overlay Blend Mode_). Finally, a subtle degraded appearance is added by a rust-coloured __Inner Shadow__.

![ ][Diamond Layer]

# What's the Benefit of Layer Styles?
There are three main benefits, all of which intertwine:

## Non-destructiveness
I'm a firm believer in keeping your workflow as non-destructive as possible. The secret of great design is iteration, and keeping everything editable rather than locked down makes iteration much easier. Thanks to Layer Styles, I can tweak, overhaul, swap or remove the appearance of just about any visual element at any stage.

## Quickness
Certain things are just way quicker using Layer Styles than with most other methods. Some examples include: filling with a solid color, creating an outline, adding some noise, creating a glow effect, or filling an effect with a pre-existing texture or image (using __Pattern Overlay__).

## Re-usability
Layer Styles can be copied and pasted from one layer to another, and saved in the Styles palette. This is of particular use to game artists, since we tend to make a large amount of assets, many of which share similar stylistic traits.

When you combine all of these benefits, you get a workflow that is efficient, highly organic, and can grow and evolve with your project. As you work, you can build up a library of Layer Styles that you apply to subsequent assets, tweaking and experimenting when necessary. As your project's aesthetic evolves, you can retrofit earlier assets with updated stylings.

# Are There Drawbacks of Layer Styles?
A few. For one, they aren't a silver bullet (but then, with the possible exception of actual silver bullets, what is?). As you'll see below they can do a lot, but they can't do everything. Sometimes you'll still need to use other techniques (painting, photography, filters, etc.) in conjunction with Layer Styles.

They also have a few rigid idiosyncracies. For example, the number, type, and order of attributes are fixed (eg. you can only have one __Pattern Overlay__, and it always must be below any __Color Overlay__). And certain behaviours (eg. __Stroke__ combined with translucency) are just plain weird.

But with a little ingenuity these problems can, for the most part, be solved or worked around. More on that later.

Probably the most serious drawback of Layer Styles is performance. If you're using just a handful of Layer Styles then no problem, but if you use hundreds like I do, Photoshop can start to get laggy, no matter how good your computer is (mine's a [beast](http://www.volnapc.com/about.html)) - especially if you're using lots of different blending modes inside them. This isn't really the fault of Layer Styles per se; the performance hit comes from using loads of layers and blending modes in general.

The solution here is to be smart about how you work. Group separate elements in your composition into folders (Layer Groups) and turn them off when necessary. Or, better yet, turn them into Smart Objects. This removes their resource footprint from the current document by displaying a flattened, rasterized version (which you can double-click to access the original editable layers). In the image at the top of this post, every ship and every building is a separate smart object (some of them duplicated).

# Creating a Layer Style Library
As your project grows, it's a good idea to start saving your Layer Styles in one place, to make re-use easier. You can use the Styles palette for this (that's exactly what it's for) but I prefer to lay them all out in a separate PSD, as you can see below. This lets me lay them out in more organised way, with labels and compartmentalised groups.

Also, the Styles palette is comprised of squares, while the PSD method allows me to use custom shapes that will better represent the potential of each Layer Style. As you can see below, I use two shapes per Layer Style; together, they show me what a layer style looks like on a large layer, a tiny layer, a round edge, straight edge, corner, and hole.

![ ][Style Library]
<cite>The Layer Style library I use for Spryke</cite>

# Combining Layer Styles
Here you can see a step-by-step process of how I applied layer styles to one of Spryke's elements - a "Weasel" ship. The majority of layers are Vector Shapes (shown initially as wireframe). I add a few small raster elements in the last step.

As you add Layer Styles to differently shaped objects, you may need to tweak them a little. For example, the angle of the red gradient on the wing needed to be rotated when applied to the tail. Similarly, the size of the glow of a large light might need to be taken down a notch when applied to a small one. Thankfully, the non-destructiveness of Layer Styles make this kind of fine-tuning pretty easy.

Also, take note that in some cases, I couldn't achieve everything I wanted in one Layer Style, so I had to duplicate a layer and use more than one set of Layer Styles. This mainly occurred in the context of __Pattern Overlays__, the only way to import a raster image into Layer Styles. Photoshop only permits one __Pattern Overlay__ per layer style, but I wanted three - a dirty texture, black scratches, and white scratches - so I had to use three identical layers, each with its own Layer Style. (I could have combined all three textures into one pattern, but that would have given me less flexibility.)

![ ][Ships 1]
![ ][Ships 2]

And here's one of Spryke's buildings. Again, practically every element is a Vector Shape with Layer Styles applied to it. (A few more Layer Styles were used than what is shown, but this is the bulk of them).

![ ][Building]

# Layer Styles For Versatility
Because they're so tweakable and non-destructive, Layer Styles are excellent for creating variations of your assets, and even for early experimentation and brainstorming.

![ ][Ship Variations]
![ ][Variations]

# Layer Styles As Internal Adjustment Layers
So far, I've concentrated on Layer Styles used on their own (ie. setting _Fill Opacity_ to 0% so that none of the original layer contents can be seen). But Layer Styles can also be used as a quick and easy way of adjusting a layer's existing contents, as you would with an Adjustment Layer.

Let's say you want to desaturate a layer. You could do Image>Adjustments>Desaturate (Ctrl-Shift-U), which is very quick but also destructive (you can't change your mind and revert to color later).

You could also use a Hue/Saturation or Black&White adjustment layer. This is non-destructive (and in the case of Black&White, very nuanced), but it's also a little clunky: it creates a separate layer, and by default it'll desaturate all layers underneath it, not just your target layer.

A third option is to use a simple Layer Style: __Color Overlay__, black (or white, or grey), 100% _Opacity_, _Saturation Blend Mode_. This is relatively quick, non-destructive, and has a light footprint in your Layers palette. And of course, you can save the Layer Style so you can copy/paste it to other layers later.

Below are a few examples of possible adjustment types, including desaturation, contrast, colorize, noise, and brightness. Note that in the centremost version, I've used __Satin__ to change the color of the circular metal area without affecting the rest of the creature (more or less).

One of the benefits of this approach is that you can stack multiple effects using __Pseudo Color Overlays__ (see next section) all within just one Layer Style, which helps keep your document compact.

![ ][Adjustments]
<cite>Spryke, shown with various adjustments, using Layer Styles</cite>

# Pseudo Color Overlays
> UPDATE (24 June 2015): Photoshop CC 2015 has introduced the ability to use multiple versions of the same Layer Style attribute within the same Layer Style. So, we can now click a "+" button to get up to 10 __Color Overlays__ at once. This is nice, and alleviates the need for __Pseudo Color Overlays__ somewhat, though not completely.

> As of writing, you still can't rearrange the order of Layer Style Attributes. So, for example, if you want a __Color Overlay__ that is applied over the top of an __Inner Glow__, or before a __Gradient Overlay__, you'll still need to use the appropriate __Pseudo Color Overlays__.

In the next section, I'll go through each of the attributes with tips and tricks for each. But first I want to bring attention to what I've dubbed __Pseudo Color Overlays__.

__Color Overlay__ allows us to apply a colour to the entire layer, which makes it highly useful. Ostensibly, it's the only Layer Style attribute that does so. However, with the correct settings, a number of the other attributes can be made to function in essentially the same way. Here is a list of __Pseudo Color Overlays__, in order of quickest to most convoluted:

- __Inner Shadow__: 30000px Distance, 0% Choke
- __Satin__: 1px Distance, 250px Size
- __Inner Glow__: 100% Choke, 0px Size, Source: Center
- __Gradient Overlay__: Set up a gradient with identical colour on both ends of spectrum
- __Pattern Overlay__: Create custom pattern that is just a single colour, and use that

Why is this useful? Because it allows you to apply several entire-layer adjustments to a layer in one go. I'll illustrate this with an example.

Let's imagine that we have a shiny blue spaceship that we'd like to make look a bit more aggressive: red, more starkly contrasted, and a little rougher-looking. Also, we want to do this non-destructively.

We'll need to change the ship's color, add texture, and fine tune the brightness/contrast. With the Adjustment Layer method, this would require several new layers. But with Pseudo Color Overlays we can do it all on the original layer, a more compact and more portable solution.

OK, here's our initial blue ship:

![ ][Pseudo 1]

First, we use a Pseudo Color Overlay (__Gradient Overlay__ in this case) to change the hue of the entire layer from red to blue:

![ ][Pseudo 2]

That's a good start, but it feels too monochrome and maybe a bit too plasticky. Let's add a second color into the mix for nuance, using the 'real' __Color Overlay__ this time.

![ ][Pseudo 3]

That's more interesting, though the addition of cyan tinges has messed up our reds (and whites) a bit. Let's counteract that by applying another reddish colour over the whole layer with another Pseudo Color Overlay (__Satin__, using the settings listed earlier). We'll use an _Overlay Blend Mode_ again to boost the contrast:

![ ][Pseudo 4]

OK, the color looks good. Finally, let's add a little bit of noise to the whole thing for a bit of a rougher texture, using __Inner Glow__:

![ ][Pseudo 5]

OK, there we have it. The method was perhaps a little quick and dirty, but the results are satisfactory. Our ship is redder, rougher, and has a sharper contrast. And, thanks to __Pseudo Color Overlays__, the whole thing was achieved with just one Layer Style which can easily be disabled, modified, or copied/pasted at any time.

![ ][Pseudo Complete]

# Tips and Tricks for each Layer Style Attribute
OK, I'll now provide a few tips, tricks, and potential pitfalls of each Layer Style attribute. I won't explain the basics about each attribute, because you can find those out yourself with a few minutes of experimentation, if you don't know them already.

## Bevel & Emboss

- Can be useful as a cheap method to create some depth, but proceed with caution. Along with filters such as Filter>Stylize>Find Edges, nothing says "it's my first time using Photoshop!" like heavy-handed use of Bevel & Emboss.
- Using Outer Bevel and Smooth, it can be used as a substitute for Drop Shadow
- Using Inner Bevel, Chisel Soft, Depth 1000%, Soften 0, Angle 0, Altitude 0, Shadow Mode Normal, it approximates an inside Stroke, but without the translucency bug (see below)
- The Texture section allows you to import a monochrome version of any raster image as a highly configurable sort of bump map
- The Link with Layer checkbox in the Texture section refers to whether or not the texture will change when you move the layer around the canvas

## Stroke

- Stay away from blend modes other than Normal 100%, because of the translucency bug (I don't know if this is a bug or a feature, but it's damn annoying so I'm calling it a bug): Applying a Stroke negates all other Layer Style attributes for the affected pixels. For example, if you apply a red Color Overlay and then a blue 6px Inside Stroke, and turn down the stroke's opacity to 50%, instead of seeing a 6px band of purple surrounding the shape, you'll just see a faint blue band, because the red Color Overlay in that 6px band has vanished. See Bevel & Emboss, Inner Shadow and Drop Shadow for workarounds to this problem.
- Whenever a stroke looks jaggy or weird, try the other two position settings, as they can sometimes have surprisingly different results.

## Inner Shadow

- Draggable: while the Inner Shadow section is selected in an open Layer Style dialog, you can drag the canvas to adjust the positioning of the effect
- Don't let its name limit you - it can be used for much more than shadows; try it with various Blend Modes
- It's one of three effects that includes a Noise slider. This makes it great for quickly adding a bit of texture to an object (try it with Overlay, Screen, or Multiply)
- With a 30000px distance and 0% Choke, Inner Shadow becomes a Pseudo Color Overlay (see previous section). Use this in conjunction with Noise to apply noise over the entire layer.
- With a 0px Distance and 100% Choke, it effectively becomes an Inside Stroke without the translucency bug. Use it in conjunction with an Outside Stroke if you want a two-coloured border on an object

## Inner Glow

- Like Inner Shadow and Drop Shadow, it contains a Noise setting
- With 100% Choke and Source: Edge, it effectively becomes another Inside Stroke without the translucency bug. Use it in conjunction with an Outside Stroke if you want a two-coloured border on an object, and add a smaller 0 Distance, 100% Choke Inside Stroke for a three-color border
- With 100% Choke, Source: Center, and 0px Size, it becomes a Pseudo Color Overlay
- Despite Inner Glow appearing above Satin, Satin's effects will be displayed over the top of Inner Glow's. I assume this is a bug.

## Satin

- Usually only affects a portion of the inside of a layer, so use this to add nuance to an other-wise flat layer.
- Draggable: while the Satin section is selected in an open Layer Style dialog, you can drag the canvas to adjust the positioning of the effect
- Can sometimes be used to affect only certain elements of an image by carefully adjusting angle, distance, and size, though this potential is constrained by the limited control of the settings.
- With 1px Distance, 250px Size, it becomes a Pseudo Color Overlay

## Color Overlay

- The simplest of the Layer Style attributes
- Affects entire layer, which is very useful
- Depending on which Blend Mode you use, you can use it for different purposes including, but not limited to: desaturate (Saturation), intensify (Overlay, Color Dodge), tint (Color, Hue), de-tint (Subtract), adjust brightness/contrast (Darken, Multiply, Lighten, Screen, Luminosity)
- Can be simulated by Pseudo Color Overlays, which allows several whole-layer effects at once

## Gradient Overlay

- Useful for helping to simulate lighting or depth
- Try using a gradient with a combination of opaque and transparent areas to add a glass-like glare or sheen
- Draggable: while the Gradient Overlay section is selected in an open Layer Style dialog, you can drag the canvas to adjust the positioning of the effect
- A Gradient Overlay that looks good on one shape will frequently need to be adjusted before it looks good on another shape.  Before adjusting the gradient itself, try fiddling with Reverse, Angle, and Scale, as well as dragging the canvas

## Pattern Overlay

- Basically allows you to import any raster image into your Layer Styles, which adds a whole new dimension of possibilities. As well as actual patterns, this can be used to add texture, photographs, or even text to your Layer Styles.
- Consider creating custom patterns specifically for use with Layer Styles (Edit>Define Pattern)
- By using a custom pattern that is a single solid color, this becomes a Pseudo Color Overlay. Because of Pattern Overlay's position in the attribute hierarchy, this is also the only Color Overlay (pseudo or otherwise) that lets you use a Gradient Overlay over the top of it.
- Draggable: while the Pattern Overlay section is selected in an open Layer Style dialog, you can drag the canvas to adjust the positioning of the effect
Remember to play with the Scale slider, as it can make a powerful contribution to the effect
- The Link with Layer checkbox refers to whether or not the texture will change when you move the layer around the canvas

## Outer Glow

- Don't let the name limit you. With the right blending modes and colors, it can be used to simulate shadows too.
- Use it in conjunction with Drop shadow to simulate lighting from two simultaneous sources.
- Match the Color, Blend Mode, and Opacity with those of Color Overlay for a seamless continuity between the two effects (great for making fire or lights)
- With a 100% Spread, it effectively becomes an Outside Stroke without the translucency bug. Use it in conjunction with an Inside Stroke if you want a two-coloured border on an object.

## Drop Shadow

- Don't let the name limit you. With the right Blend Mode, it can be used to simulate glows too. Try combining it with Outer Glow for a two-part glow (eg. a large soft blue glow with noise combined with a short, intense white glow without noise)
- Draggable: while the Drop Shadow section is selected in an open Layer Style dialog, you can drag the canvas to adjust the positioning of the effect
- If the rest of your Layer Style is translucent or transparent, uncheck Layer Knocks Out Drop Shadow to avoid a sharp, unnatural cutoff between the layer shape and the shadow.
- With a 0px Distance and 100% Spread, it effectively becomes an Outside Stroke without the translucency bug. Use it in conjunction with an Inside Stroke if you want a two-coloured border on an object.

## General Layer Style Advice

- Always feel free to experiment. For the most part, Layer Styles aren't particularly complicated, but they are idiosyncratic, which means that it's easy to understand them, but only after a bit of playing around.
- If you want a Layer Style to modify the existing layer contents, set Fill Opacity to 100%
- If you want a Layer Style to replace the existing layer contents (except its shape), set Fill Opacity to 0%
- You can apply Layer Styles not only to Layers, but to folders (Layer Groups) as well. Layer Styles that are applied to nested Layers and/or Layer Groups will stack.
- As with many dialog boxes in Photoshop, holding down Alt changes the Cancel button to Reset, which is useful.
- If you add a Mask to a layer with a Layer Style, you'll find that things like Stroke and Outer Glow wrap themselves around the shape of the new Layer Mask rather than just the original layer shape. To stop this behaviour, go to Blending Options: Custom and check Layer Mask Hides Effects or Vector Mask Hides Effects
- If you're going to use Layer Styles a lot, you'll probably want to assign custom hotkeys to Copy Layer Style, Paste Layer Style, and Clear Layer Style, as well as one or two individual attributes (eg. Color Overlay)
- To avoid cluttering up your Layers palette, click the top-right icon on the Layers palette, select Panel Options and uncheck Expand New Effects (I also set Thumbnail Size to None).

# A Final Note About Blend Modes
In Photoshop, any pixel that isn't 100% opaque won't have its Blend Mode honoured when flattened or exported. Note that this issue isn't unique to Layer Styles.

Take the following (somewhat ugly...sorry) example:

![ ][Blend Modes]

The shape on the left has a blue Color Overlay and a white Inner Glow and white Outer Glow. Because of the Exclusion and Difference Blend Modes, these glows appear magenta and yellow.

The shape on the right is exactly the same shape, but flattened. Notice how the Blend Mode of the Inner Glow was honoured, while the Blend Mode of the Outer Glow was not.

The Inner Glow was honoured correctly because it occurred on a 100% opaque portion of the shape, due to the Color Overlay underneath the Inner Glow.

Had the Color Overlay been 50%, the yellowness of the Inner Glow would have persisted, but only partially. Had the Color Overlay not been there at all, the Inner Glow would have suffered the same fate as the Outer Glow. Namely, it would have reverted to Normal, and thus become white.

That's it for the guide. I hope it's been useful, and happy creating! For more guides, check out the [Volblog](http://www.volnaiskra.com/volblog).

[Spryke Screenshot]: ./spryke-screenshot.jpg
[Vector Shapes]: ./vector-shapes.jpg
[Light Layer]: ./light-layer.jpg
[Diamond Layer]: ./diamond-layer.jpg
[Style Library]: ./style-library.jpg
[Ships 1]: ./ships1.jpg
[Ships 2]: ./ships2.jpg
[Building]: ./building.jpg
[Ship Variations]: ./ship-variations.jpg
[Variations]: ./variations.jpg
[Adjustments]: ./adjustments.jpg
[Pseudo 1]: ./pseudo1.jpg
[Pseudo 2]: ./pseudo2.jpg
[Pseudo 3]: ./pseudo3.jpg
[Pseudo 4]: ./pseudo4.jpg
[Pseudo 5]: ./pseudo5.jpg
[Pseudo Complete]: ./pseudo-complete.jpg
[Blend Modes]: ./blend-modes.jpg