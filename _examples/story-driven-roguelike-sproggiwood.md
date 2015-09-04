---
layout: article
title: Story-Driven Roguelike, Sproggiwood
author: Jason Grinblat
source: http://gamasutra.com/blogs/JasonGrinblat/20150526/244216/Design_Postmortem_StoryDriven_Roguelike_Sproggiwood.php
category: Postmortem
---

# Introduction
Sproggiwood is a game about ambition and unintended consequences. Sproggi, a mischievous forest sprite, anoints itself Savior of Sprog and hatches a plan to bring order to its chaotic realm. But the task is much more complex than Sproggi anticipates—and the story of the civilization of Sprog is fraught with strife, frustration, and woe. It's hard to avoid thinking of Sproggi as a fledgling designer, who imagines a crisp, clean, beautiful vision for his realm without recognizing the uncountable complexities that underlie it. Upon learning more and more of the truth, Sproggi is forced to continually adjust its vision and its plan for achieving the vision. Now it must be said that Sproggi is a master of euphemism and will try at every turn to couch its own failure in pleasant rhetoric. For the integrity of this postmortem, I plan to be more candid than this little fiend.

![ ][Sproggi]

# Nice to Meet You
Hi, I'm Jason Grinblat, designer and writer for Freehold Games. In October 2014, after two years of development, we released Sproggiwood on Steam. In a few days, we'll be releasing the game on iOS and Android. Sproggiwood is a story-driven roguelike set in a world inspired by Finnish mythology. It's intended to distill the roguelike genre down to its most fun, core ingredients and serve them in a more accessible, more digestible dish. For us, those ingredients are procedurally-generated encounters, monster and player parity, and diversity of player choices. In the aggregate, they amount to emergent tactical gameplay, simple systems that combine to allow you to outsmart the game—or the game to outsmart you—in unexpected ways. Our goal was to roll this up in a narrative about the problematic nature of "civilizing" native cultures, chop it into short and punchy play sessions, and serve it to order.

![ ][Adventure]

In some ways, we were well-prepared to write this game—and in some ways, we were woefully unprepared. Freehold Games is a tiny studio of three part-time core contributors. Co-founder Brian Bucklew and I had spent the previous four years developing a more traditional, open-world roguelike called Caves of Qud.

![ ][Qud]

During the course of Caves of Qud's development, we plied the breadth of the roguelike waters: we built and rebuilt engines that could encapsulate the components of highly interactive environments; we fiddled with every slider that produces emergent gameplay; and we incorporated narrative elements rarely used in the genre. But though we had the roguelike essentials down, and we both had experience in the software industry, we were—and to some degree still are—game dev hobbyists. We had never launched a commercial game.

Thankfully, our third partner Jaana Heiska was an experienced game artist. Together, we were able to wrangle the scope of our ambitious first vision and deliver a smaller but well-crafted game. Working part-time meant that the journey through our revisions took longer than anticipated, but it also gave us enough room to ultimately land where we did.

# From Far & Wide, the Vision Evolved
> From hybrid town builder to dungeon crawler. From IAP to premium.

As is the often the case with fledgling teams, we started out with a more ambitious goal. We originally concepted Sproggiwood as a mobile, hybrid dungeon crawler and town builder. The original vision still sought to distill the roguelike essence to short, 15-minute play sessions that could be played on your phone or tablet. But we also wanted to tell a story about a civilization on the rise, and allow you to make meaty choices about the direction to take your village. Our conceit was "the town is your character"—and you would adventure in dungeons, in typical roguelike fashion, winning resources that could be used to expand your town. In town, you'd manage your villagers, assigning them to tasks such as planting crops, forging swords, or staffing trade posts. The output of your village would feed back into equipping your adventurers.

![ ][Buy]

Faced with the realities of the mobile market, we asked ourselves how could we maximize our chances for success with Sproggiwood in the effort to transition to full-time game development. The answer at the time was in-app purchases. We didn't know ourselves as well as we do now—and over the next year, we'd realize that the kind of game we aspired to make just doesn't align with that model. But at the time, IAP seemed like the answer.

As development progressed, two truths became apparent. First, we couldn't integrate the town and dungeon mechanics in a meaningful way. Each system was tangled up in its own complexity, and any bridge between the two was tenuous. Essentially, we were building two games on top of each other. We nailed some intriguing town mechanics: arranging villager pegs into a limited number of building holes; drawing from a deck of random seasonal events; building roads to route villagers as they worked. But each of these was completely divorced from our interesting dungeon mechanics, and we burned ourselves out in the attempt to convince ourselves that building two orthogonal games was compelling, practical, or wise.

![ ][Town Concept]
![ ][Cave Concept]

