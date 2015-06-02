---
layout: article
title: The Craft of Game Systems Part 2
author: Daniel Achterman
source: http://web.archive.org/web/20140722040536/http://www.altdev.co/2011/11/29/the-craft-of-game-systems-part-2/
priority: 1
---

# Introduction
Welcome back! [My last article](http://web.archive.org/web/20140722040536/http://altdev.co/2011/11/12/the-craft-of-game-systems-part-1/) introduced my take on the craft of game system design. I identified the goals I believe designers should strive for, and broke down the component parts of systems. This article covers the process I use for designing powerful and flexible systems for games like RPGs and strategy games, and offers tips for each step.

## Recap
Once again, the goals for system design are based on helping you design a consistent system that lets you create game content efficiently. A system should be:

* __Comprehensible__: The parts of the system and how they interact should be understandable.
* __Consistent__: Rules and content should function the same in all areas of your game.
* __Predictable__: Designers should be able to predict how the system will behave in new circumstances.
* __Extensible__: It should be easy to extend the system with new rules and types of content.
* __Elegant__: Systems should strive to create rich situations from simple components.

The three components of game systems are parameters, rules, and content. The most intimidating part of designing a game system is getting started. I recommend breaking the task into the following steps:

1. Choose the parameters that your game uses.
2. Design rules that are no more complex than necessary to implement your game vision.
3. Define the progressions for how parameters change throughout the game.
4. Design content types that are as complex and interesting as you can manage.
5. Add new parameters, systems, and content types in layers as needed.

Let’s walk through each of those steps in more detail.

# Choosing Game Parameters
The golden rule of choosing what parameters to put in your game is to focus on parameters that impact the interesting choices players make. This is why it’s so important to start by clarifying your gameplay - it informs the parameters your game should have. If your RPG has different combat styles, make statistics to allow players to define how their character fights. Starcraft has two resource types because when to start mining gas and how heavily is an interesting choice that players make.

* __Start with character statistics.__ Players view games through the lens of their characters. All other content revolves around how it effects characters, such as items, skill trees, and research bonuses.
* __Start with a small number of basic stats.__ Create only enough stats for players to define themselves within your intended gameplay. Lots of stats are not necessary for interesting gameplay.
* __Consolidate parameters that don’t matter.__ Don’t include something like “Physical Defense” and “Magic Defense” if players aren’t meaningfully manipulating them to specialize their character or defeat content. “Defense” will suffice.
* __Be transparent.__ Ideally, players should be able to figure out what a value does and how it’s determined from its name alone. “Armor” and “Strength” are transparent stats to today’s players. “Attack Power” and “THAC0” are not.

The Legend of Zelda is a great example of a game with minimal, transparent parameter design. It’s only character statistic is “health”, which is represented by the simple visual of hearts.

![][LOZ]
<cite>A classic example of minimal, transparent parameter design.</cite>

# Making Simple Rules
Rules use the values of parameters to determine what happens in your game. To keep your system comprehensible and predictable, design the simplest possible rules that are sufficient to implement your game visions. For instance, many games don’t have damage reduction from armor at all. In D&D, armor simply reduces your chance to get hit. [The formula for damage reduction from armor in World of Warcraft](http://www.wowpedia.org/Armor#Damage_absorption) is much more complex, but it’s necessary to make high armor values scale correctly in the end game.

* __Keep formulas basic__. Formulas should be more multiplication and addition and less exponents and logarithms. This makes it easy for your players to understand how things work, and makes it easy for you to model how your game works.
* __Don’t use a single parameter for too many things__. If “Strength” affects both attack damage and health, it becomes more difficult to comprehend its value in different situations, and it will make it more difficult to balance your game, because adjusting one stat will have repercussions in multiple place.

Good rule design is crucial for creating consistent game systems. It’s a difficult challenge to create rules that serve all the needs of your game and are still simple and elegant.

# Creating Parameter Progressions
Parameter progressions refer to stat values that tend to change over the course of a game. For instance, character statistics increase and they get gear with higher damage and armor ratings as they level up in RPGs. In strategy games, advanced structures often have increased benefits and costs.

Progressions are crucial to game balance. __For a game to be balanced, related values should change at similar rates__, like a player’s power in battle and the strength of the monsters he fights. High level things like “player power” are often aggregates of a number of parameters, like armor, weapon damage, stats, and character stats. Understanding how the progressions of those parameters interact is key to making a game system predictable and extensible.

* __Define the rate that you expect stats to increase as players progress.__ Some stats may increase naturally as players level up (health, core stats) and others may increase as a result of getting better equipment (armor, weapon damage).
* __Use the simplest necessary progressions and formulas__. Values can increase linearly, quadratically, exponentially, or in some horrifying combination. Use the simplest progression that does what you need.
* __Make related values change at similar rates__. For instance, monster power and player power should increase at similar rates, as should monster power and monster XP value. Don’t make one linear and one exponential, or your game will be unbalanced.
* __Avoid switch statements__. If weapon damage increases at one rate from levels 1-10 and a different rate from levels 11-30, it’ll be more difficult to make other content match. Resist the desire to make special case solutions, and focus on consistent systems.

# Types of Progressions
There are many kinds of value progressions with different properties. The most common are linear, polynomial / triangular, and exponential.

## Linear
_Linear progressions_ are the simplest type of progression. Their formula structure is Ax + B, causing the value to increase at a constant rate. They’re simple and easy to understand, and I try to use them wherever they’re appropriate. One downside is that as x increases, the difference between terms becomes less significant. When you have 10 armor, +5 armor is awesome. When you have 500 armor, +5 armor barely matters.

![][Linear]
<cite>A linear progression</cite>

## Polynomial
The most common type of _polynomial progression_ is the _quadratic progression_, which has the structure Ax2 + Bx + C. The rate of change increases as x increases, which gives it many uses in games. It shows up commonly because the product of linear progressions is a polynomial progression. So, if the amount of gold monsters drop increases linearly with level, and the number of monsters players need to kill to level up also increases linearly with level, then the amount of gold players earn from monsters each level increases quadratically..

![][Polynomial]
<cite>A polynomial progression</cite>

## Exponential
_Exponential progressions_ have the structure C * Ax. They grow slowly at first, then extremely rapidly. They can be difficult to use because they explode so quickly, but they have some interesting mathematical properties that make them a great fit for certain systems, such as experience progressions.

![][Exponential]
<cite>An exponential progression</cite>

# Creating Interesting, Manageable Content
Content is where the magic happens. Content includes everything from the weapons that players can find and use to the skills and powers they can learn. The golden rule for content is to __design content that is as complex and interesting as you can manage__.

Content can be simple or complex. For instance, an item bonus that increases the wielder’s chance to get a critical hit by 1% is simple. Its value is immediately obvious to the player and is always the same. An item bonus that increases the wielder’s attack speed by 50% for 5 seconds after he gets a critical hit is complex. Its value is not immediately obvious, and its value is conditional on the character’s chance to land a critical hit.

* __Start simply and add content types iteratively__. Don’t start with your amazing idea for a blacksmithing system that lets players reassemble weapons from their component parts. You’ll just be creating complication at the time you most need simplicity. As you build your game and clarify its needs, add new content types, systems, and parameters, and define how they interact with the basics you have.
* __Ensure you can roughly calculate the value of your simple content__. For instance, what is the value of 2 points of strength, or a 1% increase in crit chance? Those are both examples of simple content, and being able to estimate the value of something will simplify tuning and balancing.
* __Decide what options players will have for modifying various statistics__. In Diablo II, numerous items affect stats like strength and dexterity, but bonuses to skill levels only appear on a few types of items.
* __Don’t allow players to overspecialize__. Highly specialized characters can trivialize aspects of your game, so don’t give players the ability to do it excessively. In World of Warcraft, all epic items have bonuses to core statistics like agility and stamina, but there are almost no other sources of those statistics, preventing players from stacking them.

It’s easy to want to design iteratively, but often very hard to do it. Maybe your team’s programmers and artists are busy making the engine and concepting, and you have plenty of time to write a massive a design document that details your entire game. You must resist! Don’t design too far ahead of your game. _Find a way to prototype your design_, whether in a primitive version of the engine or Flash or XNA or with cards, and put that prototype in front of playtesters. It will pay off down the road.

# Content Complexity and the Cost of Balance
The simpler your content is, the more you’ll be able to use math and exact process to balance your game. If it’s complex or conditional, it can be difficult to use math to calculate its value, and the more playtesting and intuitive hands on tweaking you’ll have to do to balance it.

Complex or conditional content can offer players deeper, more interesting choices. If your team has the resources and time to dedicate to balance, make your content interestingly diverse and complex. If it’s just you, be aware of your limitations and keep your content’s complexity in check.

# Final Word: References
I got an e-mail from a reader asking for suggestions for more articles or books about the craft of game systems. I'd like to offer a couple links and put out a call for more:

It's my opinion that _Mark Rosewater_ ([@Maro254](https://twitter.com/#!/maro254)), of Magic: the Gathering, is doing the best game design writing on the internet today. Many of his columns are specific to Magic, but many are extremely thoughtful articles about design in general. As an example, here's part one of a two part series on [The 10 Principles of Good Design](http://www.wizards.com/Magic/Magazine/Article.aspx?x=mtg/daily/mm/89).

_Ian Schrieber_ ([@IanSchreiber](https://twitter.com/#!/IanSchreiber)) wrote an excellent online course about a variety of design concepts. Here's the section on [Game Balance](http://gamedesignconcepts.wordpress.com/2009/08/20/level-16-game-balance/). UPDATE: In fact, he wrote an entire course about game balance, at [gamebalanceconcepts.wordpress.com](http://gamebalanceconcepts.wordpress.com/).

If you have an article to recommend, please add it to the comments, e-mail me, or send me a message on Twitter (@DanielAchterman).

[LOZ]: ./LOZ.png
[Linear]: ./Linear.png
[Polynomial]: ./Polynomial.png
[Exponential]: ./Exponential.png