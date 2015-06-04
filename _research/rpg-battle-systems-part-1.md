---
layout: article
title: RPG Battle Systems Part 1
author: Craig Stern (Sinister Design)
source: http://sinisterdesign.net/the-battle-system-i-wish-rpgs-would-stop-using/
priority: 3
---

# Introduction
Dungeons and Dragons, son of [Chainmail](http://www.acaeum.com/ddindexes/setpages/chainmail.html), [is the great granddaddy of the modern role-playing game](http://www.wired.com/gaming/virtualworlds/news/2008/03/ff_gygax?currentPage=1). Its importance cannot be overstated: not only was it revolutionary for its time, it has also directly inspired many of the early computer RPGs on which the genre is now based. Because of D&D’s [power as a brand](http://news.bbc.co.uk/2/hi/uk_news/magazine/3655627.stm), early edition D&D rules [were imported](http://www.gamasutra.com/features/20070223b/barton_03.shtml) into [a variety of classic computer RPGs](http://www.gamasutra.com/features/20070223b/barton_04.shtml), forming the backbone of their combat systems.

So you might be surprised to know that, as a game designer, I get heartburn any time I see a computer game deliberately aping the D&D combat rules. In spite of D&D’s intimidating legacy and marketing power, its rules simply aren’t well-suited for use in a computer RPG. Those rules (and the numerous knock-offs they’ve inspired) have been implemented sloppily in RPG after RPG, reducing what should be enjoyable tactical combat into an opaque and frustrating slog.

Rather than address the issues this has caused, the older generation of western RPG developers has instead collectively [jumped ship](http://sinisterdesign.net/?p=830) from the U.S.S. Turn-Based. Accordingly, this article is mostly aimed at indie RPG developers who may feel tempted to build combat systems modeled on the D&D-alikes that came before. Here are the reasons why we shouldn’t.

# Reason 1: The D&D combat system is sloppy.
Back in high school, I developed a pen-and-paper alternative to Advanced Dungeons and Dragons Second Edition, which I chose to call (rather uncreatively) “Epic RPG.” The primary design idea behind the Epic RPG system was to streamline combat and focus on role-playing. It dispensed with randomized damage rolls. It ditched saving throws. The few rolls that remained were made uniform: all of them were performed on a 100-point percentage scale using two 10-sided dice.

The system also employed a large stable of skills and spells designed to open up the player’s options for approaching different problems through role-playing. There were no spells that dealt direct damage: no magic missiles, no fireballs. Rather, the spells all had simple, descriptive effects that required players to combine them creatively in order to take out enemies. Gravity Well, for example, was a magical trap that would suck enemies flat onto the ground and hold them there for a certain period. Rubberfoot gave the caster two consecutive bounces where he could soar up to 60 feet into the air, then land with impunity. Crumble would cause a stone surface to break apart into chunks with a touch.

You can imagine how a clever player might prepare for an encounter with a large group of enemies in a cavern. She might set up a Gravity Well trap, then cast Rubberfoot, and once the enemy triggered the gravity well, leap up to the ceiling of the cave and Crumble a portion of the ceiling down onto them, crushing them.

After years of playing D&D, my friends and  started using this system. We quickly found our battles involving less time rolling dice and more time role-playing. I bring this up to make the point that a good RPG combat system should be elegant. It should establish relatively few, simple rules that can interact in interesting ways, thus creating a vast possibility space.
Think of chess: there are six different types of pieces (pawn, knight, bishop, rook, queen and king), each with its own movement rule. There is a rule stating that the white player moves first. There is a rule stating that you can move one piece per turn, once. There is a rule establishing a forced move (check) and one establishing a win condition (checkmate). There are a small handful of other, minor rules as well, but for the most part, that’s it. Out of that small set of rules, you get a highly tactical combat system that exemplifies the old design cliché “simple to learn, hard to master.” That, friends, is what emergent complexity is all about.

Unfortunately, D&D combat utilizes something like the exact opposite of emergent complexity: it complicates even the simplest of actions, bogging combat down with numerous rules that apply only in rare, select instances. Just look at the size of the D&D rulebook: the [Player’s Handbook](http://en.wikipedia.org/wiki/Player%27s_Handbook) was more than 125 pages thick in its first incarnation, more than 250 pages in its second and more than 300 in its third. The Fourth Edition Player’s Handbook is the largest yet, weighing in at 320 pages; its companion, the [Dungeon Master’s Guide](http://en.wikipedia.org/wiki/Dungeon_Master%27s_Guide#Dungeons_.26_Dragons_4th_edition), currently contains an additional 224 pages on top of that.

![ ][Biggest Book]
<cite>“But wait: what do I roll if I duct-tape a bec de corbin onto my long sword?”</cite>

Not all of those pages are devoted to rules, of course, but a significant portion of them are. Every single weapon has a damage range with its own associated die rolls, and yet there are numerous different weapons and spells which essentially duplicate each other. There are five different [saving throws](http://en.wikipedia.org/wiki/Dungeons_%26_Dragons_gameplay#Saving_throws) for different types of effects (three if you’re using the latest rules), which are themselves entirely separate from rolls against your character’s six [ability scores](http://en.wikipedia.org/wiki/Dungeons_%26_Dragons_gameplay#Ability_scores). Every single successful attack requires at least two die rolls. You need a bare minimum of six different kinds of dice just to be able to play: a four-sided die, a six-sided die, an eight-sided die, a ten-sided die, a twelve-sided die and a twenty-sided die.

There is a word for this: bloat. From a design perspective, D&D’s combat system is an overgrown mess. This leads us directly to our second reason for giving the D&D combat system a pass…

# Reason 2: The D&D combat system is inscrutable.
In order for a tactical combat system to work, the player has to be able to figure out the likely results of his or her potential actions. Unfortunately, the D&D ruleset is horrible at this.

To determine a character’s percentage chance of hitting a target, the player has to find the target’s Armor Class, find the attacker’s Thac0, subtract the target’s Armor Class from the attacker’s Thac0, then multiply the result by 5.

![ ][Confused]
<cite>“Wh…what’s a Thac0?”</cite>

More recent editions of D&D have [changed](http://en.wikipedia.org/wiki/D20_System) this mechanic in ways that, if anything, make discovering one’s percentage chance to hit even more labor-intensive.

> To resolve an action in the d20 System, a player rolls a 20-sided die and adds modifiers based on the natural aptitude of the character (defined by six abilities, Strength, Dexterity, Constitution, Intelligence, Wisdom, and Charisma) and how skilled the character is in various fields (such as in combat), as well as other, situational modifiers.[3] If the result is greater than or equal to a target number (called a Difficulty Class or DC) then the action succeeds.

Very few RPGs using an D&D-style ruleset gather all the necessary stats, perform the calculations behind the scenes, then just spell out the resulting percentage chance of hitting for the player. (Eschalon is a happy exception to this rule.)

Even those that do spell out a player’s chances to hit, however, essentially only tell the player whether her character is going to do no damage. Under an D&D-style ruleset, once the attack hits, the damage actually dealt can still vary from essentially nothing (1 point) to as much as twelve times that amount, depending on the weapon used! Each level of damage within that range has an equal probability of occurring; thus, unless she is attacking something with very low hit points, the player has no reasonable way to guess what will happen even if her attack connects. This makes planning out a strategy for even a single round of combat difficult.

Compare the situation above with the way Fire Emblem handles information about a potential attack: you select a character, then select an opponent. The game then immediately and clearly spells out for you a) your chance to hit, b) the damage you will deal, c) your chances of landing a critical hit, d) the number of blows you will be able to get in, and e) all of those same stats for the enemy vis-a-vis the attacker. That, ladies and gentlemen, is how you give a player clear information about her tactical options.

