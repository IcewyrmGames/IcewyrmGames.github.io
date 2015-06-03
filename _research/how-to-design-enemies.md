---
layout: article
title: How to Design Enemies
author: Mike Birkhead
source: http://web.archive.org/web/20140801081037/http://www.altdev.co/2011/05/20/how-to-design-enemies-tips-from-a-combat-designer/
priority: 2
---

# Introduction
(The following is a more concise version of a three part series - [Designing Enemies: or How I Learned to Stop Worrying and Love the MvC](http://www.flarkminator.com/?p=234))

[Every](http://www.fightersgeneration.com/main.htm)
[move](http://www.youtube.com/watch?v=7xyuX7u-Xts)
[you](http://www.youtube.com/watch?v=zlPVxh-zPd8)
[can](http://www.youtube.com/watch?v=8vfVeFyZKfg)
[think](http://www.youtube.com/watch?v=Kv6RjWIETUk)
[of](http://www.youtube.com/watch?v=34vRWMdtZlk)
[has](http://www.youtube.com/watch?v=3T_RdUPNg6k)
[already](http://www.youtube.com/watch?v=e99I29695zA)
[been](http://www.youtube.com/watch?v=Z1ggc2qxCDg)
[created](http://www.youtube.com/user/CHECK4900).

It sounds ludicrous, but all of that expended effort, all of that struggle to come up with a "cool" new special move, all of that work comes to naught when you end up with something that is, at its core, derivative. That time is better spent on other areas of the game.

Designing enemies [requires research](http://www.flarkminator.com/?p=316) (such as those 10 links above), so do not be ashamed to use the ideas of other designers. It is no more offensive to use a pre-constructed library in Java, than it is to take the ideas from one game and reapply them to another. The ideas don't make the designer, execution does. But it is not enough to simply research other games. Designing enemies requires you to understand not only how to deconstruct the games you see, but also how to reconstruct those parts back into your enemies.

# Deconstruction: understanding how moves are constructed
All moves, both of the player and of the enemies, are broken down into three stages: Action, Reaction, and Result. The first two, actions and reactions, are concerned with animations, while results are about changes in state, and it is through these three stages that we control the three primary balancing dials of a move: Power, Range, and Speed.

## Action
There are countless ways that I can swing my fist, countless ways I can swing a sword, and countless ways that I can cast a spell, but all actions follow the same basic structure, and they are all balanced around the same tradeoffs. The basic structure of a move is built on three stages: Startup, Hit, and Recovery.

- __Startup__ -- The move is starting, but nothing has happened yet.
![ ][Kick1]<cite>Frame 5: Readies the kick</cite>

- __Hit__ -- The move is now "active". This is where we turn on the collision, or check hit boxes.
![ ][Kick2]<cite>Frame 8: Extends and connects</cite>

- __Recovery__ -- The move is no longer active, but I must spend time recovering back to my "rest" state before I can perform another move.
![ ][Kick3]<cite>Frame 12: Brings the leg back</cite>

It is important to understand how moves are affected by adjusting any of these three stages. The longer the startup, the easier it is to judge what move you are doing. The tighter the hit frames the harder it is to land. The longer the recovery the easier it is to punish. You can have the most powerful move in the game and I the weakest, but if my move has fewer start up frames, I will beat you all day every day. My speed defeats your power.

Power, range, and speed are the three major "dials" that you adjust when designing and balancing your moves and creatures. There are millions of ways you can attack someone, but in the end it is these three aspects that are the most important. When you talk about moves, you talk in these terms. In MvC2, for example, all enemies can be broken down into three classes: Giants, Pixies, and Projectiles. Giants defeat Pixies, which defeats Projectiles, which defeats Giants - rock paper scissors. This kind of class balance requires that you understand not only the three stages of an action, but also the reactions you cause (or don't cause).

## Reaction
When you are hit by a move, much like when you perform an action, you play an animation, and your character is locked into this reaction for a period of time. There are two basic kinds of reactions: Hits, and Guards. When guarding a hit, the type of reaction you play is not only visually different, but also shorter in length, and this distinction is very important.

Let's say I have a punch with 2 hit frames, 4 frames of Recovery, and a kick with 3 frames of Startup. The punch causes 10 frames of Hit Recovery but only 5 frames of Guard Recovery. If I attack someone with this punch (and they do not guard it), I can link my kick too get a free hit (my hit, recovery and startup is less than his hit recovery). If they guard my punch, however, he will recover before I do. This is just a simple example, but you can see the importance in understanding the difference.

![ ][AttackerRecover]
<cite>The attacker recovers first</cite>

![ ][DefenderRecover]
<cite>The defender recovers first</cite>

But that is not all. Speed, as we discussed above, defeats power, but that doesn't always have to be true. Some moves allow the player to have armor or "tank" through attacks. While tanking you take damage, but do not react. This gives you a clear advantage. Tanking is an example of a modifier that we can place on a move, and it's not the only one you can use.

- __Tank__: When hit you take damage, but do not play reactions. Sometimes a move can only tank a fixed number of hits. For example, you can tank the first hit, but if you are hit a second time you play a reaction normally.
- __Armor__: When hit you do not take damage, and anyone trying to hit you is put into a special reaction (usually as if they were just parried).
- __Invulnerable__: You take no damage and do not play reactions.
- __Guard Break__: Attempting to block a move with this attribute forces you to play a special kind of reaction. You do not take damage, but you are left vulnerable.
- __Unblockable__: Attempting to block a move with this modifier forces you to play a normal reaction as if you did not block it at all.
- __Crumple__: A special kind of reaction. Your character loses control for a period of time. Being hit while crumpled causes you to play a normal reaction. Note: THIS IS NOT THE SAME AS BEING STUNNED. When you are stunned and receive a hit, you remain stunned until a period of time has passed. The Crumple state, however, ends once you are hit.
- __Frozen__: Turned to ice, turned to stone; theme is irrelevant, the reaction is the same. You are locked down, stunned, and you cannot break free until a timer runs down.

With all of the various reactions (normal hits, guarded hits, air hits, crumples, etc.) and with the knowledge that to truly sell an attack it has to have an appropriate reaction, you can see how the workload begins to balloon when left unchecked.

## Result
The final stage, results, is when we change our character's state, and this change applies to more than just the health. Other changes in state range from altering your current armor rating, to altering whether you are considered on the ground or in the air.

### Health
- __Damage__: A fixed reduction in health. The amount of damage done is scaled by two factors: the opponents armor class, and the current combo count.
- __Poison__: A fixed reduction in health over time.
- __Heal__: A fixed increase in health
- __Regen__: A fixed increase in health over time
- __Drain__: Reduces health from one person, healing someone else for some fraction of damage done.

### Defense
- __Defense__: Increases or decreases the amount of damage scaled by your defense.
- __Tank__: I can tank X number of hits
- __Armor__: I have armor for a certain period of time. (Not the same as tanking).
- __Increase__: Making one character move faster than another is a simple to understand, if complex to implement, example of this concept, but a better illustration is to consider what happens if we reduce the number of startup frames a character plays.
- __Decrease__: Much the same, but in reverse. I could increase the length of my opponents recovery, giving me a major advantage.

### Position
- __Impulse__: Not all moves shove you across the screen, some suck you in. Impulse is the generic attribute, applied programmatically, of how much (both positive or negative) something shoves you.
- __Launch__: Knocking an enemy into the air places him into a completely new state. The game must understand not only that he acts differently, but also that he reacts differently. There are a whole new set of reactions to play when you are in the air; remember what I said about your workload ballooning when you don't pay attention?

Results are easy to grasp and fun to think about, but do not get carried away. Their simplicity in concept belies their complexity of implementation. For every system you wish to modulate, the programmers must expend time and effort making that system variable instead of fixed. Pick your battles carefully.

# Reconstruction: choosing what moves to give to your enemies
Deconstructing moves is only half of the job. The preceding knowledge allows us to break down what we see in other games, but now we need to take the myriad of moves out there and apply them to our cast in a way that is fun for the player. The primary goal of Action Adventure games is Accomplishment. We want our players to feel that they have accomplished great things, and for us, the combat designers, this requires a depth of player and a breadth of cast. Note: this breadth in play comes from the cast as a whole, and not the individual enemies. The monsters are not there to play mind games with the player; they are there to make her feel like a bad ass. Players want to smash faces. If they want subtlety, they will play a fighting game. A game which is DESIGNED for mind games, and they will play it with real people who are infinitely trickier than a computer. This does not mean that your enemies cannot be tricky - they can and should have a trick. That is trick, in the singular. The player learns the monster's trick, and, once overcome, gives her a sense of accomplishment. She is getting stronger and better than her adversaries.

So if you want player's feeling accomplished and not asking what idiot ruined their night, there are three things to keep in mind. First, you must always keep in the mind the Roles your cast must fill. Second, you must Classify your enemies in a balanced manner. Third, you must find your Trick.

## Roles
The first major task in designing enemies is to determine the roles they will fill. These roles are defined by the mechanics of your player, so if you do not know your player, then it will be very hard to know our enemies. This does not mean, however, that you forgo designing enemies until your player is complete. Instead, the two processes are designed in concert. When one changes, so does the other, and you should be in constant communication with whomever is designing the player. There are four major roles your enemies must fill: Emphasizers, Enforcers, Smashers and Challengers.

### Emphasizers
Emphasizers should, when striving for mass market appeal, make up the majority of your cast. An emphasizer is a creature that rewards, not requires, the use of one specific mechanic. The key is to have positive reinforcement. The player is not penalized for using the wrong method; she is simply rewarded for doing it the "correct" way. Emphasis rewards experimentation, while requirements brutally teach. The former flows naturally, and over time the player discovers the best course of action. The latter brings the game to a screeching halt, while the player must deign the correct solution. There are times when you should enforce a mechanic, and those times are when you want to teach your player something core to the game.

### Enforcers
The majority of your cast should be emphasizers, but they do have a downside. By allowing for multiple killing solutions they lack the ability to forcibly teach the player. Sometimes, you have a mechanic that is so core to your design that a player must learn it. Enter the enforcers. These creatures require a mechanic from a player, and without the player using it, they will not progress. Enforcers have their place, but their place should be rare. Use this only when something MUST be taught to the player, and do so with as much obvious flair as possible; this is not a time to be subtle. Subtly and enforcers do not mix well, and if handled poorly can quickly become frustrating.

![ ][Roles]
<cite>A selection of enemies from Chains of Olympus expressed in terms of Class and Role</cite>

### Challengers
These are the bosses, the difficult enemies, the ones you use all of the tools in your toolbox to defeat. Challengers are separated from your emphasizers and enforcers due to their complexity of design and cost to implement. Where most enemies in your cast have their one or at most two attacks, a challenger has three or four. Remember, the more attacks you give an enemy the more it can play mind games with the player, and mind games are dangerous. Catching a player off guard and providing a greater challenge, if handled well, can spice up the game and drive the player to break through to a new level of mastery. More often, however, they are a hell of frustrating and repeated deaths to overly cheap tactics that follow no pattern and offer no accomplishment.

### Smashers
Providing the player with challenges is important, but sometimes you just want to destroy something - a lot of somethings. Smashers are the smaller, weaker and easily dispatched enemies that you throw at the player, sometimes alone, but most times accompanying other enemies, and they let you get your smash on. Remember our number one goal in these games is to give the player a sense of accomplishment, and letting your mass murderer out of the bag every once in a while feels really good.

Where Challengers strive for difficulty, Smashers strive for simplicity, and this simplicity should be applied not only to their difficulty, but also to their implementation. The Smashers serve a secondary function. By making them lightweight in terms of Ai, poly count, texture size, and basic memory footprint, you can sprinkle these enemies liberally across the game, without having a major impact on your level designs, and we all know how important that is when memory becomes tight.

## Classes
Roles are important, but they are not enough if we want to have a balanced cast that is diverse in play. For that we need to group our creatures by additional criteria.  A balanced cast is one diverse in style, complexity, and mechanic. In the old days, it was as simple and clean as a "skinny", "medium", and "fat" hockey player, but now balance has a more textured meaning. In God of War they break enemies down into several classes, which ensures clarity in discussion, ensures designers (and others) visualize their workload, and ensures there is a properly distributed variation in play. Classes range from "Pests" which contains all of the lightweight annoying enemies, all the way to "Bosses" which, obviously, tracks the bosses.

![ ][Ice Hockey]
<cite>Ice Hockey for the NES</cite>

Clear and distinct classes are necessary for meaningful discussion. Why spend time and effort describing a monster's [presence](http://www.flarkminator.com/?p=189) when you could say he's of class (to borrow the term) "Pests", which starts you both on a mutual foundation. To reach this understanding requires your design department be both vigorous and consistent. If you are lazy, forgetful, or inconsistent, you will seriously harm communication. The rewards, however, outweigh the dangers, as enforcing this lets other departments quickly understand not only what you want, but also how much work it creates (or saves if it's cut). Visualizing your workload, while important in the beginning, is just as critical near the end when things are being cut. Your cuts need to save time and they need to leave the game without a gap in its play.

Roles and Classes, while appearing redundant, serve two distinct goals for the game. Roles are defined by the player, while Classes are primarily defined by workload and difficulty. The mechanics of your player demands enemies that work well against and with him, but only viewing your cast through that particular lens leads you to end up with lots of "clever" enemies that lack a cohesive feel. The ultimate goal is a diverse cast, and having Classes not only helps to ensure visual diversity, but also helps to visualize the workload you are creating.

## Tricks
Everything must serve a purpose. If you cannot explain to me why a creature must exist - [in less than three sentences](http://www.flarkminator.com/?p=312) - then it's a safe bet the player is not going to enjoy killing it. Lacking purpose reduces your creatures, effectively, into very fancy destructible objects. A [great designer I know](http://pushing-buttons.blogspot.com/) always asks, "What's this guy's trick?" And the question has stuck with me. It's a great question to ask of your enemies. A trick implies that you can fool me, but once I know your trick it loses its effectiveness. Being fooled keeps you on your toes, while providing you with the opportunity to learn and grow as a player, which leads to our ultimate goal of accomplishment.

# Closing
Designing enemies is seriously the most fun and most challenging task you can have making games. It challenges you as a designer in the two best ways: nailing the science, and nailing the feel. What I have expressed here is a structure - the science, if you will. It is meant to help you on the path, but never forget the importance of feel. The science can only take you so far, and that was one of the hardest lessons I had to learn when I started. Sometimes, you just need to put down the calculator and play the game.

And if you choose to take away only one thing from this post, let it be this: [ideas are meaningless](http://www.flarkminator.com/?p=260), execution is everything. Every move you can think of has already been created, and mining their ideas doesn't make you a bad designer. Believe it or not, taking that idea and executing it to the same (if not higher) quality is harder than you can ever imagine, so if you are smart, you will choose to devote all your limited time and dwindling energy to executing to the fullest of your extent. Go, mine, study what they have done, and show everyone how well you can execute.

[Kick1]: ./Kick1.jpg
[Kick2]: ./Kick2.jpg
[Kick3]: ./Kick3.jpg
[AttackerRecover]: ./AttackerRecover.jpg
[DefenderRecover]: ./DefenderRecover.jpg
[Roles]: ./Roles.jpg
[Ice Hockey]: ./IceHockey.jpg