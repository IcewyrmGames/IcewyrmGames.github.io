---
layout: article
title: Black & White Postmortem
author: Peter Molyneux
source: http://www.gamasutra.com/view/feature/131476/postmortem_lionhead_studios_.php
category: Postmortem
priority: 2
---

# Introduction
_Black & White_ is the game I always wanted to make. From the days of _Populous_ I had been fascinated by the idea of controlling and influencing people in an entire world. I was also interested in the concepts of good and evil as tools the player can use to rule or change the world. These themes crop up regularly in my games, but I realize now that with every game I was heading toward my ultimate goal—the god game _Black & White_.

I wanted the game to be more flexible, more open, and more attractive than anything I'd ever played. I was determined that the player could do almost anything he or she wanted. Instead of leading players deeper into a world of levels and testing them with tougher and tougher monsters, I wanted players to be engaged by the story but to take it at their own pace and decide which bits to tackle and when to tackle them.

More technically, I didn't want a panel of icons or a set of on-screen options. With _Dungeon Keeper_ I felt we overdid the control panel, and, while it worked, it didn't add to the immersive sense of being this evil overlord deep underground. Frankly, it simply reminded you that you were playing a videogame.

Finally, I wanted to place into _Black & White_ the ability to select a creature (originally any creature from the landscape) and turn it into a huge, intelligent being which could learn, operate independently, and do your bidding when you wanted. I knew that this would require an artificial intelligence structure unlike any ever written. It had to be the best.

![ ][Black & White]
<cite>Lionhead Studios' Black & White.</cite>

Of course, I needed a team for all this, but I wanted the right sort of team and so had to build it slowly. A core team of about six was formed, and at the start of Lionhead we worked at my house. Our first task was to create a library of tools, so we spent our time there doing boring foundation tool-building.

We started work on the game proper when we moved into our offices in February 1998, at which time there were nine of us. By this time we had begun thinking about the game in general terms. We discussed what we could have in it, what we should have in it, and what, in a perfect world, we'd like to see. Funnily enough, much of the last category did in fact make it in, things such as the changing atmosphere and buildings if you change alignment between evil and good or vice versa. Also, ideas for some fully lip-synched characters were thrown around. At that time, we didn't seriously think it could be done.

![ ][Tortoise Concept]
<cite>Concept drawing for the tortoise Creature.</cite>

During the first year of Lionhead we added people gradually, as I was very keen for the friendly, family-style atmosphere of Lionhead to remain, and it takes a certain sort of person to fit in and enjoy working with such a close-knit team. This policy of only recruiting people whom we felt had the talent and a way of working which fit in with Lionhead's existing members meant that our team had evolved their own way of working. They didn't just carry out their tasks but questioned, tested, and pushed both themselves and each other. It's labor-intensive, but you often end up with more than you expected. For example, the art team divided up the tribal styles for the villages and tried to outdo each other in terms of design and effort put in. The result was better design work than we thought we'd get.

At Lionhead Studios, we all knew that _Black & White_ was going to be something special. This belief became self-fulfilling as we were inspired by each new feature and every neat, innovative section of code. Naturally, this meant that everyone worked exceptionally hard. Over the course of the project the team did the work of a group twice their number. We regularly went home as dawn broke, and weekends became something other people did.

# What Went Right

## 1. It got finished
This sounds stupid, but we encountered some big problems, and there were times when we doubted that the game (as it ultimately ended up) would get released. As a new company, we not only had to work out the game we were going to create, but we had to write the tools and libraries, create everything from scratch in software, and also gel together as a team.

We couldn't have a dress rehearsal for this, so we learned by trying things and then changing them if they didn't work. As time rolled on, we couldn't afford to make any mistakes or pursue blind alleys. For example, we talked about updating some of the graphics at one point. It didn't seem a big job, but once we'd changed some of the buildings in the tribal villages, they showed up any unchanged ones and made them look less impressive, so we had to assign time to do them all. We got a much better set of buildings out of this, but if we'd known that we'd have had to do all of them, we would have said, rightly, that there wasn't time.

The programmers were likewise coming up with neater and neater ways of coding, and thus trying to do more and more with the code they had. It says a lot about the talented and single-minded development team at Lionhead that everybody always wanted to make every element that little bit better.

And as we fixed the bugs and sent the game to QA, we felt like people who'd run a marathon and could see the finish line, but it didn't seem to be getting any closer. Perhaps this is a function of not getting enough sleep over a period of several months.

