---
layout: article
title: RPG Battle Systems Part 2
author: Craig Stern (Sinister Design)
source: http://sinisterdesign.net/12-ways-to-improve-turn-based-rpg-combat-systems/
category: Mechanics
priority: 3
---

# Introduction
In [my last opinion piece](http://sinisterdesign.net/?p=889), I provoked a certain subsection of the world of RPG enthusiasts by slaughtering a particularly sacred cow: the D&D-style combat system. A surprising number of people wrote in agreeing with me. Predictably, however, others responded in one of two ways: (1) “So you think a real-time, action-centered combat system is better?” or (2) “Name an RPG combat system that’s better!”

The answer to (1) is easy. No, [I don’t think real-time is better](http://sinisterdesign.net/?p=830). Just the opposite: I prefer turn-based combat in my RPGs. Of the six games I’ve released since I started designing games, five use turn-based combat, and I’m working on two more with turn-based tactical combat for good measure. That should probably tell you something about my tastes.

The answer to (2) is more complicated. I don’t think that there is just one way to do a turn-based RPG combat system correctly. I’ll avoid naming particular games, since I don’t want to give the impression that all RPGs should employ combat in the style of any one particular game. I will, however, discuss the features that good turn-based tactical combat systems have in common, and cite games that successfully employ them.

# The Four Virtues of a good tactical turn-based combat system
If you’ve read my last article, this list is going to look familiar. A good tactical turn-based combat system exemplifies the following Four Virtues:

1. __Emergent complexity.__ It creates complex gameplay out of a comparatively simple set of rules.
2. __Clarity.__ The immediate consequences of various tactical decisions are made clear to the player.
3. __Determinism.__ The system is sufficiently deterministic that skilled play using a proper strategy will nearly always result in victory.
4. __Tactical tools.__ If there is some randomness in the system (which there will be in most cases), the player has sufficient tactical tools at her disposal so that skilled play will almost always trump bad luck.

The Four Virtues of a good tactical turn-based combat system are closely interconnected: with a handful of simple rules, a turn-based combat system can exponentially increase its [tactical possibility space](http://books.google.com/books?id=yiOtN_kDJZgC&lpg=PT252&ots=fhemZN8RVt&dq=%22possibility%20space%22%20in%20chess&pg=PT252#v=onepage&q=%22possibility%20space%22%20in%20chess&f=false), thereby achieving the goals of both emergent complexity and skill-based outcomes to battles.

Clarity, in turn, arises organically if you do this properly: which is to say, if you don’t achieve complexity by overloading your combat system with arcane rules, the player should quickly be able to understand exactly how her actions will play out in combat, allowing her to plan ahead and strategize. (Clarity also depends upon [good interface design](http://wilbefast.com/2011/05/27/the-importance-of-interfaces/) and appropriate visual cues to the player, but those things are basic to good game design in general, and aren’t worth discussing here.)

So let’s get specific. There is a veritable cornucopia of techniques that game developers have used in the past to make their turn-based combat systems sparkle with tactical possibilities, and I want to see new RPGs start using them with greater regularity.

# Ways to Improve RPG Battle Systems

## Use space.
Adding a spatial dimension to combat increases its complexity exponentially without making it substantially harder for the player to understand. Most people have played  games like Candyland or Monopoly, to say nothing of Checkers and Chess. Everyone (even your mom) intuitively understands the concept of moving pieces between spaces.

By using space in your battles, you add a new dimension to combat both figuratively and literally: the concept of attack range comes into play, and the player gains direct control of actions like fleeing and protecting weaker characters behind stronger ones.

Of course, you aren’t required to have a grid-based (or hex-based) map with movable characters to create a good tactical combat system, but it’s an awfully effective way to introduce complexity using simple rules. This alone will put your game far ahead of most jRPG combat systems.

Then again, spatial combat is not exactly a huge achievement: virtually every western RPG has this in one form or another. Let’s be a little ambitious. Here are 11 other techniques for achieving the Four Virtues that have been consistently overlooked not just in jRPGs, but in western RPGs as well.

## Give the player at least six characters
This one is absolutely key, and yet most western RPGs of the past 20 years have missed it. Imagine playing chess with only four pieces–you’d be looking at a game with greatly reduced tactical complexity and far less interesting matches.

Putting more characters under the player’s control pays great dividends in terms of tactics. More characters means that the player can be expected to handle much more involved combat scenarios, and becomes responsible for keeping more characters alive. This naturally gives rise to dilemmas about how to balance multiple objectives with minimal losses, which in turn make combat more interesting.

Also, with more characters under the player’s control, each individual character can be much more specialized. Speaking of which…

## Specialize the characters
How dull would chess be if it were played entirely with knights, or bishops? Make sure characters of different classes serve different battlefield roles; don’t just make them all fighters with different hit points, armor and spells.

If you differentiate your classes successfully, your player will have to think carefully about which characters should perform which actions during battle. The Fire Emblem series, especially, [does a great job](http://fireemblem.wikia.com/wiki/Category:Classes) with this.

## Specialize the enemies
This should be obvious: if every enemy is a melee bruiser with magical attacks, your player has no reason to prioritize one enemy over the others. Give enemies distinctly different capabilities, weaknesses, and battlefield roles.

## Variable distance
Do not always begin battles with enemies 1 turn or less away from melee range! Spacing them out a little will give the player more flexibility to try out ranged tactics, as well as pressuring the player take cover from or flank enemy ranged units.

## Directional facing
Make it so that characters are easier to hit and/or suffer additional damage when attacked from behind or the sides. Doing so amplifies the importance of positioning in close quarters, adding another wrinkle to the player’s considerations. It also has a side effect of making faster-moving characters more dangerous, as well as increasing the effectiveness of flanking and [pincer movements](http://en.wikipedia.org/wiki/Pincer_movement).

## Variable terrain
Used properly, terrain can add new dimensions to player considerations about character positioning, creating natural choke points on the battlefield, providing cover, or even providing bonuses or penalties to the characters who stand on it ([Advance Wars](http://en.wikipedia.org/wiki/Advance_Wars#Terrain) and the [Disgaea](http://disgaea.wikia.com/wiki/Geo_Panel) games serve as excellent examples of the latter).

Terrain can also serve as a point of character specialization, with certain classes performing better on certain squares (or being uniquely able to move through them).

## Manipulable terrain
But why stop there? Let the player actually manipulate terrain during the battle. Temporary terrain creation occasionally appears in western RPGs in the form of walls of fire, walls of ice, and traps that players can place to form barriers or choke points. Destructible terrain in RPGs is rare, however, and most created terrain lasts for only a short duration.

We can do better than that. Give the player meaningful flexibility to shape the battlefield, creating new avenues of attack and closing off existing ones. This will cause your combat system to accommodate more creative tactical thinking. The player won’t just be thinking about how to place her characters to best make use of the environment: she’ll also be thinking about how to change the environment itself to create those opportunities in the first place.

## Resource management
This appears in nearly all western RPGs to a limited extent, mostly in the form of budgeting gold, conserving magic points and hoarding scrolls and potions. However, this standard RPG implementation of resource management isn’t usually too important at the combat level–it’s typically a broader challenge spanning a whole foray into a given area.

To liven up particular combat encounters, use a system that requires players to balance more powerful attacks against other priorities on a turn-by-turn basis. Action Point systems (e.g. the kind used in [X-Com: UFO Defense](http://www.ufopaedia.org/index.php?title=Time_Units) and the first two [Fallouts](http://fallout.wikia.com/wiki/Action_points)) are great for this, forcing the player to weigh a variety of factors all at once when deciding on character actions. Also good are systems where most powerful abilities use large amounts of magic points, but magic points regenerate over time (e.g. [Tactics Ogre: Let us Cling Together](http://videogamegeek.com/thread/560222/some-thoughts-on-tactics-ogre-let-us-cling-toge)).

## Give units multiple attack options
This dovetails nicely with resource management: giving each character the option of more effective but more expensive or risky attacks expands the player’s tactical options greatly. Should the player pin her hopes on her character landing a more powerful blow, or should she have him get in a quick jab and leave some resources for the character to defend himself afterwards?

These sorts of small-scale dilemmas are the bread and butter of a satisfying tactical combat system. (Fallout and Fallout 2 provide [a great example](http://fallout.wikia.com/wiki/Aimed_Shot) of how to use this technique.)

## Support multiple objectives
I mean this not just in the sense that your combat system should challenge the player with different win and loss conditions; I mean this in the sense that multiple different objectives (not of the win/loss variety) should be  able to coexist within any given battle in your combat system.

This is a simple extension of the idea that a good RPG should have choices with consequences: there should be post-battle consequences for what happens during battles as well. Did she hit a town guard with a misguided arrow? Make it so the player is wanted for assault. Did she successfully protect the manor of the richest man in town? Make the rich NPC give the player a reward after the battle.

Aside from the obvious benefits such a feature creates for immersion, it also creates a richer tactical experience for the player. The goal becomes not just to win–the goal becomes to win while accomplishing as many side objectives as possible.

Because of the effort involved in setting up custom objectives for each battle, you might instead choose to set up your combat system with persistent side objectives such as maintaining character morale ([X-Com](http://www.ufopaedia.org/index.php?title=Agents_Stats_%28Apocalypse%29#Morale.2FBravery)) or gathering certain resources that can only be gathered during battle (treasure chests in Fire Emblem, captured majin in [Eternal Poison](http://www.gamerstemple.com/vgguide.asp?g=4756&i=1)).

In [Telepath RPG: Servants of God](http://telepath.wikia.com/wiki/Soul_Charge), for instance, slain characters can only be resurrected through the use of soul charges, which in turn can only be obtained by using one character’s Soul Suck ability on a critically injured enemy during combat. The player is forced to periodically use the character who can Soul Suck in order to maintain a supply of soul charges; and within particular battles, she must weigh the risk of keeping an enemy alive long enough to harvest it against the reward of having a one-shot chance to raise a slain character later on.

## Allow delayed attacks
Delayed attacks add a new twist to the turn-based formula, allowing characters to attack even when it isn’t their turn anymore. Counterattacks are an effective (and, at least among Japanese strategy RPGs, common) form of delayed attack. By allowing melee units to only retaliate against melee units and ranged units to only retaliate against units at range, counterattacks further complicate unit match-ups and enforce character specialization. (Players will want to attack melee units at range, and vice versa.)

Attacks of opportunity are another form of delayed attack that encourage the player to pay extra attention to her own unit movement and placement, juggling the costs and benefits of expending all of a character’s actions during its turn versus keeping some in reserve in case enemies wander into attack range later on. These are, in short, an extension of the resource management concept we talked about in #9 above. (You can see the attack of opportunity mechanic at work with [X-Com’s reaction fire](http://www.ufopaedia.org/index.php?title=Reaction_Fire#Overview) system and with the guard command in [Pool of Radiance](http://crpgaddict.blogspot.com/2011/06/pool-of-radiance-combat.html).)

Interestingly, a couple of upcoming indie games ([Frozen Synapse](http://www.frozensynapse.com/) and [Fray](http://www.fray-game.com/)) actually use delayed attacks as the centerpiece of their entire combat systems. In these games, combat focuses around the player’s ability to guess which units will be where, when.

## Elevation effects
This is a straightforward extension of “variable terrain.” Elevation effects may grant range, accuracy and damage bonuses for attacks launched from the high ground, consonant penalties for attacks launched from the low ground, and hinder movement for certain character types. In other words, elevation effects are another way of differentiating parts of the battlefield and giving players minor objectives to weigh during the course of battle. (Should I capture the high ground, or go for another objective elsewhere?) They also work to provide further points of differentiation between characters: melee characters versus ranged characters, grounded characters versus characters with vertical movement abilities, and so on.

Speaking of movement…

## Movement-focused special abilities.
Movement tends to get short-changed when it comes time for special abilities in RPGs. Most RPGs give their characters damage-dealing attacks, some buffs, some de-buffs, maybe a few summoning spells, and then call it a day. It’s strange that we don’t see more movement abilities, particularly so given that war games—themselves the progenitors of role-playing games—originated with chess. Chess not only distinguishes pieces almost entirely through their unique movement patterns, it also throws in special movement abilities for good measure. Pawns, for instance, get an [optional bonus space](http://sinisterdesign.net/6-more-ways-to-improve-turn-based-rpg-combat-systems/www.youtube.com/watch?v=DE0YT8Rqtsg) when first moving forward from their starting spaces. There is also [castling](http://www.youtube.com/watch?v=nECzHBY6sEY). It’s a little odd to see so few turn-based RPGs employ special movement abilities, given their long and distinguished heritage.

It isn’t necessary to introduce a huge number of disparate movement patterns à la chess; just one or two special movement abilities can do the trick. Recent Fire Emblem games, for instance, give larger (particularly mounted) characters the ability to [rescue](http://fireemblem.wikia.com/wiki/Rescue_command) smaller characters and drop them elsewhere. Games in the Disgaea series let human characters [pick up and throw](http://disgaea.wikia.com/wiki/Throwing) allies and enemies, or even stack characters in a tower to set up elaborate throw chains. The rules in these latter examples themselves are simple and easy to grasp, but their tactical implications are far-reaching, opening up many new possibilities over the course of a single battle.

## Item drops
I’ve been thinking a lot about the last couple of iterations of Super Smash Brothers; in particular, about the way they punish players who stay put in an inaccessible corner of the battlefield. There are a few ways the game accomplishes this, but perhaps the most salient is through its use of [random item drops](http://en.wikipedia.org/wiki/Super_Smash_Bros._%28series%29#Gameplay). Random item drops reward mobile players: a player who controls most of the map is going to grab the vast majority of the items, many of them extremely helpful during the battle. By contrast, a player who turtles in a small portion of the map is statistically unlikely to snag more than an isolated few. This encourages dynamic play by giving battle advantages to the non-turtling player.

It doesn’t have to be items. Dune 2, the [great-grandaddy](http://www.ugo.com/games/dune-ii-the-building-of-a-dynasty) of the RTS genre, dropped crates containing free resources at random onto the battlefield, encouraging map control. It doesn’t have to be drops, either: numerous Japanese strategy RPGs employ [static treasure chests](http://www.youtube.com/watch?v=5hhrBLM8sfA&t=5m13s) to force players to advance at a steady clip, or else surrender their contents to thieves who spawn on the battlefield. The key thing is that there should be time-sensitive elements with unpredictable locations that give a tactical advantage to the player if he or she gets there first.

## Zones of Danger
Here is another thing that Super Smash Brothers does especially well, and which turn-based combat systems could stand to learn from. Super Smash Brothers maps tend to contain areas that put the player at greater risk from other players, typically due to the risk of taking environmental damage. Even better, those areas are oftentimes dynamic, meaning that the player has to adapt to a changing battlefield.

X-Com: UFO Defense had [an implementation](http://www.ufopaedia.org/index.php?title=Smoke_and_Fire) of this with its famously out-of-control fire and smoke dynamics, seemingly modeled on cellular automata. Dune 2, in turn, had a particularly ingenious approach with its “spice blooms”; a [spice bloom](http://en.wikipedia.org/wiki/Dune_II#Gameplay) was essentially a natural land mine that would destroy every unit on top of it when triggered (an event called a spice blow), but would also leave behind valuable resources. In this way, it served as both an environmental hazard and a random resource drop all at once.

## Death countdowns and revival
When a character falls on the battlefield, try having their unconscious body stick around for a while before death; give the player a chance to revive that character under a strict time limit. This simple rule both gives the player an opportunity to recover from mistakes, and provides them a challenging side objective with vast potential to spawn interesting dilemmas. You can see this technique at work in Final Fantasy Tactics, Tactics Ogre: Let Us Cling Together and X-Com.

## Character-centric consequences
I touched on something related to this in the last article under the rubric of providing multiple battlefield objectives. That was about giving battlefield events plot consequences. Here, however, I want to suggest to you that we should be doing everything we can to make our decisions on the battlefield have character development consequences.

Party RPGs with perma-death necessarily have a touch of that, provided that character deaths play a role in dialog and cut scenes going forward. (This happens in Fire Emblem games and in Telepath RPG: Servants of God.) But that’s just scratching the surface of what is possible.

I’m going to talk about a game that isn’t an RPG for just a second: [Crusader Kings 2](http://en.wikipedia.org/wiki/Crusader_Kings_II#Gameplay). Crusader Kings 2 is a recently-released strategy game that does exactly what I was [talking about back in 2010](http://sinisterdesign.net/?p=689): it models characters in an emergent way, then lets the game’s story grow organically out of their interactions. This sort of emergent personality modeling completely sidesteps the supposed incompatibility of narrative and gameplay, and sports the potential to make combat interesting on a level that few (if any) games have attempted to date.

Now, I’m not suggesting that RPGs should go whole hog and ditch their hand-crafted narratives in favor of an approach like this; rather, just consider for a moment the possibilities opened up by a hybrid approach. Suppose that characters in your party had certain personality attributes, and that those attributes would impact their performance on the battlefield. Maybe one character is “jealous,” so her accuracy drops if another character of the same gender gets between her and her love interest. Maybe another character is “greedy,” and gets angry if another character finishes off an enemy he wounded. Maybe a character who gets close to death one time too many gets a “traumatized” attribute and starts having flashbacks in cut scenes outside of combat. Maybe a character subject to a missed attack that would have otherwise been fatal will become convinced that (the) God(s) protected her, changing her dialog out of combat and making her less careful in combat. I’m just rattling off examples; the possibilities here are absolutely limitless.

Fire Emblem and its imitators have a very narrow implementation of character-centric consequences in so-called [support systems](http://fireemblem.wikia.com/wiki/Support), where characters that spend a lot of time near one another in battle can develop closer relationships and give each other bonuses in combat by fighting together. A different (also very narrow) implementation of this can be found in the “level up by doing” systems of the Elder Scrolls games and X-Com, where having characters perform specific actions makes them better at those actions over time.

Those sorts of implementations are elegant, but limited both in scope and in approach. A more robust, simulational implementation–a combat system which models character personalities and motivations, then impacts them dynamically over the course of a battle based on events as they occur–has enormous potential to lead to extremely interesting emergent situations in combat, both tactically and narratively.

# Conclusion
Well, that’s 18. I know of no RPG combat system that uses all eighteen of these techniques at once, and to be honest, I’m not entirely sure that I’d want one to! That would be one heck of a complicated combat system. But in an environment of RPGs whose combat systems err on the side of simplicity, that’s the sort of problem I really wouldn’t mind having.