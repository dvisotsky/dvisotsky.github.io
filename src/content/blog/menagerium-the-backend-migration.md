---
title: "Menagerium, the Backend Migration"
description: "Open5e to the rescue and UI rework"
pubDate: "Mar 21, 2026"
tags: ["hobbies", "tech"]
heroImage: "/src/assets/balcony.jpg"
---

## Migrate, and migrate again

This project is getting closer by the day. After temporarily trimming out unneeded features that can be added after the MVP is done, I am able to focus on the more important aspects of the tool. In the [last update](/blog/menagerium-the-prototype.md) I mentioned that the relational database for storing actions, creatures, and everything else was growing too complicated and I'd need to migrate to a NoSQL database to gain flexibility. Well, the migration itself wasn't too bad. But it turns out I don't even need my own database in order to get an MVP out there. I came across[open5e](https://open5e.com/), an open-source resource for D&D 5th edition content, including a huge catalog of creatures. This is exactly what I needed to expand from my own seeded catalog of around 20 creatures to the hundreds provided in official D&D handbooks and manuals.

## MVP in sight

Now that I had a substantial catalog of creatures, I could focus on the actual user experience. Searching and filtering out creatures, dialing in the look of various creature types and combat ratings, and making the tool feel more like an actual catalog rather than a dev sandbox.

## Flipping tables

Typically when viewing large amounts of data, tables are the way to go. However I find the rows and columns of text a little dull to look at, and wanted to present the data in a more creative way. Enter the "Creature Card".<br/>
While it displays the most relevant data about a creature, it also provides a break from the wall of text that a table brings with it by displaying a procedurally generated image of the creature in question. Since there are thousands of creatures in D&D, it'd be nigh impossible to create an image for each. My solution is instead to focus on the creature types, of which there are 14. These give the foundational shape of the creature image, while things like color, stroke, background, and text color can hint at other aspects of this creature specifically.

<div style="display: flex; justify-content:center;">
    <img 
        style="margin: auto;"
        src="/src/assets/adult-dragon.png"
    >
</div>

The hope is that this will set the Menagerium apart from existing combat trackers and give users a more pleasing way to browse and search through the Creature Catalog.