## 2. All the risks paid off
We wanted to do some pretty groundbreaking things in _Black & White_. One example was doing away with the panel of controls and using the Gesture system for casting Miracles. We tried and tried to get this feeling just right, and if we'd had to dump it, I'd have been so disappointed. But after research, testing, and simple trial and error we got it working beautifully, and we now have a feature no one else does.

Also, integrating the story line into such a free-flowing strategy game was a risk. We thought it would sit quietly behind the game, popping up to direct you if you hadn't moved on, but the story came alive and started to draw the player through the game in a way none of us, apart from perhaps scriptwriter James Leach, had envisaged. It also gave us characters such as Sable, the Creature trainer, and those advisors whom we hear people now quoting lines from, and who exist outside the game as recognizable characters.

The huge, learning, intelligent Creature was also more of a gamble than he now seems. To go into AI in such an in-depth way required Richard Evans, our AI programmer, to consider what learning was, how practice works, and how the reinforcement of ideas comes about. Then he built all this into a character which appeared to live and learn like, say, a clever puppy. AI is always a minefield, and I'm always disappointed by great strategy games which appear to have the most simple, easy-to-predict AI running your enemies. We just wanted to advance the technology to its extreme.

![ ][Creature Comforts]
<cite>Creature comforts.</cite>

We also wanted to do more with graphics and animation blending. The world changes depending on whether you're playing as a good or an evil god, and things take on subtle new looks. The Creature, the player's hand, and many of the buildings change, and we used more animation blending to achieve smooth movement and changes than anyone else has ever done, I believe.

We're also the first game (apart from Microsoft's _Flight Simulator_) which enables you to import real weather in real time into the world. We are also the first to enable unified messaging, whereby you can send messages to the web from the game, or receive them, using e-mail and mobile phones. This integrated two-way messaging as well as the ability to take your Creature out of _Black & White_ and onto the web is brand-new. Also, the game can import names from your e-mail package and assign them to unique villagers in your tribe in the game. I expect lots of games to do similar things in the future, but we took massive risks and devoted huge amounts of effort to being the first and to making it work properly.

## 3. The game looks so stunning
When we started, we used a wireframe test bed and a couple of conceptual screenshots to provide some atmosphere. I first showed the test bed and these mocked-up screenshots to the press at E3 in Atlanta in 1998, and I could see on the assembled faces that nobody believed we could accomplish anything like it in the final game. I was complimented on the depth and beauty of preliminary efforts, but the compliments had a slightly hollow ring. I could almost hear people thinking, "Yeah, it looks great, but anyone can draw pretty screens using an art package. What's your game really going to look like?"

![ ][Horny]
<cite>Concept art featuring Horny from _Dungeon Keeper_ — a great deal to live up to.</cite>

Not only did we manage to pull off the look we wanted, but we exceeded it by some margin. The sheer beauty of the lands is something I hope won't be matched for a while, and the fact that you can move, zoom, and rotate to view it from any angle, anywhere in the game, is again something we got spot-on.

Looking back, I don't know whether we were insanely ambitious, because at the time we started, you couldn't have done what we did. We needed so much custom-written software, and we also needed the minimum specification of the PC community at large to get better before this would be viable. When we started _Black & White_, most people had 32MB of RAM in their PCs. The game requires 64MB, but that's commonplace now. So, if you like, we aimed beyond the horizon, and the world rotated and caught up with us so we still hit our target.

I still have those original screenshots, and I still like looking at them. We wrote a book called _The Making of Black & White_, and from reading that, it's clear that we went from a bunch of bizarre ideas linked by the concept of supreme control to the best game I have ever seen.

![ ][Final]
<cite>The final product.</cite>

## 4. The artificial intelligence
The Creature AI, as I have mentioned, is absolutely spot-on. Richard Evans worked tirelessly on this, and it became something that surprised even him with its flexibility and power. The AI isn't just restricted to the Creature. Every villager in the game has it as well, and they are all different in their wishes, desires, motivation, and personality. Because there is no upper limit to the number of villagers you can have, we had to cap the AI slightly by giving some of the villager control to the Village Center, which acts like a hive and farms out some of the cooperative elements to the people. We couldn't have them interrogating each other, so this central control means that they do work as a unit but can retain their individual characteristics. This makes the game much faster and still gives them minds of their own.

The Creature himself is an astonishing piece of work. Once he starts learning, he forms his own personality as he goes, and no two players will ever have the same Creature. The complexity is kept to a minimum to keep him fast, but we managed to steer completely clear of using random elements to make him seem like he has a mind of his own. And there is nothing in the game that you can do which you can't teach your Creature to do. It's true to say that the Creature mirrors you and your actions, so in _Black & White_ we've got a game in which part of the game itself learns from everything you do and tailors itself to you.

