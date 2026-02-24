---
title: "Menagerium, the Prototype"
description: "Adding a UI, and planning a DB migration"
pubDate: "Nov 09, 2025"
tags: ["hobbies", "tech"]
---

## Pushing buttons

Since [my last update](/blog/menagerium-the-idea), the Menagerium file base has grown. There is now a front-end built in Vue and Typescript, sharing types with the back-end to make development easier and reduce type issues.

Building these pages reminded me how picky I am about user experience, but it was also a good exercise in prioritizing the big pieces and coming back to touch up the details later.
I found myself tinkering with colors and margins and had to pull myself back into scaffolding out real features. So far there is a functional search page for Creatures, Spells, and Actions, as well as forms to create new entities. The axiom is the Combat Encounter feature though, allowing users to track health, status effects, and turn order as well as view the details of creatures in the combat and takes notes on players.
The UI is not perfect, however I feel like the project is still in the scaffolding page and I'll have to live with it being simply functional for a time.

![Combat Creation Page](/src/assets/combat-creation.png)

There remains a few features to flesh out, and the relational database is starting to show its flaws. The rigidity of referencing an existing attack or creature inhibits the ability to customize things, and so I am debating migrating to a NoSQL approach to allow users greater flexibility when creating new creatures and the actions they can take.
Currently, actions are capable of scaling damage and other stats based on the creature's size or abilities, however I'd like to break the relationship between the tables completely, instead creating a copy of the action and storing it within the creature so that the user can tweak it to their liking without affecting the original entity. This principle would apply to spells and creatures themselves as well, allowing users to customize a creature's stats when creating a combat encounter in order to better fit their players.

Hopefully my next post will hail me a genius and tell you how easy and beneficial the migration was. Let me dream.
