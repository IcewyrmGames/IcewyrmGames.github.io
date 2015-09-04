---
layout: article
title: Darkest Dungeon's Affliction System
author: Chris Bourassa
source: http://www.gamasutra.com/view/news/244480/Game_Design_Deep_Dive_Darkest_Dungeons_Affliction_System.php
category: Deep Dive
---

# Who: Chris Bourassa, creative director and artist, and Tyler Sigman, game designer and executive producer
We had been circling around the idea of doing a game together for years, but we were busy with other studios and start-ups. We’d get together and brainstorm various ideas, but the one we were most captivated by was Darkest Dungeon.

Both of us freed up in the spring of 2013, and we decided it was now or never, so Red Hook Studios was born. We were excited by the chance to work on a game that had no external compromises--something purely made by us, for us, the way we wanted it to be. We were willing to bet that if we did that, there would be a decently sized niche audience that would also like it and thereby support the business.

Over the course of the game’s development, we built up a team of experienced collaborators to help make the game a reality. Right now we have six full-time people working on the game, plus our sound (Power Up Audio), music (Stuart Chatwood), and narration (Wayne June) contractors.  Both of us have enjoyed the small-scale production, where limited resources breed creativity and force hard decisions.

# What: Modelling an adventurer's mental health with the Affliction System
The ability and skill to fight is only half of the equation. What if a hero was unwilling to fight?

Darkest Dungeon is about the psychological toll of adventuring. The centerpiece of this is the Affliction System. As heroes adventure, their stress levels build. This is presented in game as a stress meter on each hero. When the stress meter reaches 100, heroes face an Affliction check.  If they fail the check (which is common), they manifest a temporary condition of reduced effectiveness -- an Affliction. Afflictions are different ways that people respond to stress.

![ ][DD Main]

Heroes can become selfish, abusive, hopeless, paranoid, afraid, masochistic, or just plain irrational. The different afflictions cause a wide variety of different game behaviors. For example, a selfish hero may take treasure for themselves, a hopeless hero may give up fighting, and a paranoid hero may become convinced that the other party members are enemies.

Sometimes, a hero will pass the Affliction check. This puts them in an incredibly useful Heroic state, where they may inspire the other team members or fight at increased effectiveness.

To reduce stress, you need to give heroes time off between missions and let them unwind in the ways that people do: drinking, gambling, meditation, prayer, and more. However, there are limited slots in town for each activity, and each hero has their own personal preferences on what they like. This becomes a bit of a board game in terms of trying to make the most of R&R between quests.

The Affliction system puts the player squarely in the role of a team manager, squad leader, or hockey coach. To be successful, you need to consider the human factors on the way to accomplishing your goals. Push heroes to their limit, and they will break mentally.

# Why?
We’re big fans of RPGs, ranging from classic old games like the Bard’s Tale series, Eye of the Beholder, Ultima Underworld, etc., on up to Diablo, Dark Souls, and contemporary MMOs.

However, many RPGs lose sight of the human element. Situations are presented as purely a player’s choice whether to face down a terrifying monster with only 1 HP left. We started asking: how would the hero feel?

In addition, we wanted to make something that stood in stark contrast to the "loot pinata" style of RPG. To be fair, some of those are done incredibly well, and we’ve clicked and right-triggered to the best of them, but they rely on a huge amount of procedural loot generation and the game becomes all about finding the next larger sword.

Taken together, those considerations led us to focus almost exclusively on the sword arm, not the sword. More specifically, the ability to fight is only half the equation. What about the willingness to fight?

# The Human Response to Stress
Although we are obviously influenced by Lovecraft in terms of tone, we never really thought of things in the strict “insanity” filter that many Call of Cthulhu games adopt. In fact, the inspiration for the Affliction System itself was not Lovecraft, but rather the role of human factors in history and fiction. Wargames have often incorporated human factors (morale), and many movies have illustrated them to great effect (Aliens, The Thing).

We wanted to capture the human response to stress. Any person can break under pressure, and people break in different ways. Some people become angry and abusive, whereas others become withdrawn and hopeless. However, moments of extreme pressure and high stakes are also what drive meaningful heroism. The strongest of us shine when everything is on the line!

Because we were focused on the human response to stress, we also had to consider how people reduce stress and settle back into normal behavior. Just as people respond to stress differently, they also recuperate in different ways. Some people need a drink; others need spiritual centering.

We felt that building a fantasy dungeon crawling party with these ideas in mind could result in some interesting -- and volatile -- adventuring.

# The Stress Meter
Although we wanted parts of the Affliction system to be purposefully opaque at first glance, we realized early on that we needed to completely expose the Stress meter and display stress increases and decreases directly as numbers -- for example, +20 Stress!

We ended up with a straightforward Stress Meter, and while this presentation is something we initially tried to avoid, the meter provides a tangible thing for players to try and “game.” This is a good thing: It provides clear feedback and consequences, while still allowing an organic narrative to develop. When taken in context of the unpredictable ways in which Afflicted heroes can behave, complex (and often tragic!) situations can develop.

![ ][Stress]

# Afflictions and the Affliction Check
Stress mounts organically during adventuring through critical hits, dealing with curiosities, party interaction, and more.  The Affliction Checks -- which determine whether the hero becomes Afflicted or Virtuous, are big moments and can really have a dramatic effect on the outcome of a quest.

Since drama is the name of the game, we sunk additional time and effort into the presentation of these moments. A banner announces that a hero is being tested, and after a (very tense) moment, the result is revealed in a fullscreen splash!