## 5. The way the team came together to make _Black & White_ happen
This is Lionhead Studios' first project, and everything started from scratch. The people, the software, and the working environment were all new. Although this was exactly what we needed to do a game so fresh and diverse, it also created problems which I was delighted to overcome. The lack of any precedent meant that things took a lot longer than they should have, and the open-ended nature of the game throughout much of its development meant that team members were limited only by their own imagination.

But the nice thing is, every member of the Lionhead team gelled brilliantly, and although I know we picked the very best people, there is an element of luck in whether they can all work together so well. We certainly lucked out with the team, and every one of them contributed massively to making the game what it is.

The last few months of the project were the hardest any of us has ever had to work, but thanks to the people, they were also some of the most fun months we ever had. If nothing else, we'll always remember the time we spent closeted together making _Black & White_.

And I'll never forget that without the right team, this game never would have happened. It's as simple as that.

# What Went Wrong

## 1. Planning the story
We underestimated how long it would take to construct and write the story element of _Black & White_. The free-form nature of the game required an unfolding tale to give it some structure and lead it to a conclusion, and in October 1999 we began to work on the story. We thought it would take no more than two months, but after a while we realized that we didn't have the skill set needed to take care of this vital aspect of the game. I contacted James Leach, who'd been the in-house games scriptwriter at Bullfrog and had worked on _Syndicate Wars_, _Dungeon Keeper_, _Theme Hospital_, and many others. He was working as a freelance ad copywriter but gladly came on board, again in a freelance capacity, and turned our ideas into a fully plotted story line, wrote hundreds of challenges and quests, and wrote all the dialogue in the game. It ended up being more than 60,000 words, the size of a novel.

Hiring James meant that we got a sense of continuity, consistency, and style throughout the game. It also meant that we could describe what we wanted, or even write placeholder text, and he would rapidly turn it into finished work. Sections of the game that were still at an early stage seemed more easy to understand, get a feel for, and work on when we used dialogue and text which seemed, to us, finished. Of course, another pass was usually needed to make it accurate and sometimes to polish it, but having a dedicated scriptwriter made this a simple task.

Storytelling in games, as elsewhere, is an art. If a story line flows easily and naturally, that's because someone has worked incredibly hard at it. I'm a great believer in the emotion and immersion that can be added to a game through good story and dialogue. It can't make a bad game good, but it can make any game better. And when the script was looked at by Hollywood scriptwriters and film directors from the BBC, we knew we were on to a winner.

Another by-product of using a professional scriptwriter was that we morphed the in-game advisors, the good and evil guys, from being just sources of information and guidance into stylish, popular characters who are now bankable properties in their own right.

![ ][Citadel]
<cite>The Citadel.</cite>

## 2. Fixing the bugs
After canceling our Christmas party on December 26, 2000, we managed to hit Alpha, which as any developer knows is a very loose definition, but at least we could say that all the game features were now locked. After a well-deserved Christmas break, we came back to find that we had more than 3,000 bugs. We had six weeks to reduce this to zero, but the thing about bug-fixing is that you can solve one problem but in doing so create three more. So although we worked as hard as we could, the overall figure crept down slowly rather than dropped at the rate at which we were actually sorting out the bugs.

![ ][Micromanage]
<cite>We tried to make the micromanagement of the villagers as user-friendly as possible.</cite>

By this stage the team was very tired. The only things that kept them going were the sense that the end was in sight and the fact that they could now play the game and actually experience what we had created. Bugs, of course, could have killed the game, so there was no way around it but to fix each and every one. We had bug lists circulated to every member of the staff, and we put up a chart on the wall which was updated daily. Some days we had more bugs than the day before, and that was like looking at a mountain which was growing quicker than we could climb it. But there came a moment three weeks into this process when we felt we'd broken the back of the major bugs, and the numbers fell steadily. Of course, the irony was that the last 10 bugs were the hardest to fix, and with every one there were four more created. It was as if the game just didn't want to be finished and perfected.

## 3. The project was too big
_Black & White_ got to be so large that we almost felt lost within the code. In fact there are well over a million lines of code within the game. Loading up even the most simple of the smallest tools would take many minutes, and compiling the entire game took over an hour. This meant that toward the end of the development phase even a tiny change could take a whole day to implement.

Checking in changes and rectifying errors was a nightmare. We eventually decided to limit the checking-in to one machine, and we implemented a buddy system whereby nothing was done without an onlooker checking it at every stage. This put a stop to tired people checking in changes at four in the morning and finding that, instead of fixing something, they'd actually caused further problems.

