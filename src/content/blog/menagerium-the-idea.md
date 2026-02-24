---
title: "Menagerium, the Idea"
description: "A personal project for D&D combat tracking"
pubDate: "Oct 20 2025"
heroImage: "/src/assets/iguana.jpg"
tags: ["hobbies", "tech"]
---

## Dungeon Problems require Modern Solutions

In 2025, I had the opportunity to try playing Dungeons and Dragons for the first time. I'd been curious about the game for some time but never had the chance to actually try it out for myself. One of my friends decided to try running a campaign, and we found that we had a lot of willing participants who would join as player, me included. When I find something I enjoy, I tend to hyper-fixate for some time, and so I found myself writing my own short campaign and leading a few sessions. After trying a virtual table top as well as playing with physical pieces and dice, I found that I enjoyed having a common map in the middle over everyone using their own laptop or tablet to view the game. That being said, D&D involves a good amount of overhead when it comes to combat, and a digital tool could come in handy to prep and run battles.

Thus, my idea to build one myself popped into my head. I didn't bother looking if an existing tool already existed, and so built out the MVP without knowing about [Kobold Fight Club](https://koboldplus.club/) or [Improved Initiative](https://improvedinitiative.app/e/). Enter the Menagerium.

## A new Quest

The first hurdle would be to think through the basic database tables that a project like this would require. I chose a relational database over noSQL, thinking that I could re-use things like attack actions and spells. Later on this would come back to bite me, but we'll get to that later. My main desire for this project was to allow users to browse and search through D&D creatures, and use the pre-defined stats to help run combat encounters. So the first few tables stored creatures, various actions they could take, and spells that could be used. I chose to use GraphQL since the creatures had a lot of details and I wouldn't need everything at once. TypeORM also would be useful to keep the DB up to date, and I wired up the various resolvers and services with NestJS. This would be the foundation of the application, and after building out the basic CRUD functionality I tested everything in Postman to double check it worked as expected. Next up would be the UI. Vue seems like a good option, once the basics are set up I'll link a post here for a follow-up.

[Update: The Prototype](/blog/menagerium-the-prototype)
