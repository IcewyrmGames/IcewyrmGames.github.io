---
layout: page
title: Game Systems Part 1
author: Daniel Achterman
source: http://web.archive.org/web/20140722022325/http://www.altdev.co/2011/11/12/the-craft-of-game-systems-part-1/
---

# Introduction
Since this is my first post, I’d like to start with a quick introduction. My name is Daniel Achterman, and I’m a game designer. I’ve been doing gameplay and system design in a variety of genres for about 8 years, mostly RPGs, at companies like Gas Powered Games and ArenaNet. My intention with these pieces is to share specific, practical advice and techniques that game designers can use to create systems, tune content, and simplify their lives.This first piece shares some general guidelines and best practices that I’ve found useful. Future articles will cover topics like experience curves, calculating values for content like item stats and ability damage, and managing large amounts of game data.

If you ever have a question or want to start a conversation, you can reach me in several ways:

- Add a comment to this post.
- Send me a message on Twitter: @DanielAchterman
- Send me an e-mail at DanielAchterman@gmail.com

## What Type of Game Is This Best For?
The approach to game design in these articles is analytical and methodical. It’s best suited to games with a lot of content, like RPGs or strategy games. These articles are more about the hour-to-hour experience than the minute-to-minute experience, so they won’t apply to many types of games. My apologies if this material doesn’t directly translate to your work - I hope you can still find them valuable.

# The Hallmarks of Good Systems
RPG and strategy games tend to have a ton of content - more than any one person can keep in their head at once. Game systems don’t just define how that content works - they are a tool that designers use to generate, tweak, tune, and manage that content.

From a designer’s perspective, good systems should be five things: comprehensible, consistent, predictable, extensible, and elegant.

![][Vagrant Story]
<cite>This is the Vagrant Story weapon crafting chart. Fun game, but weapon crafting was incredibly obtuse and over-complicated.</cite>

- __Comprehensible.__
	- You, the designer, should understand all the parts of your system. You should know how you choose various values in your game, why you do it that way, and what other rules and content those values impact. If you want to adjust your gameplay in a specific way, you should know what to change to get that result.
- __Consistent.__
	- Your game rules and content should function the same in all areas of your game. Armor shouldn’t work differently for flying units, and the formula for gold value of items shouldn’t change at high levels. This is a big part of making your game comprehensible to you.
- __Predictable.__
	- You should be able to determine how your systems will behave in new circumstances. If you multiply experience gained by 2 in some situation, or introduce a monster with double the normal armor, you should be able to predict the results. Using simple progressions and formulas helps make predictable systems.
- __Extensible.__
	- When you create new types of content for your game, you should be able to easily extend your existing systems to include it. Maybe you decide what your game really needs is randomly generated minibosses. You should be able to extend your existing monster content to include them easily. Extensibility makes it easier to design your game iteratively, adding new systems and content types as they are needed.
- __Elegant.__
	- Elegant systems have a certain ... je ne sais quoi. They create extremely rich situations from a small number of moving parts. Some of my favorite examples of elegant system design are 4th Edition D&D, Magic: the Gathering, and Settlers of Catan.

![][Catan]
<cite>The numbers - so simple! But the situations - so interesting!</cite>

# Getting Started: Game Systems Follow Gameplay
Creating a game’s systems and content is an intimidating task. It can seem like there will be a million variables in the game, and before you can start figuring out how they’ll relate to each other, you have to choose which ones your game will have in the first place. What stats will your game characters have? What will increase on level up? What types of upgrades can characters get? Items? Resources? Experience values? Gold costs? It’s overwhelming.

> “Begin with the end in mind.”
> <cite>- Stephen Covey</cite>

The first step is to clarify the game you’re making. While systems are the foundation of how a game works, they shouldn’t be the starting point of its design. You might have a great idea for how mana regeneration will work in your game, or how leveling will be affected by weapon types. Leave those ideas aside for now, and instead ask yourself: What is the core game loop? What interesting decisions will players be making? What are the appeals you intend your game to have?