Another worry about the project's size was that we didn't think the game would fit on one CD, although we were desperate for it to do so. The audio files are immense. Music, dialogue, and effects are all compressed, but of sufficiently high quality that we refused to reduce them any further.

And with 15 language versions to get translated and recorded, we had to do the biggest localization job I've ever seen. This landed on Lionhead Studios at the very busiest time, and although our publisher did an excellent job of handling it, we were needed to check and answer questions and to provide explanations for some of the more arcane elements of the game.

## 4. Leaving things out
The idea of the game didn't really change much over the course of its creation. But I do have some regrets that features we thought would be great proved unworkable. I expected this, as it happens with every project, but I thought the problems would be caused by software or even hardware limitations. In fact, it came down more to emotional issues.

For example, the original idea of the Creatures was that a player could choose to make any living thing a Creature. We wanted the player to be able to select an ant and grow that, or a human being from a tribe, and raise him or her. Christian Bravery, one of the artists, spent a long time drawing concept work and sketches depicting what the Creatures could look like at various stages of their development. This of course included humans.

We soon realized that people would have certain expectations from a human. Players wouldn't expect a turtle to learn as quickly as a man, but if we dumbed down the people, they'd seem like a proto-hominid race from eons ago, and we didn't want that. Also, discipline in the game involves slapping your Creature. We certainly couldn't have the player slapping a child or a woman or, really, even a grown man. The emotional feel of raising a human, teaching him or her to eat what you want, and leading him or her around in a speechless environment was all wrong.

![ ][Details]
<cite>The game's underlying detail is immense but never overwhelming.</cite>

Christian's work in visualizing humans as player Creatures was all for nothing in the end, and we dropped the idea. We also dropped the notion of turning any living thing into a trainable Creature, as ants, butterflies, fish, and other nonmammals would have caused big problems. A flying Creature would change _Black & White_ into a totally different game.

I also regret that we couldn't use color as a dynamic concept a little more. The landscapes in the game are gorgeous, and our sound and music man, Russell Shaw, suggested that various spells could drain the color out of areas, or spread different colors around. We liked this idea for its surrealism, and we thought about having color wars with other wizards (at this stage you weren't a god, you were a wizard battling others on a land). The idea lost momentum when we thought about how the land would actually look, and how it would seem like something drawn by a preschooler. I still like the idea of color wars, but I think children's TV has also cottoned on to the idea, which means we won't be going there.

## 5. Talking about release dates
I have to admit, ruefully, that I have a reputation for being, shall we say, optimistic about when the projects I'm working on will be completed. I opened my big mouth and announced that Lionhead Studios would finish _Black & White_ and get it released at the end of last year.

I just can't resist talking about whatever I'm currently working on. This has been a problem I've experienced with every game I've ever developed. But the thing is, when I think something is going to be finished in December, I really do believe it. People at Lionhead were telling me that we had to build in time for bug-fixing, and I knew this was true, but the truth is that there seems to be no formula for working out how long things will take. The best thing to do, I guess, is to take the finishing date I first think of and move it twice as far away—and then not announce it until we're halfway there.

It's a function of working on products which could literally be endless. Unlike a film, where once the footage is shot, you edit it with an idea of where you'll end up, you can add completely new features to a game and then balance it and change it radically right up until the last minute. I'm sure that there were many people who didn't believe me when I said we'd finished making Black & White and were only convinced when they saw a box with a CD in it.

# "Just More"
_Black & White_ is unlike any other game ever written. That was our goal, and we achieved it. We wanted something more beautiful, more complex, more emotive, more innovative, more clever, and more, well, just more.

As you've read, it was beset by problems. We nearly drove ourselves crazy solving them. Nothing worthwhile is ever simple, though, and for every minute spent thinking up wonderful ideas to include in the game, there were probably 20 hours of sheer hard effort trying to get them to work.

People told Lionhead we were perfectionists, but if we were, the game would never have been finished. It's not a perfect game. Our next game won't be, either. But because there's no such thing as a perfect game, we'll just try to do something different, and do it as well as we possibly can. Someone asked me recently what drove us to work so hard on this and to spend so much time thinking outside the box. The simple truth of my answer only struck me afterwards. With _Black & White_, we made the game that we wanted to play.

[Black & White]: ./black-white.jpg
[Tortoise Concept]: ./tortoise-concept.jpg
[Creature Comforts]: ./creature-comforts.jpg
[Horny]: ./horny.jpg
[Final]: ./final.jpg
[Citadel]: ./citadel.jpg
[Micromanage]: ./micromanage.jpg
[Details]: ./details.jpg