![ ][Hopeless]

Each affliction has different effects in combat, camping, and exploration. While there can be some positive effects (e.g. an Abusive hero gains a damage bonus), Afflictions are generally bad! Afflictions reduce your heroes’ capabilities and also make them challenging to manage because the hero will frequently act on their own. This might not be so bad if a hero decides to attack on their own and you wanted them to do that anyway, but it can cause serious problems if a greedy hero opens a trapped chest, or a masochistic hero refuses to be healed.

We want to put you in uncomfortable situations where you do not have complete control of your party. This is a central pillar of the game, and all mechanics are designed to reinforce it. We toy with player agency, constantly reminding you that these little digital heroes have minds of their own and sometimes their desire for survival (or a heroic death) will trump whatever you had planned. We want you in the role of a squad leader, trying to make the most of your soldiers and tackling hard decisions about who to sacrifice and who to save.

In contrast to the transparency of the Stress meter, we purposefully don’t list all the behaviors that any given Affliction may have. We want you to have to observe and react to your hero as it happens. Of course, you can build up awareness over time by playing the game. In this way your time and veteranship are rewarded.

The behaviors themselves were designed, as much as possible, by holistic consideration of the Afflicted states. For example, “What would a fearful hero do in combat?” They’d back away, they’d occasionally be too terrified to attack, and when they would attack they likely wouldn’t be hitting at full accuracy and vigor. “What would an abusive hero do in combat?” They’d bark at any failings of their allies, they’d hit enemies with an uncontrollable rage, and so on. Then, of course, there is the grab bag “Irrational”, which can do... you guessed it... any combination of the other Affliction behaviors.

# Barks
In addition to the behaviors themselves, we needed to pay off the heroes’ personalities by having them comment on their situation and actions. That’s one of the key ways in which we remind the player that what really matters is how the heroes feel, not how the player feels.

![ ][Barks]

We’ve invested a great deal in the barking system -- we have the ability to write custom barks for every class-plus-affliction combination. This way we can have a Selfish Grave Robber sound different than a Selfish Bounty Hunter. It was important to us to inject additional personality into the hero classes by exploring their personalities and alluding to their backstories in their speech. The more you play a certain class, the more you will learn of where they’ve been, and how they look at the world.

The barks also act as behavior signals -- almost every Affliction act out is preceded by a contextual bark. We also show the Affliction symbol above the hero’s head to illustrate that they are behaving on their own instead of under player control.

# Virtues
Sometimes, despite the odds, a hero can rise to the challenge, shake off their stress, and rally themselves and their party to fight on! Passing an Affliction check allows a hero to enter a temporary "Virtued" state.

![ ][Virtues]

There are currently five types of virtue: Stalwart, Courageous, Focused, Powerful, and Vigorous. Virtues are purely positive and can make the hero herself more effective, and sometimes even enhance the overall party. Having a hero pop Virtuous in the middle of a nasty fight can be a huge moment, and for as much as we like to focus on human fallibility and beat the player down... the heroic reversals are what memorable adventures are built on!

# Town Activities
We had a great time designing the stress recovery system. There are six different activities in town where you can “install” heroes and let them drain off stress. The slot system is intentionally very boardgame-like, and we pay off the game’s theme with the various side effects that can occur and the way we present the stories in the Activity Log.

Of course, just as people are fallible, some of their “hobbies” are fallible, too -- Flagellation and Drinking, for example. We get a great deal of satisfaction from reading angry tweets about how somebody’s favorite hero went on a drunken bender and left town, leaving them with a gaping hole in their roster! (SPOILER: The heroes always come back, eventually.)

And to add a little unpredictability, we let the Caretaker occupy spots in town randomly. This is a funny little side-narrative. He is equally happy in the abbey or the brothel.

# Quirks
Whereas Afflictions are major, temporary conditions, we also wanted to represent the little ways in which people have weird tendencies or special skills. These are our Quirks.

![ ][Quirks]

Quirks come in positive and negative flavors and can range from “Hagiomania” to “Nervous.” Each quirk affects some manner of gameplay. Some are simple stat buffs, but others play into the town metagame. For example, a hero with “Known Cheat” is banned from Gambling in the Tavern and will therefore have to look to other entertainment to reduce their stress.

Quirks can be removed by treatment in the Sanitarium. Surely they use humane methods in there... don’t they?

# Affliction History
Finally, another small mechanic that came about organically from observing human behaviour is the Affliction History. People tend to react to stress in ways that are individually consistent over time. A person who panics as a deadline approaches tends to fall into that comfortable panic again when the next deadline comes around. To pay this concept off in-game, we track each hero’s history, and over time they tend to fall into the same Affliction patterns. This supports our goal of building a small emergent narrative for each hero.

Fighting back the horrid abominations from outer spheres is gruelling, stressful work! A lifetime of blood and battle takes a toll on even the most hardened hero, and we felt it was time for an RPG to acknowledge that.

> “Have you met Reynauld, the paranoid Crusader with a gambling problem and the runs? He’s your new front-line tank.”

![ ][DD Logo]

[DD Main]: ./dd-main.jpg
[Stress]: ./stress.jpg
[Hopeless]: ./hopeless.jpg
[Barks]: ./barks.jpg
[Virtues]: ./virtues.jpg
[Quirks]: ./quirks.jpg
[DD Logo]: ./dd-logo.jpg