Two, IAP wasn't working for us. We were ham-fistedly quantizing our content into purchasable chunks that didn't match the path of progression we wanted for our players. Sproggi would explain how this is the result of an inherent flaw in the model, how it bleaches the soul out of otherwise soulful games. That's a bit harsh, Sproggi. I'm willing to chalk it up to my inexperience as a designer and the desire born in my hobbyist's heart to build something that I myself am excited to play.

# What Went Right

## 1. Bite-Sized Emergence
In my opinion, this was where we were exposed to the least amount of risk. This was well-trod territory for us, the bread and butter of Caves of Qud. Our paradigm is to design bite-sized, modular encounters that lend themselves to being combined in surprising ways. Some of these encounters are individual monsters and some are dungeon traps. For example, a slime puddle requires you to step on it within a few turns to prevent a new slime from spawning. A frog pulls you toward it with its tongue if you're nearby. When the procedural dungeon populator decides to combine these two encounters, you'll often find yourself pulled away from a slime puddle just as you were about to step on it. How devious combinatorics can be!

![ ][Vampire]

Adhering to a common roguelike precept, we often favor treating the player no differently than a monster and vice versa. Wily players notice when a frog is about to shoot forth its tongue, and they swap places with a nearby monster—saving themselves and damning the monster to a froggy demise.

These bite-sized encounters still work well in the absence of the other roguelike components that we stripped away—such as hunger, inventory management, and true permadeath.

## 2. Nailing the Feedback Loop
We grappled with this one for a while, and we didn't get there until relatively late in the dev cycle. Originally, you purchased powers for your adventurers in town. Once you entered a dungeon, your powers were locked and you could only augment your adventurer with equipment that you found in chests. On the back of bite-sized emergence, this was nominally working for us. In our feedback surveys—which we incorporated later in the process than we should have—the game reached about a 6.5/10 on the "compelling" scale despite a higher net promoter score. Essentially, players were telling us that while they would recommend the game, the gameplay wasn't as compelling as they expected.

![ ][Town Skills]

Fortunately, a savvy playtester pointed out that while they were accruing gold to purchase their next power in town, they didn't feel enough immediate reward while adventuring. Dungeon sessions were short, but the reward feedback loop needed to be even shorter. Here's where we came up with a new metaphor that would drive us to our final design. While each dungeon session served merely as a single adventure in the broader arc of your civilization, it could also encapsulate the entire arc of an individual adventurer. The player could earn levels in the dungeon and choose powers while leveling up. This could happen early and often—and in combination with other engaging dungeon features (treasure chests, shrines, potions, and scrolls), it would reward the player frequently and consistently. As it turned out, choosing the order of your powers as you level became an integral piece of the strategy for defeating dungeons—especially as they scale in difficulty.

![ ][Ninja]

## 3. The Personalities of the Player Classes
My favorite design task was concepting the player classes. Early on, I had the idea to borrow from the MOBA model of 3 powers plus 1 ultimate power to encapsulate a class. This jived with our aesthetic goal of fitting all the player powers onto one screen. It also gave players a number of small but powerful "toolbelts" for tackling dungeon encounters—each of which contained a totally unique set of synergistic tools. There's an art to capturing the essence of a class in just four powers, and I think we nailed it.

![ ][Icons]

## 4. The Duplicity of Adorable Art
Jaana is a tremendously gifted artist, and she pushed me and Brian in directions that we wouldn't have otherwise gone. She manages to create adorable art that's never cloying.

![ ][Sketches]

Her art contributed to our goal of making an accessible roguelike for a wider audience. Aside from drawing players in on its own right, it also allowed us to craft an experience of playful deception where players discover that the adorable art belies (a) the game's difficulty and (b) the darkness of its themes. Sproggi is quirky, mischievous, and cheerful—all characteristics that the art connotes—but the astute player sees through the playfulness and into the often grim enterprise Sproggi insists on undertaking.

![ ][Sproggi 2]

# What Went Wrong

