---
layout: article
title: Reducing Visual Confusion In Your Game
author: Peter Angstadt
source: http://gamasutra.com/blogs/PeterAngstadt/20150312/238446/How_to_Reduce_Visual_Confusion_in_Your_Game.php
category: Art
priority: 3
---

Are players missing important gameplay elements on screen? Do they not see enemies until it's too late? Here’s a technique to help make your game's visuals easier to understand for the player.

Take a screenshot, desaturate it, and see if you can immediately and easily understand the image. Removing the color reveals the values, which are the light and dark shades of an image. When used properly values can indicate depth, show shape and form, and draw attention to areas you want the player to notice.

Let's look at a screenshot of DOTA 2, along with the values:

![ ][DOTA 2]

__The image is still understandable with the color removed__. The ground uses darker grays than the heroes or units, which visually separates them. Also, the heroes and units are the brightest and highest areas of contrast. While the ground has detail, its difference between it's light and dark values is small so as not to draw attention (here's some [further reading](http://media.steampowered.com/apps/dota2/workshop/Dota2CharacterArtGuide.pdf) on DOTA 2's art style).

This concept of a value analysis is borrowed from the art world. It’s one of the classic principles artists use to making a good painting and it's one more tool you can use to reduce confusion and help the player focus on what you want.

If your values are a mess, it’s time to get them organized. Let’s consider [DIGHARD](http://dighardcrisis.com/), a little hobby project my friend Max and I are making where you dig to the center of the earth and fight dinosaurs along the way.

To quickly see the values of a screenshot, we make a new layer in photoshop, move it to the top, fill it with black, and set its layer mode to Saturation. Now toggling the layer visibility also toggles the values. Here's a screenshot from earlier in development.

![ ][Dighard 1]
<cite>There's no contrast to help determine shapes, nor show the separation of the chatacter, terrain, and background</cite>

Unlike DOTA 2, DIGHARD was not understandable with the color removed. This made it harder to distinguish between the gameplay elements at a glance or when things got hectic during gameplay. The background, enemies, and the walk-able surfaces were all about the same value, the same shade of grey. The hero's silhouette is barely visible!
We spent some time to organize our values a little better. We darkened the background, increased the brightness on the walk-able surfaces, and pumped up the character’s brightness a little:

![ ][Dighard 2]
<cite>Adjusting only lights and darks brings the character out and separates the background from the terrain</cite>

There's still more work to be done, but it’s now easier to pick out the enemies and the character from the walk-able surfaces, and everything pops out better from the background.

But this doesn't mean you should go crazy with contrasting values. Too much contrast in too many places is equally confusing. Contrast draws attention, and if everything is drawing attention, nothing will.

The key idea is to come up with a __plan for organizing your values__ within the scene.

Every game organizes their values differently. For example, Limbo uses lighter values in the background and much darker values in the foreground, which is the reverse of DIGHARD and DOTA 2.

![ ][Limbo]
<cite>Light values in the back, very dark values used for gameplay elements</cite>

This is really just the tip of the iceberg for [working with values](https://www.youtube.com/watch?v=_1f7VsTILQ4#t=48). There’s a lot we can learn about guiding the player’s eye and calling attention to important elements from classical art techniques.

Make sure your game is visually readable without color using value analysis. It's simple and easy to apply even if you don't consider yourself an artist!

[DOTA 2]: ./dota2.jpg
[Dighard 1]: ./dighard1.jpg
[Dighard 2]: ./dighard2.jpg
[Limbo]: ./limbo.jpg