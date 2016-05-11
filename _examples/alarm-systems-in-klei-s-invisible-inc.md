---
layout: article
title: Alarm Systems in Klei's Invisible, Inc.
author: James Lantz
source: http://www.gamasutra.com/view/news/244383/Game_Design_Deep_Dive_Alarm_systems_in_Kleis_Invisible_Inc.php
category: Deep Dive
---

# Who: James Lantz, Technical Designer at Klei Entertainment
Hi, I’m James Lantz, technical designer at Klei Entertainment and one of the core designers on the _Invisible, Inc._ team. I have a deep passion for layered systems design and deep, complex experiences. Before Klei, I worked at Loot Drop and as an independent designer on a game called _Mercury_.

# What: The Alarm system in Invisible, Inc.
Our vision of _Invisible, Inc_ has always been a tight game about tough decisions. In Invisible, there is no decision or action without consequence. The alarm system is one of the most important mechanics in the game. The alarm level goes from 0 - 6 and represents the corporation you’re infiltrating slowly discovering your presence. It goes up when you kill a guard and when guards see bodies, but most importantly it also goes up at the end of each turn in the game.

The alarm system is undoubtedly one of the more controversial mechanics in _Invisible_. There are very few stealth games that push the player in the same way _Invisible_'s alarm system pushes you. It is a huge part of what makes _Invisible_ a tight, tense experience and not a sandbox stealth game.

<iframe class="thumbnail" src='https://gfycat.com/ifr/AthleticBiodegradableGrassspider' frameborder='0' scrolling='no' width='640' height='444.44' allowfullscreen></iframe>

While the alarm system made the game too stressful for some players, it also allowed us to lower the overall difficulty in each level. No starting situation in _Invisible_ is particularly difficult to solve on its own. Instead they work together to challenge the player’s decision-making in the mid to long term. This is part of what gives _Invisible_ a unique feeling -- it’s about spy movie style casing and planning in addition to clever execution.

# Why?
_Invisible_'s design was strongly inspired by some of our favorite games over the last decade, including _X-COM_, _FTL_ and _Spelunky_. One thing that those games all share in common is a sense of time pressure, either in certain parts or throughout. In _X-COM_, bomb missions have direct time pressure. In _FTL_, you’re constantly being pursued by the rebel fleet. In _Spelunky_, a deadly ghost will start to chase you if you hang out too long on any given level.

We knew we needed that sense of time pressure for _Invisible_, not only because it fit the game’s theme but also because we wanted players to be making interesting tradeoffs with every move, and keeping busywork to a minimum. But none of our existing influences gave us a perfect starting point.

<iframe class="thumbnail" src='https://gfycat.com/ifr/SerpentineZestyChital' frameborder='0' scrolling='no' width='640' height='289.59' allowfullscreen></iframe>

_Spelunky_'s ghost works in the context of an action game, but ultimately can be avoided indefinitely and doesn’t tie together existing systems, which make it unsuitable for a game like _Invisible_. _FTL_'s rebel fleet is closer to what we want, but while fighting the rebel fleet is more interesting than running away from _Spelunky_’s ghost, _FTL_ is balanced such that engaging the rebel fleet is never a good idea and any reasonable player will avoid them entirely unless they are tremendously unlucky. Every other _X-COM_ mission, with the exception of the bomb mission, has no time pressure and allows players to advance, inch by inch, with no motivation for reckless play beyond impatience or role playing.

We wanted the same sense of time pressure as those systems, but wanted to create a new kind of mechanic that would play with our existing systems and underpin the players’ mid and long-term decisions throughout each game.

# How?
For inspiration, we turned to the classic hunger mechanic in true roguelike games like _Nethack_. Hunger not only creates a sense of tension, it also creates a greater context for each move that gives players a structure in which to understand the rippling consequences of each decision. It also ties neatly into the existing systems through which players interact with the game, injecting new life into mechanics.

What’s hunger for a spy? How much she is detected, how much heat is on her, how much chatter is on the radio -- and so, we designed the alarm system.

Initially, the alarm was a series of 20-30 levels. It would go up one per turn, and at certain intervals it would level up and cause nasty things to happen for the player. This satisfied our core design goals for the mechanic, but it failed on multiple experiential levels. First of all, the UI was unintuitive -- 20 levels of alarm made it unclear when the next alarm level would actually become a problem. Second, the consequences of each alarm level were unpredictable and random, which would be OK in a more action-oriented game but was unwelcome in a stealth game about careful planning.

To solve these problems, we instead made the alarm 6 levels and gave each level 5 sub-levels that had no effect. The only time the alarm had an effect is when all 5 sub-levels filled up and it made the transition from one full level to another full level. This also allowed us to use smaller numbers, making the alarm more readable and the levels more memorable. With our new alarm in place, we could provide tooltips warning players about the next level without flooding the alarm with tooltips about every level.

<iframe class="thumbnail" src='https://gfycat.com/ifr/IckyDifficultHorsefly' frameborder='0' scrolling='no' width='640' height='407.64' allowfullscreen></iframe>

That still left the biggest question for the alarm system -- what kind of consequences make sense in _Invisible_? We were stuck on this problem for awhile, but grounded ourselves in our core design goals for the system. Our main goal was not to make the alarm levels balanced, nor to make them the most interesting and deep they could possibly be. Instead, our goal was to create movie-like tension and drama above all else. Because our goal for the alarm was primarily experiential, we focused on ramping tension and creating systemic texture rather than ratcheting up the difficulty.

For example: at alarm level 2, all the firewalls in the building are raised by one. At alarm level 3, another patrol enters the building. While increased guard presence is the natural language of the game, early firewall levels are designed to show you the texture that other systems in the game offer when combined with the threat of guards.

That leaves one huge problem still unaddressed -- the alarm feels unfair to many players. This is a problem of context and expectations from a stealth game based on previous experiences, and one that we were unable to solve fully. However, we were able to ameliorate the issue by providing lots of in-world fiction for the alarm and making it very clear and predictable to players with extra UI and tutorialization, including the small but incredibly effective change of renaming it from “ALARM” to “SECURITY LEVEL.”

# The Result: A tense and dramatic spy thriller
Both in terms of gameplay and feeling, we got a great result from our alarm system. We felt that it fits perfectly into the game and is a core part of what makes all the systems work and what forces you to think carefully about each decision.

That said, there are definitely players who we lost along the way with the alarm system. While it’s clear that it was the best choice for _Invisible_ as a game, it would have been ideal if we had managed to perfect the way we contextualized the alarm system both in-world and out so that fewer players had a negative gut response to it.
