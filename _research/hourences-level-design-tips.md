---
layout: article
title: Hourences Level Design Tips
author: Sjoerd De Jong (Hourences)
source: http://80.lv/articles/10-rules-of-building-great-games-and-levels/
category: Level Design
---

# The Importance of Planning
![ ][Hourences Intro]
<cite>Works of Hourences from his official website (hourences.com) © Hourences, 2015</cite>

I think there are a lot of different and often very good ways to start a level and what you should do depends greatly on the kind of game you want to create something for, your own experience, and so forth. So there’s no ready recipe for that.

In general the most important thing is to think things through. Properly sit down and think about what it is you want to make. Especially if you are new to this. I do a lot by the flow, because I base what I do on previous experience and I know it will work out anyway, but if you are new to it – plan everything.

Whether you plan by just sitting down somewhere and thinking it through, or by drawing a plan, or by using Lego, it doesn’t matter. Just ensure you think it through in detail. Exactly what are you building? What are the potential problems you might face? What will make this special and unique and can you amplify that further?

# Sculpting The Landscape
![ ][Hourences Staircase]
<cite>Works of Hourences from his official website (hourences.com) © Hourences, 2015</cite>

I’ve used World Machine for one of the sections in [The Solus Project (TSP)](http://80.lv/articles/the-solus-project-unreal-engine4-interview/) but it didn’t help too much. Our landscapes are too specific and small for [World Machine](http://80.lv/vendors/world-machine/). I do use World Machine to generate distant mountains and landscape elements though. Works very well for that.

The way you should build the landscape depends so much on exactly what you build. You should of course always take the player’s camera angle into account. A real time strategy game with an overhead camera would see different things than a first person player of course, but other than that it is a very wide question.

I personally start out with nothing more than the landscape and sculpt it until it is about what I had in mind. Then I place the biggest rocks on buildings on top, and continue with sculpting the landscape. These objects give me a better understanding of scale, distance, composition and so forth.

# Style VS Reality
![ ][Hourences Asian]
<cite>Works of Hourences from his official website (hourences.com) © Hourences, 2015</cite>

A stylized look can be really cool, I love The [Walking Dead](https://www.telltalegames.com/walkingdead/) for example, but it is not my style. I like keeping it realistic, but at the same time I don’t want to make the real world. There is enough of that around us already, and if you do that you need to do it super well because everyone is going to compare you attempt at realism with what they know of the world. That makes it hard to pull off properly. Going more artistic solves that, and it is more fun also. It gives you a lot more possibilities to create something impressive and memorable.

# Don’t Confuse the Player
![ ][Hourences Cave]
<cite>Works of Hourences from his official website (hourences.com) © Hourences, 2015</cite>

I tend to place things carefully. Like a tree that fell down can create a line, a kind of border where it fell, so I will deliberately place these kind of things to create subtle barriers and lines where I need them to guide the players in the right direction. Even if people can just step over said fallen tree, you tend to recognize these kind of lines and borders and change your navigation accordingly.

Navigation aside there is also visual composition to keep in mind. You don’t want it cluttered with random elements, so I will place things to create balanced and varied yet not too varied areas. In TSP in particular also tend to place stone blocks in rows, statues, or blue ship debris to highlight certain directions or areas.

Look At The SkyThe skies in The Solus Project are all built by me from scratch. They are not actual skyboxes, but gigantic 3D skies. The planets you see are a million units across and actual 3D objects that orbit the world.

The first Unreal taught me that skies are crucial to the experience, so I have always put a lot of emphasis on making good skies. A sky should be varied, have a sense of scale, drama, and give a clear indication of where the light is coming from.

![][Solus 1]
![][Solus 2]
![][Solus 3]
<cite>Solus Project</cite>

The sun in general is crucial. I see a lot of people simply paint in a bright dot in the sky with a lot of bloom and be done with it, but I spend many days making my sun and it consists of many different layers of flares. The great majority of my sun has nothing to do with Bloom or Lightshafts or such at all, it is all done by hand, and I think people greatly underestimate the work you should invest in making the sun and the sky.

# Do Light Early On
![][Hourences Space]
<cite>Works of Hourences from his official website (hourences.com) © Hourences, 2015</cite>

I always do basic light early on, after I placed the majority of most important geometry, just to get a sense of space and feel for it, but after that I will hold off doing lighting until texturing and geometry is nearly entirely finished. You cannot do lighting if you don’t know what kind of colors your textures will have, so that must come first for me. Keeps development streamlined also by doing things in clearly divided steps.

Lighting has a major impact on gameplay, for example it can help or confuse the navigation of the player by highlighting or darkening the exit. It can make the player careful if it is dark, or it can make the player feel more stressed if there are for example a lot of blinking red lights, and so forth.

# Everything is Connected
In general everything has an impact on everything. If you build games you should always look at the entire picture and never do one thing independently of another.

# Optimize Your Scene
![][Hourences Factory]
<cite>Works of Hourences from his official website (hourences.com) © Hourences, 2015</cite>

A lot of students hit a problem with optimization for two reasons.

First of all they never really get forced to think about it, because a portfolio piece is almost always small in size, plus doesn’t has to run on a wide range of platforms and devices, so they never get to cover the optimization part of the job.

And secondly this is also something that just needs a lot of experience, which you don’t have if you start out.

I don’t really care if I can make one particular area look nice, that isn’t very hard to do, what I care about is if I can mass produce similar graphics and art throughout dozens if not hundreds of locations in the entire game, and done in such way that I never have to go back in and optimize it. So when I begin building something, I will immediately take into account everything that could potential slow either me, the player, or the hardware down further down the line and I try to cover as much of it as I can right away.

Think about the big picture, and think it through what could all end up being slow, and tackle it all before it is a problem.

# Guide The Player
I tend to create pockets of free space, followed by linear sections and bottlenecks. So you can explore freely in certain areas, but there is only one way out of each of those areas. I ensure the way out is always in a way special, for example the top of a hill, or near a large statue. So you can find it back and feel naturally inclined to go there, yet still have the opportunity to go elsewhere also.

If you look at a game like [GTA 5](http://80.lv/articles/gta-v-beats-skyrim/) which is pretty much entirely about trying stuff out and doing whatever you feel you want to do, that still has a very streamlined singleplayer experience build in as well I would say. So it is perfectly possible to combine the two, but it depends on the type of game on exactly how you are doing it.

# Technology Does Not Kill Creativity
![][Hourences Staircase]
<cite>Works of Hourences from his official website (hourences.com) © Hourences, 2015</cite>

If the technology becomes better you actually have less need for avoiding creative risk because you don’t have the tech to worry about and you can thus go all out on more creative games. I think that that is actually happening in a portion of the market because powerful and free engines like the [Unreal Engine](http://80.lv/vendors/epic-games/) create a new kind of niche market. It attracts small teams who don’t need a multi-million dollar hit game to survive, and thus those teams can focus on more creative experiences.

That said, there are of course also a lot of run of the mill kind of games being released, but I don’t think the tech is to blame there. What you we are dealing with in general is a games market that has exploded over the past few years.

10 years ago it was very hard to sell a game without a publisher, nowadays there are a 100 different ways of getting your game out there. That attracts a lot of people, and a lot more games get made because of that. That consequently also means you will have a lot more copycats, simply because there are so many more games and because it is so much easier to step into the market.

On top we have seen the mid tier developers disappear over the last couple of years, only to begin bouncing back up now. For a couple of years now we have been left with only some of the largest studios around, and those large studios can’t usually take the risk of doing something too new or creative due to the budgets involved. Budgets that are nowadays a lot higher than they were before, and games made for a market that has a million times more competition then 10-15 years ago.

Read the first post in our improvised series [here](http://80.lv/articles/the-solus-project-unreal-engine4-interview/).

[Hourences Intro]: ./Intro.jpg
[Hourences Staircase]: ./Staircase.jpg
[Hourences Asian]: ./Asian.jpg
[Hourences Cave]: ./Cave.jpg
[Hourences Space]: ./Space.jpg
[Hourences Factory]: ./Factory.jpg
[Solus 1]: ./Solus1.jpg
[Solus 2]: ./Solus2.jpg
[Solus 3]: ./Solus3.jpg