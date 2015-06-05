---
layout: article
title: Designing an RPG Inventory System That Fits
author: Robert DellaFave
source: http://gamedevelopment.tutsplus.com/articles/designing-an-rpg-inventory-system-that-fits-preliminary-steps--gamedev-14725
priority: 3
---

# Introduction
Our hero is preparing to take on a vicious two-headed Ogre, whose sole purpose in life is to smash the capital city into utter oblivion. With backpack firmly in hand, our potential savior forks over enough Gil to purchase 100 hi-potions. Only there's one problem: the 100th won't fit, which seems odd considering he can stash another 99mid-potions.

The point of our little tale is that RPG inventory systems are usually not based in reality, nor should they necessarily be. The best designers are constantly placing themselves in the shoes of their target audience, developing systems that capture the spirit of their game without hampering the end-user experience. Finding that delicate balance between ideal design and the context of the game world at large is the key to developing a killer inventory framework.

# The Basics: Tried and True RPG Inventory Systems
One of the clearest paths to becoming a solid game designer is to learn from the triumphs and failures of others. That being said, before designing your own RPG inventory system it is imperative that you at least familiarize yourself with the most widely accepted practices.

Now, that doesn't mean you're pigeon-holed into using one of the ensuing schemes—quite the contrary. If anything, you should study them, learn their strengths and weaknesses, and perhaps use them as a template for your own innovative design.

## The Classic JRPG Inventory or the "Rule of 99"
One of the first true inventory systems to be widely implemented by RPG developers, inventories based off the "Rule of 99" are most commonly associated with classic JRPGs such as Final Fantasy VI, Chrono Trigger and early entries into the Pokemon series. The design paradigm behind this system is exceedingly simple: players can stash an innumerable amount of items in their inventory, but only a fixed number of each. And while that fixed number is typically 99, it can just as easily be 50, 100 or 1,000. Also, the "Rule of 99" inventories are typically universal, meaning that they're shared between all party members.

![ ][FFVI]
<cite>Final Fantasy VI: The "Rule of 99" in its heyday.</cite>

### Advantages
- __Low design risk:__ The "Rule of 99" inventory system effectively eliminates the need for micromanagement. As long as players can afford an item, storing it will rarely pose an issue.
- __Easily scalable:__ Re-balancing a "Rule of 99" inventory system is hardly a laborious process. Case in point: By changing the number 99 to 200 in code, you'll have effectively doubled the size of your game's inventory.
- __Easily implemented:__ Along the same lines, inventories rooted in static quantities are exceedingly easy to implement, and shouldn't eat up valuable development time.
- __Sorting and filtering:__ Developers have a myriad of options available at their disposal to handle sorting and filtering.

### Disadvantages
- __Searching:__ Regardless of how many filters you implement, navigating through a sea of items can be inconvenient and frustrating.
- __Realism:__ The "Rule of 99" makes no practical sense whatsoever.
- __Item value:__ The only real design limitation of the "Rule of 99" is that helpful items (such as buffs and potions) shouldn't be overly powerful in relation to enemy strength—not when you can store so many of them. One solution is to ensure that potent items are priced accordingly, so that the player can only purchase them selectively.
- __Non-visual:__ The "Rule of 99" inventory system often feels antiquated, largely due to a lack of visuals. Walls of text are so 1994.

> Design Tip: Inventories of this type are designed to allow players to carry as much of a single item as they deem necessary. By lowering the 99 to, say, 10 you would force players to begin managing their resources more effectively. If that's what you're going for, fine—just be aware of it.

## The Weighted Inventory
Weighted inventory systems have gained a great degree of popularity in the past decade, largely due to the growth of the Western RPG. Games like Fallout 3 and Oblivion have made exemplary use of the system, harnessing it to add an extra layer of depth.

In this system, each item or piece of equipment is assigned a numerical value that represents its weight. And, as you might have guessed, items that are perceived as heavier are assigned a higher value than those perceived as lighter. For example, a rocket launcher may carry a weight of `20` whereas a first aid-kit may only warrant a `1`.

Characters can only carry a certain amount of weight before experiencing the ill-effects of burden or fatigue, which may ultimately cause them to walk slower or gradually lose health. Alternatively, the game can disallow the character from going over the allotted weight limit entirely.

![ ][Fallout 3]
<cite>Fallout 3: Apparently our hero has no problem carrying over 10,000 bullets.</cite>

### Advantages
- __Resource management:__ The need to manage resources effectively becomes apparent, without necessarily ever becoming a huge burden.
- __Realism:__ Weighted systems add a degree of realism not present in the "Rule of 99" system.
- __Implementation:__ Weighted systems are nearly as easy to develop as "Rule of 99" systems. However, they do require a bit more design creativity.
- __Sorting and filtering:__ Again, weighted inventories are just as flexible as "Rule of 99" systems are in regards to sorting and filtering, if not more so.