## 1. Two-Year Development Time
This was a product of working part-time and starting with a vision that changed dramatically over the course of the project's life. If Brian, Jaana, and I were full-time, I'm confident we would have reached the final product much earlier. However, we'd also be under much tighter financial constraints, and I can't guarantee that Sproggiwood would have been profitable. (It likely wouldn't have been.) We had the relative luxury of hammering on the design until we were satisfied.

With Sproggiwood under my belt, I know I can shave time off future projects by starting with a more realistically scoped vision. A hybrid game of the type we originally concepted just isn't realistic for a tiny hobbyist team. I also have a better understanding of the market, and I know that we can ameliorate the risk of our "soulful" hobbyist endeavors by setting ourselves up to port our games to multiple platforms.

## 2. Subpar Town Mode
Sproggiwood retains a vestige of the former town mode, which it still uses as a mechanism to offer upgrades that span multiple dungeons. It's a storefront, albeit a very pretty one, that you can decorate as you please. Thematically, it's a win, since these global upgrades represent the advancement of your civilization, and they provide a backdrop for the monsters you capture to roam around in. Mechanically, players sense that something's lacking since so much artistic attention is paid to the town.

![ ][Town]

With more time to iterate, we might have built the hybrid game from our original vision. Failing that, we might have incorporated some lighter town mechanics that imparted more of a sense of the town's purpose.

## 3. Lack of Asymmetry in Item Design
From my perspective, this is a subtle one. It's a case of letting my designer hat squeeze the player perspective out of my brain. I designed a set of carefully balanced weapon and armor enchantments that could appear on the items for any class. The weapon enchantments are flaming (deals extra damage, comes in three tiers of variety with increasingly elaborate flame patterns), freezing (freezes enemies, three tiers, increasingly elaborate frost patterns), and vampiric (drains life, two tiers, increasing potency). The armor enchantments are systematized in a similar way.

![ ][Shop]

I spent a great deal of time working and reworking the designs of these enchantments, ensuring that they were balanced, tactically interesting, and variously desirable for different player classes. In one sense, this is a big win because it contributes tremendously to the balance of the game. That contribution is sort of invisible, and I'm okay with that. But games are more than just elegant systems—and in the roguelike genre, items in particular have a tradition of juicing up gameplay. Some players have noted that despite their multiplicity, the items feel samey. I don't blame them.

Now, my advice to myself would be: insert dashes of asymmetry into your design. Don't lose your way in the weeds of systemization. Asymmetry can disrupt the balance of your elegantly designed systems—but in the right doses, it can do so in memorable and thematic ways.

Fortunately, I took my my own advice—and in the latest version of Sproggiwood, we added rare class-specific items with totally unique enchantments. A grappling fork for the farmer! A staff of frogs for the wizard! This has juiced up our loot immensely without toppling the balance of the system.

![ ][Staff]

## 4. Buried Story and Symbolism
Ultimately, Sproggiwood is still a bit of a hybrid game. Wrapped around these systems of emergence is a mythological setting and a narrative about the collision of two civilizations. I love language—and while I appreciate the austerity of purely mathematical systems, my games will always include words. On the one hand, this lends a dimension to Sproggiwood that is rare for the genre. Exposing unsuspecting players to a strange narrative and its dark themes is rewarding. However, I'm a believer that your themes should permeate your design, and in this way Sproggiwood doesn't realize its full potential.

There is a conceit at work here. For players who are paying close attention, it might dawn on them that Sproggi is asking them to engage in some morally questionable endeavors. That realization might extend to their experiences playing other games. They might ask: who are these monsters that I'm slaying? What right do I have to loot their valuables? Why has the genre codified these actions into canon?

![ ][Chests]

Unfortunately, these questions lie too deeply beneath the surface of the game to ever take the thematic forefront. They exist—but the game fails to push them into the purviews of most players, so they're largely ignored.

# Conclusion
Conquering a rival civilization—and concealing your imperialist intentions in rhetoric—is a difficult task. Likewise is developing a mechanically novel, thematically rich hybrid game. If I were to reductively distill my experience into three nuggets of advice, I'd say:

1. Engage playtesters early and often and use surveys to track their feedback. We used [www.surveymonkey.com](). It’s important to include a subset of consistent questions across all your surveys so that you can objectively measure change over time. When you find particularly astute playtesters, jump on them and hit them over the head with more questions about their experiences. A good playtester will force you to rethink your assumption that your game has reached its apex.
2. Permeate your design with your themes. If you want to convey something, don't settle for burying it under the surface. Work the mechanics until they orient players in the right direction for asking the questions you want them to ask.
3. Insert bits of asymmetry into your systems. Break the even plane of systematization with an obelisk of "whoa."

Of course, all this advice is presumptive (especially the latter two points)—and if you think it's at odds with your goals, ignore it. But I would keep in mind that the systems underlying the experience you envision for your players are likely more multifaceted than you're giving them credit for. As designers, we've a tendency to smooth away those facets when we get lost in the glamour of our visions. In that way, maybe we're all a bit like Sproggi.

![ ][Sproggi 3]

[Sproggi]: ./sproggi.jpg
[Adventure]: ./adventure.jpg
[Qud]: ./qud.jpg
[Buy]: ./buy.jpg
[Town Concept]: ./town-concept.jpg
[Cave Concept]: ./cave-concept.jpg
[Vampire]: ./vampire.jpg
[Town Skills]: ./town-skills.jpg
[Ninja]: ./ninja.jpg
[Icons]: ./icons.jpg
[Sketches]: ./sketches.jpg
[Sproggi 2]: ./sproggi2.jpg
[Town]: ./town.jpg
[Shop]: ./shop.jpg
[Staff]: ./staff.jpg
[Chests]: ./chests.jpg
[Sproggi 3]: ./sproggi3.jpg