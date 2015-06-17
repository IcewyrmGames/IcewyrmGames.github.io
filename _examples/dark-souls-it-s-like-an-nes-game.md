---
layout: article
title: "Dark Souls: It's Like An NES Game!"
author: James Margaris
source: http://www.gamasutra.com/blogs/JamesMargaris/20150505/242687/Dark_Souls_Its_like_an_NES_Game.php
---

# About This Series
This blog is inspired by Matt Zoller Seitz's [Please, Critics, Write About the Filmmaking](http://www.rogerebert.com/mzs/please-critics-write-about-the-filmmaking), the gist of which is that critics, rather than writing solely about how a film made them feel, should examine how the film made them feel that way. Sietz calls this the "form" of the film, a term I'll use here, though I have little interest in "formalism."

It's hard to find good writing on design. It's hard to find writing on design, period, from either critics or developers. (It sure is easy to find "think pieces" though!) My goal is to write about the design of games - the specific decisions that were made for an individual game that make the game what it is.

I'm starting with Dark Souls for a few reasons. Most importantly I feel like it. Another reason is that Dark Souls is a game most people are familiar with and perhaps have read other writing about. I'll try not to be too duplicative of previous writing. Hopefully you'll appreciate this analysis, even if you're familiar with prior work.

# It's Like an NES Game!

![ ][Iron Sword]
![ ][Dark Souls]
<cite>Above: Dark Souls and I can't Believe it's Not Dark Souls</cite>

This is something that gets thrown around a lot regarding Dark Souls. I never paid much attention to it - it's just something people say. (The same sort of people who think any game with pixel art is "8-bit") But when my friend who grew up on games like Castlevania 2, Rygar and Battle of Olympus said that I paid attention. The game made him feel the way NES games did. There's a lot to talk about with the design of Dark Souls so this is my angle: what are the specific design decisions that make it feel like an NES game? (Or alternately: unlike a modern game)

![ ][Bloodborne]

# Easy Stuff Out of the Way
Recently on my Twitter feed was a picture of Bloodborne (Souls successor) with text along the lines of "Bloodborne as a Western AAA game." It has about what you would expect - onscreen tutorial text, a quest log with "Rats killed:7/10", a minimap, etc. I'm going to quickly dispense with the easy stuff of how Dark Souls is like an NES game and unlike a modern one: The game is obtuse, lacks ease-of-use features like on-screen aids or exclamation marks over heads. It expects the player to fail, perhaps forever, and does little to ensure that they can tour all the content in timely fashion by way of lower difficulty or breadcrumb quests, which makes exploration and progress feel like an achievement by the player rather than an inevitability. These observations are valid but also trivial, so this section is done.

# Combat: Direct User Control
Dark Souls is "What You Do is What You Get" - each button maps to a well-defined action.

For comparison take a game from the Batman series. Once you reach a few hits on the combo meter Batman goes into badass Batman mode and the combat verbs change - whereas pressing attack may have previously done a single weak punch now Batman leaps at an enemy and does a flying knee, knocking them over. The input here is the same as it was before - the player isn't doing anything different, it's that Batman has decided to step up his game. (Batman only does cool effective moves once he's pumped himself up enough apparently) To leap towards an enemy you press the stick vaguely in the direction of an enemy and Batman attacks one - when enemies are clumped together which one Batman attacks feels arbitrary. Batman also rarely if ever leaps and misses - he never buffoonishly attacks empty air in a decidedly non-Batman way. Which move Batman does is also largely up to him - sometimes he does a flying knee, sometimes he does a jump spinning kick. The jump spinning kick feels slower - if an enemy is charging to attack and you attack to beat them to the punch whether you succeed seems to depend on which move Batman decides to do. (Without looking at frame data I can't say for certain that some attacks are slower, but they certainly feel slower.)

Batman is a game of indirect control. You suggest an action to Batman and he does it in a sufficiently cool and Batman-like way. Dark Souls is uninterested in making you look cool - if you want to look cool that's entirely up to you. What move you do is determined entirely by your inputs and the state of the game (more on this later), without any discretion from the character.

