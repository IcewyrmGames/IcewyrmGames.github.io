---
layout: article
title: "Design 101: 1- Design Goals"
author: Dan Felder
source: http://gamasutra.com/blogs/DanFelder/20150413/240853/Design_101_Design_Goals.php
category: Design 101
---

# Welcome!

![ ][Classroom]

Hi, welcome to Design 101. Like many people in the industry, I get asked a lot of questions about game design. Sometimes it's from friends, sometimes it's from their kids, sometimes it's even from new students of my former teachers. Lately I've been answering a lot of the same questions over and over again, so it'll actually save time if I just write an article series.

Today we’re going to be talking about what I believe to be the most important concept in game design. Amazingly, it’s also a topic that's rarely discussed. In fact, I feel it's the root of a lot of miscommunications, objections and arguments about game design we see.

It starts with a question.

# The Question
You’re the lead designer of a turn-based war game. It’s time to design how combats between units work.  John, a designer on your team, is arguing to make the combat system really swingy and based in random elements like dice rolls; so that a weaker unit has a small but significant chance of destroying much stronger units and surviving. Kate, another designer on your team, is arguing to make the combat entirely deterministic; so that stronger units will always defeat weaker ones.

John claims that his suggestion will make each combat a lot more exciting. Kate claims that players will find losing stronger units to weaker ones frustrating and that it will suck the skill out of the game.

Which suggestion is better?

# The Core Answer (That is also a Question)
To answer this question we need to ask ourselves, “What experience is this game trying to create for the player? What do we want the player to feel at this moment?” This is our Design Goal.

Without a Design Goal, deciding between John’s and Kate’s suggestions is impossible. It’s like trying to decide whether water is better than wine. Are we trying to impress a date? Are we trying to move to a healthier diet? Are we trying to pick beverages for an elegant party? Are we filling a sports bottle with a refreshing drink? What’s our goal?

The fact is that all mechanics are correct for SOME game. All mechanics create different experiences for the players. The question is which mechanics create experiences that support your design goal. Game design is a bit like chemistry. You figure out the reaction you want to create in the players, then pick mechanics which create that reaction. And yes, if you pick the wrong ones the result will  probably blow up in your face.

# Applying Design Goals
To figure out whether John or Kate are right, let’s apply a hypothetical design goal. For this game, your design goal is, “Create a fast-paced, beer-and-pretzel wargame that makes players feel like gung-ho, brawling berserkers”. To support this design goal, you’ve chosen your game’s factions not to represent disciplined regiments but rather barbarian hordes and battle-crazed Vikings. You don’t want people getting too bogged down with calculating perfect plays in this sort of game, you want pulse-pounding excitement that players don’t feel obligated to think too much about.

Clearly John’s mechanic supports this design goal. Making combat swingy and semi-unpredictable creates excitement, tension and thrilling comebacks against all odds. Having randomness be a significant factor in the outcome also prevents most players from planning too far ahead, because they decide to wait and see what happens after the first attack. This keeps the action moving far more than in deterministic games like chess.