> Design tip: If you go with a weighted inventory system, it's critical that you allow players to sort items by weight.

### Disadvantages
- __Balance:__ A great deal of playtesting is required to ensure that players can carry the "right" amount of inventory. Allow them to carry too much and the game loses depth; too little and they'll constantly be suffering from fatigue.
- __Item dump:__ Sifting through items, trying to find ones to throw away can be cumbersome and frustrating, more so if the system isn't properly balanced.
- __Item value:__ An item featuring a weight of `2` (hand grenade) might be far more valuable than one carrying a weight of `20` (steel pole). Designers are therefore restricted in how many low level items can boast powerful stats.
- __Non-visual:__ Weighted systems are usually text-based, and do little to enhance the visual appeal of the game.

One design idea that you may want to explore is that of a hybridized weighted-banking system. Combining the aforementioned weighted system with MMO-style storage, players would be encouraged only to carry items they deem as essential to the next leg of their journey, and store the rest in a vault or bank for later use. Using this system, the amount of item dump would be reduced dramatically. It would also allow for greater design flexibility.

## The Visual Grid
Popularized by action RPGs like Diablo 2 and survival horror games ala Resident Evil, the visual grid inventory system is just that: players have a specific number of slots in which to house items, represented visually by a rectangular grid. Visual grids are also popular in modern MMOs such as World of Warcraft and Star Wars: The Old Republic.

Instead of being assigned a weighted value, equipment and other inventory items are sized accordingly. For instance, a broad sword might be three grid slots high and one wide whereas a short battle ax would be two high and two wide. Other, non-rectangular item compositions have led gaming fans to liken the system to playing a game of Tetris.

![ ][RE4]
<cite>Resident Evil 4: Anyone up for a mini-game of Tetris?</cite>

### Advantages
- __Visual:__ Due to its visual nature, resource management is a relatively intuitive process. Visual systems are also more appealing to the senses than weighted or "Rule of 99" frameworks.
- __Drag and drop:__ Because inventory is represented graphically, players can move items from one locale to another with ease. Identifying items is less of a chore than it is with "Rule of 99" or weighted systems.
- __Realism:__ Visual systems are pseudo-realistic. Size is just as much a determining factor in how much one can carry as weight is.

### Disadvantages
- __Arrangement:__ Rearranging items so that you can free up one or two more inventory slots can be a chore, especially if they're shaped like Tetris pieces.
- __Size balancing:__ Smaller grids require players to either item dump or make more trips to the vendor. On the other hand, the larger the grid, the less realistic and harder to explore they become.
- __Stash:__ Due to their finite nature, implementing this system will almost also require your game to feature a stash or banking system. That is, unless you keep the number of inventory items strictly limited (better for survival horror RPGs).

> Design tip: The idea of Tetris shaped inventory items, while interesting on paper, was scorned by gamers and has since been all but abandoned. If you're dead set on designing a visual system, I'd recommend using rectangular items only.

## Realistic
Realistic systems are generally preferred in rouge-likes, some survival horror games, and games designed to be excruciatingly difficult. Dark Souls comes to mind.

All of the aforementioned systems can be used as a template for the realistic model. There's only one caveat: Whatever system you use, the amount of storage must be severely limited. Why? The answer is simple: in real life, people can't carry very much.

That being said, if you go with a "Rule of 99" inventory system for your realistic game, item scarcity and intelligent placement is a must. That, and each item should be extremely valuable to the player. If the decision whether or not to consume a potion now or later is not painstaking, then the game designer didn't do his or her job.

Due to their real-world confines, realistic inventory schemes are the least flexible, and require careful design.

![ ][Dark Souls]
<cite>Dark Souls: To gain humanity now or later, that is the question.</cite>

# Determining the Right Inventory System for Your RPG
Now that you're familiar with a variety of popular RPG inventory systems, its time you started designing your own. Well, not exactly. In order to determine which model, or concoction of models, is best suited for your game, you need to answer some preliminary questions. Oh, and I also recommend that you design another system first—more on that in a bit.