Bayonetta is a game with more direct control than Batman, focused more heavily on the technical aspects of fighting, but it still has aggressive aim-direction assist. If you attack an enemy at an awkward off angle your character will turn to face the enemy. In Dark Souls you'll just swing and miss.

Dark Souls is often lauded as tough but fair - direct control is an important element of that fairness. The character never chooses the wrong move or faces the wrong way - it's always the player that's to blame. Direct control also allows for more advanced positioning tactics - because there's no auto-facing you can start up a slow attack directed at empty space, predicting that an enemy will move into that space. You can attack body parts like tails, exactly choosing a position that allows you to hit the tail while avoiding incoming attacks, rather than the game forcing you to attack towards the center of mass and making it impossible to attack far-flung appendages without positioning such that the appendage is between you and that center of mass.

It should go without saying how Dark Souls is like NES games in these respects, but I'll say it anyway: most NES games had little to no fix-ups and featured direct control. The idea that player input is a suggestion for the character to interpret became widespread only recently. (Most notably in Assassin's Creed)

# Combat: Range and Positioning
![ ][Bayonetta]
<cite>Above: Bayonetta deftly dodging an attack from a self-styled cultural critic. (It's a metaphor!)</cite>

In many modern combat-centric games range and positioning are fairly unimportant. Most close-combat games feature an invincible dodge or a counter that is used reactively rather than making attacks miss by being to the side or out of range. Dark Souls does feature a roll but it has limited invincibility. Which direction you roll often matters as much or more than the invincibility frames, whereas it rarely matters in a game like Bayonetta or God of War. Dark Souls features a parry but the parry is much less forgiving than the counters in other close-combat games and works on a lower percentage of attacks.

Combat in NES games tends to be positional, with geometric precision required to avoid enemies. In most NES games avoiding attacks consists of being in the right spot in 2D space - running under a Koopa Paratroopa, jumping over a Bullet Bill, standing between Dracula's pillars of flame. It's hard to think of many NES games that feature reactive dodges or counters that work in any place on-screen. Spatial positioning, rather than dodges or counters, is at the heart of many NES games and at the heart of Dark Souls combat.

# Combat: A Sequence of Discrete Actions
Dark Souls combat has few combos and, more generally speaking, few stateful elements. Backstab is available if you're behind an enemy and and the post-parry hit is available after you parry. (In DS2) That's about it. The combo system is basic and more reminiscent of games like Final Fight than modern combo-centric games, and combo length is naturally limited by stamina.

In Bayonetta a non-repetitive combat sequence looks like this: "stinger" forward to close distance and hit an enemy, punch punch kick kick (this kick launches an enemy), immediately jump and kick to do the upwards red hot kick, as you come out of the kick punch punch punch kick kick, jump+kick to do a second red hot kick (this one counts as you jumping off of the enemy), punch punch punch kick kick, jump+kick to to a third red hot kick (this one counts as your second jump, as jumping off an enemy doesn't count as a jump) punch punch punch kick kick kick, (this knocks the enemy towards the ground), land, foot stomp. If this sounds complicated - well I didn't factor in transforming into a bat in mid-air, various other ways to extend combos on the air or in the ground, holding down buttons for continuous fire, etc. Many of the actions above rely on state - the only reason the second kick in the grounded sequence launches is because the previous 3 inputs left us in that state. The optimal way to play modern combat-centric games is to become a human meat-grinder - to mercilessly pummel enemies with long strings of attacks pausing only to reactively dodge or counter. In Bayonetta even dodging doesn't reset state - instead "dodge offset" allows you to continue your combo even after you dodge.

By comparison here is a typical non-repetitive Dark Souls combat sequence: weak attack, weak attack. Then you're back to a neutral state from which you can attack again, roll, position, etc.

In this way Dark Souls combat is similar to the combat in NES classics like Ninja Gaiden. In Ninja Gaiden you can slash, you can jump and slash, and you can duck and slash. There is no air juggling, no combos. You just slash, then maybe slash again. Combat in both games is series of single, discrete, stateless actions.

# Loot
To the best of my knowledge in Dark Souls players who are doing poorly aren't aided by the invisible hand of the designer - for example by being given extra health from defeated enemies if they're stuck for a while. (In fact in Dark Souls 1 there are no health drops period) Dynamic difficulty adjust appears to be entirely absent. Similarly loot tables are not adjusted to take the player into account. In many modern games if you open a chest as a level 40 Archer the loot inside will be weighted to be something relevant to a level 40 Archer. This is such a common expectation that reviewers will lament the existence of random loot tables. (To be fair those random loot tables sometimes exist in games that otherwise cater to the players, and thus are out of step with the game's larger design philosophy) In Dark Souls the loot tables on enemies are fixed, and the loot in chests and lootable objects are entirely predictable and not based on tables at all. This is also, of course, common for NES games - if a bad player plays Super Mario Brothers they aren't gifted extra mushrooms.

# Detective Vision: There Isn't Any
![ ][Tomb Raider]
![ ][Batman]
![ ][Last of Us]
<cite>Why don't you just show me the underlying structure of the game I'm playing?</cite>

Batman has Detective Vision - a special vision that allows him to see into people's bodies and through walls with a combination of training, senses, gadgets and nonsense. Lara Croft has Instinct Vision - a seemingly magical ability scientifically explained by her high midichlorian count. Fantasy Guy in LOTR has Wraith Vision. (This one has an actual justification so I have nothing clever to say about it) In Enslaved interactive objects glow, in Mirror's Edge Faith has "Runner Vision." In The Last of Us Joel has sonar sense. (This one is also justifiable, in the comic book series we learn that Joel was bitten by a radioactive bat while working for Oscorp)

Part of the reason these systems exist is no doubt the "me too" nature of game development, but they also solve a real problem - in games that prioritize visual fidelity the underlying game logic can be unclear. These modes exist to show players what the game is about minus the visual clutter.

In the NES days most game logic was clear - objects on screen usually served a purpose, due less to philosophical adherence to Checkov's Gun reasoning than to hardware limitations. Games were usually laid out on grids, so judging height and distance was easy. Background elements were desaturated, less detailed, or simply a solid color. The visuals of the game were a representation of the game rules, rather than a stab at realism or fidelity for the sake of.

In modern games it's common for invisible walls to block off areas that should logically be accessible. For doors to exist that can't be opened. For geometry with no physics to decorate the landscape. Dark Souls takes the opposite approach - much like how Dark Souls' combat is "What You Do is What You Get" Dark Souls' layout is "What You See is What You Get." If there's a door you can probably open it if you have the right key. If there's a ledge you can probably jump to it, even if it looks like the sort of ledge that wouldn't have physics data in other games. Traversing Anor Londo requires that the player unlearn internalized lessons of which game objects in a world are relevant and which are for graphical show, to walk on small, off-angle ledges that look to be purely art elements rather than game structural ones.

In Dark Souls gameplay fidelity take priority over graphical fidelity. The same is true of animation fidelity. Many modern games prevent the player from fighting enemies on uneven surfaces like ramps and stairs, because specialized animations require player and enemy to be approximately level. In Batman a reason nearly all boss fights are either gimmick battles or versus groups of thugs is (I assume) that the Batman combat system relies on animations that work only against same-sized humanoid opponents. None of the cool animations Batman does, like jumping and kneeing a guy in the jaw, would work against a very tall guy. In Dark Souls it's common to fight on stairs, on ramps, in thin corridors, against enemies of different shapes and sizes - very few of the animations rely on Player Part A hitting Enemy Part B (just backstabs), and if fighting on stairs looks a bit wonky the designers have decided to just go with it. There's very little concession to removing "jank" in favor of more "realistic" or purely artistic presentation.

# Traversal: There Isn't Any Of This Either
![ ][God of War]
<cite>Hey, at least it's not a turret sequence or a hacking minigame</cite>

We've reached what I think is the primary reason Dark Souls is "like an NES game." Modern design ethos for action/adventure games is that they are broken into 3 distinct parts - combat, traversal and exploration. (The latter two sometimes combined) You fight in an arena against waves of enemies, then you climb up some stuff or trundle through some corridors, then you listen to an audio log or read some graffiti. Then repeat. (Remember when "environmental storytelling" seemed exciting?) These different parts are often distinct already, but many games use music cues to further delineate them, letting you know when enemies are approaching or have been dispatched.

In the typical NES game the challenge comes from the combination of enemies and level. Levels had environmental hazards like pits, spikes and lava, and occasional devoted traversal sections like the disappearing block bits in Mega Man, but it was rare for a significant stretch of time to feature traversal without enemies. Arena-style combat was also relatively rare in NES games, usually reserved for bosses and mini-bosses, mid-stage set-pieces, etc. Few NES games required the player to defeat regular enemies - in most games you could simply run past them. They often functioned more like a type of environmental hazard than an enemy, with simple patterns and limited AI. (This is very clear in a game like Metroid) The formula for NES games was taking simple enemies and simple level design elements and combining them to provide novel, increasing challenge. There's nothing threatening about a Goomba on flat ground or a pit you can fall into, but if you place a Goomba right past a pit now you're cooking.

NES games often lacked dedicated traversal verbs or traversal that was mutually exclusive with combat. In Super Mario Brothers you traverse by jumping - that's also how you attack and dodge. There's no dedicated traversal mode (I'll ignore water levels) in which the buttons do something different than they normally do.

Modern games are a very different story. In a realistic presentation normal humans jumping 25 feet onto floating platforms looks a little odd. So in the service of fidelity and realism in modern games traversal is about climbing nets and ropes, sliding down things, clinging to ledges, playing elaborate "hoisting yourself up" animations, etc.

When you jump onto a ledge your hands are free. When you climb up a ledge your hands are occupied. As such modern games with traversal usually lock out normal combat during traversal sections. In God of War while your feet are planted you have access to an elaborate combo system; when you're climbing a net you have access to two attacks, one of which is basically useless compared to the other and neither of which is at all satisfying to use. While traversing a rope you can kick people or grab them and toss them off, with a system that has none of the depth or fun of standard combat. In some games you can't attack at all while traversing, while in others you can but the action is perfunctory.

In Dark Souls there's no dedicated traversal action besides using ladders, which is infrequent. Beyond that traversing is just walking / running / falling / jumping, not context-sensitive animations or a different verb set. While there is navigation and exploration there isn't much traversal in the modern sense. Similarly there are few enemies you're required to defeat and few arena battles. Eschewing arena-style layouts, Dark Souls combat areas are not distinct from traversal areas - combat takes place in all sorts of differently-shaped environments as you wander through them.

The first time you encounter a Black Knight in Dark Souls it's likely the one in Undead Burg. You can walk right by if you want. If you choose to fight the fight is awkward, taking place in a narrow corridor with no room to dodge. If you lure it out beyond that there are stairs, and beyond that a small area with a rooftop. If you want to lure the Black Knight to an open combat space you have to travel quite far, past nearest bonfire. (I'm not sure if it will even follow you that far) Similarly, the second Black Knight (in Undead Parish I believe) is on a small circular landing at the top of a spiral staircase. Fighting here is just as awkward - the space is small and you can fall onto the stairs. If you try to lead the Knight into an open space you hit either a dead end or a room full of enemies.

At the end of the game you fight a variety of Black Knights again. This time you fight them one at a time in open space. It's not hard. (Even Jeff Green had more trouble falling off the stairs leading up to the enemies than fighting them) It's almost as if the point of this section is to reveal to the player the trick that's been played on them - that the difficulty of Black Knights was always an illusion. Their patterns aren't complicated, they aren't clever or particularly fast. They were hard only because you were scared, because they surprised you and ran up to you while you were walking along a narrow ledge, set upon you right after you dropped down into a small room, or chased you around while other enemies fired arrows at you. At the end of the game they're just Goombas in open space. They only functioned as competent enemies in the context of other enemies and an environmental layout that played to their strengths. (If only we could fight the Capra Demon again in a large arena instead of a studio apartment)

More than anything, the reason Dark Souls is "like an NES game" is not due to difficulty or any particular mechanic - it's that the rhythm and layout of the game, what you do and the verbs you use, the philosophy of level design and enemy placement, is like an NES game. It's level layout and enemies working in tandem to create a continuous experience.

# But Is It Good?
So far I've said very little about whether or not these design decisions are good. Now I will, with a bit of a caveat: I don't believe that context-free "good design" is a real thing.

Coherent design is important - how well do design decisions work in the context of other design decisions? Form matching theme is important - how much does the design support the theme and content? I would go as far as to say that form and content are inseparable in gaming - form isn't just a vehicle to convey content, it is content. (Note again: I have no interest in "formalism", I'm just using the word "form" here)

You can decide for yourself if the design of Dark Souls is good or not. Instead I'll talk about how the design of Dark Souls is coherent.

The world of Dark Souls is unfriendly and indifferent to the player in theme. It is also so in mechanics. A game with an unfriendly world but with a designer that bends over backwards to aid the player can destroy the illusion - that's a game with no teeth playing at being a game with teeth. Dark Souls has teeth, in theme and mechanics.

If you kill an enemy that uses a giant axe they drop a giant axe, even if you're a magic user who lacks the strength to wield an axe. Upon dying the enemy doesn't quickly swap out their axe for a staff to make your journey more pleasant. Dark Souls is not about respecting your time by ensuring a regular pacing of satisfying, semi-random rewards - it's about respecting your ability to persevere in a harsh world.

The game is hard, but that's balanced by the player being in control. In Dark Souls the designer doesn't help you face the correct direction when you swing your sword or adjust it to hit a monster's face that's out of reach above you. If you were facing the wrong way and whiff or your weapon bounces off a wall that's on you. But at the same time your character will never do a side-to-side swing when you wanted an overhead one. There are no Assassin's Creed situations where you want to run up a wall but your character decides to jump into a hole instead. (To be fair Bed of Chaos is kind of like that, but due to wonky but predictable jump physics rather than your character independently deciding to do something silly). You have the responsibility to pull yourself up by your bootstraps, but you also have the tools to do that. Dark Souls gives you a manual transmission - harder to use than an automatic but more powerful with mastery. Or, in slightly different terms, it's like a racing game with all the assists turned off.

There is no separate traversal mode, no part of the game where combat is locked out in favor of context-sensitive navigation verbs. At every point in the game you have your full combat repertoire available, which means that at any point in the game you can expect to run into enemies. The only solace is at bonfires, which serves to make bonfires focal to the game, both thematically and mechanically. Fire is safety. Fire is life. That's the fiction of the game and the mechanics.

# Classic Trite Full Circle Conclusion
Dark Souls is like an NES game, sure. But many games are "like NES games", and many are much more superficially similar. Dark Souls isn't a nostalgic aping of the NES era - throw in some "chiptune" music and some "pixel-art" graphics and claim to have throwback sensibilities. Dark Souls doesn't have a throwback aesthetic, it has a throwback design aesthetic. It exists on a largely unexplored alternate evolutionary path that rejects much of what has become conventional design wisdom. It demonstrates NES-era priorities and design philosophy.

At the start I referenced the piece Please, Critics, Write About the Filmmaking. Dark Souls gives some players the warm, familiar feeling of an NES game. I hope I've explored how it does that in an elucidating way - the specific design decisions that contribute to that feeling, beyond superficial similarities like the absence of quests or being "NES hard."

[Iron Sword]: ./iron-sword.jpg
[Dark Souls]: ./dark-souls.jpg
[Bloodborne]: ./bloodborne.jpg
[Bayonetta]: ./bayonetta.jpg
[Tomb Raider]: ./tomb-raider.jpg
[Batman]: ./batman.jpg
[Last of Us]: ./last-of-us.jpg
[God of War]: ./god-of-war.jpg