Kate’s mechanic, on the other hand, is awful for the game. Kate’s fully deterministic design creates a cerebral, tactical experience that feels much more like playing chess. It encourages players to think carefully about their plays and do a lot of precise math. These calculations tend to reduce the impact of emotional moments, [as has been demonstrated in studies](http://www.nationalpost.com/story.html?id=8cf455d9-8634-4cb1-972f-03dd9621350b). Next time you're angry, try multiplying three-digit numbers in your head. You'll be amazed at how quickly your emotional state shifts.

# But isn’t this obvious?
You’d think so, but people gloss over it all the time. I’m one of them. Just the other day I wrote a short piece about improving the game of Rock, Paper, Scissors without being highly specific about my intended design goal; and it was clear after reading some of the comments that I had been far too vague in explaining the specific type of experience I was trying to create in my players (and why Rock, Paper, Scissors falls short of that experience in my view).

Also, it’s easy to get tied up in a lot of different factors that affect the experience. I’m working on a project right now where we’re redesigning significant portions of the game’s core mechanics, and are often torn between multiple factors. Choice A might do a better job of communicating the game’s lore through gameplay and feature additional strategic depth, Choice B might allow for longer and more epic struggles between warring factions, Choice C might take less micromanagement but won’t do nearly as good a job in the other factors…

… And then I remember our design goal is to create a fast-paced, explosive, visceral and cinematic strategic experience that takes less than 15 minutes per game. Choice B actually hurts the design goal, Choice A isn’t that relevant and Choice C’s reduction of micromanagement will help turns flow faster. Choice C it is.

# A Recent Example
A few months ago I was playtesting a PvP map for a strategic war game. I had played a lot of the campaign mode thus far, as I was designing a campaign mission at the time, but it was my first time trying a PvP map. However, the mechanics were almost identical to the campaign mode.

I played the map… And I hated it.

“This is absurdly slow-paced,” I protested to the mission’s designer, “The whole first round we just moved all our units closer to each other. It was a complete waste of ten minutes.”

“Okay,” he said, “But the people playing this mode enjoy that careful positioning and set up in round one. It’s chess-like, it foreshadows the coming battle on a tactical level, and it lets them slowly set up optimal engagements. Very focused on the competitive tournament scene here.”

“Oh. So PvP is Spike Mode, and the Campaign is Timmy Mode?”

“Exactly.”

“In that case, it’s awesome.”

If you haven’t heard of them yet Timmy, Johnny and Spike are the three player psychographics that drive Magic: the Gathering’s design. Each name represents a different kind of player, or rather a different motivation for playing a game. Because each psychographic enjoys a specific kind of experience, each one forms its own design goal.

I won’t go into the details here, because most of you are probably already familiar with the terms. If not, [Mark Rosewater has already explained them better than I ever will](http://archive.wizards.com/Magic/magazine/article.aspx?x=mtgcom/daily/mr220b). I highly recommend checking out this article if you’re not familiar, it’s full of fantastic and useful information for designing in a wide variety of games.

# Wrapping Up
All of us think in terms of design goals in some form or other. It honestly feels a bit weird to be talking about something that might seem so obvious. However, it’s easy to let a design goal slip by when you’re working on game. People either never articulate and agree on it clearly enough, creating intractable  arguments, or just forget to refer to it.

So here are my tips:

1. Write out your design goal as early as possible, and as specifically as possible, for everything you’re working on. Spend a full day clarifying your design goal if you have to, and get everyone’s buy-in. It’s well worth it in how much time you’ll save later by avoiding arguments and heading down the right path more often than not.
2. Write the design goal on a note card and tape it to the side of your computer. This comes from my playwriting days, when we were told to write out our mantra (the one sentence describing the play’s core message) and tape it to the side of our computers. Games are at least as difficult to keep straight as plays, and the advice is just as useful here.
3. Just as different chemicals are required to create a finalized chemical reaction, sometimes the design goals for specific elements of your design are going to be a bit different than the whole of your design. The design goal for an individual level might be different than the design goal for the whole game. Each of [Flower’s](http://thatgamecompany.com/games/flower/) critically acclaimed levels has its own emotional tone, but together they form an overall experience.
4. Whenever you can’t decide on some element of the game’s design, whether a mechanic, level layout, which texture to use or anything else - take a moment and refer back to the design goal. Remind yourself, and whoever you’re working with, what result your decision is trying to achieve. I’m amazed at how often this clears up the problem.

At the core, our job is the simple matter of figuring out what experience we want to provide and then making design choices that will provide that experience. I’ve been told it sounds profound to end articles with a quote, so here it is.

> “When a man does not know what harbor he is making for, no wind is the right wind.”
> <cite>Seneca</cite>

Hmm… Not sure it worked.

[Classroom]: ./classroom.jpg