# Reason 3: Results are too randomized
Before computers, game developers needed ways to model unpredictability. Unfortunately, spin wheels are cumbersome to transport and rely on physics so simple that players may learn to reliably manipulate the results with skill and practice. Playing cards are only as random as the shuffler makes them, and are even more labor-intensive to produce and use than spin wheels. What was a game developer to do?

![ ][Twister]
<cite>The spin wheel–probably not a great way to resolve combat.</cite>

Dice were the answer. Dice are fast (compare a die roll with shuffling a deck of cards), portable, and reliably generate randomized results. In short: dice are the original random number generators, and as far as random number generators reliant on real-world objects go, they’re probably the best. Hence, the popularity of dice in non-computer games.

There are big advantages to being able to generate numbers at random in a game. The biggest is that it introduces an extra element of risk to player choices. Risk is exciting. As the Wired biography on Gary Gygax [put it](http://www.wired.com/gaming/virtualworlds/news/2008/03/ff_gygax?currentPage=2):

> Gygax was fascinated by the way the rolling of dice affected — and enlivened — the game experience. “Random chance plays a huge part in everybody’s life,” he says. He learned this first hand in his job as an insurance underwriter, which was a game in itself. His work involved evaluating policies and calculating how much to charge in premiums based on salary, age, medical reports, and the potential for long-term disabilities. He did special risk underwriting as well, such as evaluating the payout for a Major League Baseball team that wanted to take out a policy on one of its players. “I wasn’t popular in the home office because I wasn’t chicken,” he says. “I’m just a risk taker. I have gut instincts.”

That said, there are also big disadvantages to using randomized numbers in a game. Every time your game requires the player to roll dice, you take control–and therefore, responsibility–away from the player. You open the door of “that wasn’t my fault, it was bad luck.”

![ ][Continuum]

That’s a bad door to open. Some degree of player control is essential to skilled play of a game. If your game’s battle system ventures too far into Randomized territory, the player is going to feel like she doesn’t have control over the outcome—and she’ll be right.

# Reason 4: Mitigating factors do not translate to computers
For the most part, D&D gets away with relying so heavily on die rolls because it is a role-playing game run by human beings. Players have the flexibility to improvise tactics during a play session—and, just as importantly, the ability to nag the Dungeon Master to fudge the dice in the name of a fun play experience.

If you are designing a computer game, there is no Dungeon Master to fudge the rules for you. There is only a program that is going to execute every line of code you enter with exacting literalness. You do not have the luxury of designing an arbitrary or unfair combat system. Any factors that are going to tilt combat in the players’ favor have to be coded into the game itself.

Unfortunately, most games that use an D&D-style combat system fail to give the player enough tactical options to manage the risks imposed by a highly randomized combat environment. They adopt the Thac0, the randomized damage and the saving throws, but then fail utterly to give the player more than a small handful of real tactical options. The player’s only friends become superior stats and superior loot.

This is poor design. Giving the player better combat numbers merely amounts to weighing the dice in the player’s favor. Weighing the dice does not turn a game of luck into a game of skill. In a game with randomized outcomes in combat, you have to give the player some robust tactical tools to manage her risk, or else she might as well be playing [this](http://www.newgrounds.com/portal/view/558933).

Some game designers have done a better job of introducing outside tactical considerations than others. Compare, just for a moment, two popular computer RPGs with D&D-based combat systems: Baldur’s Gate and Pool of Radiance.

Pool of Radiance implements [a wide variety of tactical considerations](http://crpgaddict.blogspot.com/2011/06/pool-of-radiance-combat.html) which allow the player to mitigate the risks inherent to a highly random, dice-based battle system: distance, directional facing, different attacks (fighters can sweep groups of adjacent enemies), and large numbers of characters under your control with different strengths and abilities.

Compared to Pool of Radiance, combat in Baldur’s Gate is an unpredictable mess. The tactics you can use are highly limited due to 1) the small number of characters under your control; 2) the fact that they each have only a single attack (not counting spells); 3) the awkward non-grid-based movement system; 4) the fact that enemies close distance with you almost instantaneously; and 5) the fact that [you do not have direct control](http://www.rpgamer.com/games/dnd/bg2/reviews/bg2tobstrev1.html) over your characters.

# B-but…but…
“But Craig,” you protest, “Baldur’s Gate 2 and Planescape Torment are widely considered to be two of the greatest RPGs ever created, and they both used the Baldur’s Gate implementation of the D&D combat system!” This is true. However, these games are classics because of their engaging characters, strong writing, and player freedom.

They are not classics because of their combat. So far as I am aware, there is not a single person on this planet who has played Planescape Torment, then decided that it was the best RPG ever made because he just loved using D&D’s clunky combat mechanics to determine the outcome of enemy encounters.

# The Takeaway
The D&D combat system barely functions in its original, intended medium; recreating it in a computer game is like creating a calculator program that lovingly renders a pixelated abacus and lets you click to slide the beads around. You might as well just code something new that isn’t tedious and frustrating to use.

In my next post, I’ll talk about various ways to create a genuinely satisfying tactical combat system. Until then, for the love of all things holy: please leave the D&D combat system alone.

[Biggest Book]: ./biggest-book.jpg
[Confused]: ./confused.jpg
[Twister]: ./twister.jpg
[Continuum]: ./continuum.jpg