Those are the aspects of your game that players engage with most immediately, so your goal when designing systems should be to support the game experience you intend. Form follows function, and systems follow gameplay.

## Case Study: Dungeons and Dragons

![][DnD]

Dungeons and Dragons is about role-playing characters in a fantasy setting and going on adventures with your friends. Teamwork and cooperation are an important part of the experience. Characters perform actions in turn, with the chance of success and results of those actions defined by systems. To make cooperation matter, there are a variety of types of challenges (combat, disarming traps, social interactions) and combat roles (defender, striker, support) that characters can be strong or weak in.

As a systems designer, the above description would direct my work in several ways:
- To encourage teamwork, systems should allow characters to excel in certain types of challenges and combat roles, but not others.
- Role-playing and non-combat play is important, so social statistics should be meaningful.
- Since immersion and role-playing are important, the content of the game should be flavorful and exciting in a fantasy setting.
- The math to determine the results of actions should be comprehensible and uncomplicated.

# The Components of Game Systems
“Game Systems” or “Mechanics” can be broken down into three components: Parameters, Rules, and Content.

- __Parameters__
	- Parameters are the values that your game systems use to simulate your game, such as health, movement speed, weight, mana cost, critical hit chance, etc.
- __Rules__
	- Rules are the functions and formulas that determine the results of actions and events in your game. Rules include things like how combat damage is calculated, how character statistics change when they level up, and how random loot is determined.
- __Content__
	- Content is all things in your game, including characters, items, monsters, spells, talents, etc. Each type of content has parameters that define it, like damage for a weapon, or  attributes for a character.

![][FF13]

In this screenshot of Final Fantasy XIII, the content is the monsters, characters, and the weapons they’re using. The parameters are the values for all of their stats that affect combat, such as their health. The damage values when the hero strikes a monster are determined by rules, using the character parameters and some randomization.

![][MTG]

For a different kind of example, the content in Magic: the Gathering is the cards. Each card in the game represents a noun that players can summon, like a creature or land, or an action that players can perform, like casting a spell. The rules define the different types of cards and how they function. This creature’s special abilities also fall under rules, as does its “Creature” type, as that defines its functionality in the game’s rules. The creature type, costs, stats, and ability values are all parameters.

# Designing a Game System in Five Steps
Once you’re ready, break the task down into pieces and tackle one at a time. This is the process that I use to design and iterate game systems:

1. Choose the parameters that your game uses.
2. Design rules that are no more complex than necessary to implement your game vision.
3. Define the progressions for how parameters change throughout the game.
4. Design content types that are as complex and interesting as you can manage.
5. Add new parameters, systems, and content types in layers as needed.

Parameters are the first step because choosing them helps focus what aspects of gameplay need to be reflected in your systems. While parameters are closely related to content, if you start by thinking of all the types of content your game will include, it’s easy to bloat your parameter list. Starting with parameters and then rules for how they interact helps you make the hard cuts up front and keep your content and rules lean.

My next article will cover this process in more detail and offer guidelines for how to choose parameters, design rules, and design content types that will result in a system that is powerful and flexible.

# Conclusion
Much of game design is an art. The quality of content and the appeal of various design choices are subjective and vary from player to player. Good system design is more of a craft. Game systems are a tool that designers use for creating and tweaking content. In terms of ease of tweaking and resistance to degenerate cases in games, some system designs are objectively superior to others.

I adore investigating game systems. I love seeing how designers organize their data, reverse engineering their content progressions, and trying to figure out why they used the formulas they did. I hope you enjoyed this introduction, and I’m looking forward to sharing more techniques and examples soon. Please let me know what you think in the comments!

[Vagrant Story]: /img/GameSystems/Vagrant.jpg
[Catan]: /img/GameSystems/Catan.jpg
[DnD]: /img/GameSystems/DnD.jpg
[FF13]: /img/GameSystems/FF13.jpg
[MTG]: /img/GameSystems/MTG.jpg