Hey, no one said becoming a designer is easy (if they did, don't listen to them). But by following the rules of stepwise refinement, determining a basic template for your RPG inventory system should be as easy as fitting 99 Bronze Armors into a knapsack.

- __What RPG sub-genre does your game fall under?__ Let's start with an easy one. Kick things off by identifying your RPG's primary sub-genre. Doing so will lead you in the right direction. For instance, high fantasy-based JRPGs where the real-world rules of logic and reason don't necessarily apply lend themselves to the "Rule of 99" system. Conversely, weighted systems are best suited for gritty Western RPGs set in worlds that obey certain real-world parameters.
- __Determine the role inventory will play in your game.__ If emerging triumphant in battle consistently relies on the usage of healing items, thrown weapons and consumable buffs, then either a "Rule of 99" or visual grid that allows item stacking is probably the way to go. On the other hand, if the strategic use of resources is an immersive facet of gameplay, a weighted system might prove more applicable.
- __Begin breaking down your inventory assets into categories.__ Remember when we said that you should first design another system before tackling inventory? Just like a suitcase is valued by what goes inside of it, RPG inventory design is dictated by its eventual contents. Thus in order for inventory design to become a much more intuitive, streamlined process, I encourage you to first design your inventory items. Let's see how.

## Designing Inventory Items From the Top Down
Here's where I like to use what we technical junkies call _top-down design_. Top-down design is a relatively simple concept that tasks designers with looking at the big picture first, and then drilling things down into their constituent parts. In the case of inventory items, we start by breaking our game assets into two categories (inventory vs. non-inventory assets) and work down from there.

- __Which game assets types will be displayed in inventory and which will not?__ For instance, weapons, armor and consumables should almost always take up inventory slots. Ammo and one-time use special items may not. What about items that your characters have equipped? Will they be included as part of your inventory or person? By answering the aforementioned questions, you'll be able to readily deduce which items belong in your inventory, and which can be placed elsewhere or remain hidden.
- __Departmentalize inventory asset types.__ Begin systematically pairing down inventory categories by type. Start at the top; doing so will allow you to more readily pair down general types into sub-categories. It's also a good way to predict the sorting mechanisms your inventory system will need to employ. High-level types may include weapons, armor, accessories and consumables.
- __Do it again, and again.__ Consumables can easily be broken down further into restorative items, items that inflict direct damage, and items that provide buffs. From there, restorative items might be further sub-categorized into healing items, items that remove status effects, and items that mimic the effects of an inn.
- __Assign individual inventory items' statistics.__ Once you've reached the point where you can't drill down your categories any further, list the assets that fall under each category and assign them stats.
- __Determine asset availability.__ Differentiate between assets that are sold by vendors (if any) and those that can only be found in either chests or on the corpses of the vanquished. If your assets falls into the latter category, determine each asset's rarity. Designers can justify overpowered items, as long as they're appropriately rare.
- __Count the number of total inventory assets in your game.__ Simple enough.

Now that you've designed your game's inventory assets—congratulations on that, by the way—we can resume our discussion on inventory system design.

Picking up right where we left off, the next facets of inventory design to consider are:

- __Usability:__ When determining how often inventory items, particularly consumables, will be used, look no further than your hero party's perceived battle efficacy. This will dictate their reliance on items. For example, in 16-bit RPGs, party members take a righteous beating, necessitating the constant use of potions and healing spells and, in turn, the "Rule of 99" inventory system. Other games implement more advanced healing schemes, such as "Life on Hit" or "Regen", which reduce item reliance. (That said, these games tend to clog up player inventories with equipment instead.)
- __Quest functionality:__ How does your questing system function? Games like Diablo 3 make use of Waypoints, which allow players to travel back and forth to town with relative ease. Thus, resource management becomes less of  an issue—although the constant trips to the vendor can be annoying. Skyrim, on the other hand, sees your hero traveling great distances en route to his or her destination. Items are therefore more scarce, but still plentiful enough that players must weigh their decisions carefully. The "Rule of 99" system wouldn't work in Skyrim, because it would make the game too easy and also reduce player immersion.
- __Is your party comprised of a single character or a collective group?__ Weighted inventories function more intuitively in games featuring one protagonist, whereas the "Rule of 99" is best suited for party-based play. Visual grids can function in both settings.

![ ][Diablo 3]
<cite>Diablo 3: Waypoints allow players to sell their crappy loot whenever they please.</cite>

> Note: A few party-based RPGs have tried to pull off individual inventory systems and, although these attempts were ambitious, most players quickly grew frustrated with them.

Don't be surprised if this process leads you to conclude that your ideal RPG inventory system doesn't fit neatly into one category. There's no such thing as a catch-all system. That's why it's up to you to determine which template or hybridization of templates works best, and to base your design on that. From there, you can tweak your preferred inventory system so that its inherit flaws become less apparent, always keeping in mind the end-user experience.

# Conclusion
At their best, RPG inventory systems are functionality intuitive and make sense within the context of your game-world. At worst, they're a source of frustration that can disrupt your game's delicate balance. In this segment we outlined a design process you can implement to prevent that from happening. To help you decide, here's a flowchart you can follow to pick one system as a starting point.

![ ][Flowchart]

[FFVI]: ./ffvi.jpg
[Fallout 3]: ./fallout-3.jpg
[RE4]: ./re4.jpg
[Dark Souls]: ./dark-souls.jpg
[Diablo 3]: ./diablo-3.jpg
[Flowchart]: ./flowchart.jpg