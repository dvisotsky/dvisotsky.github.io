---
title: "Development Environment"
description: "My toolkit for productive software development"
pubDate: "Jul 08 2025"
tags: ["tech"]
---

## Closing the Gap

Ask a carpenter or framer about their preferred tools for the job and you'll hear about different brands and tools that all have the goal of cutting and combining pieces of wood in different ways.
Ask a photographer about their worfklow and you'll hear about the pros and cons of different focal lengths, aperture settings, and editing software-- all for the end result of capturing a moment.

Every professional has their toolkit and workflow to achieve the best result they can. I've even heard that there is more than one way to skin a cat, however that's one skillset I'd rather not know the details of.

As a software engineer, I've also been dialing in my preferred methods of building software.
Thankfully, switching tools in my field is much easier than those that use hardware. In most cases I can simply install a new tool, or build it myself, instead of swapping entire battery ecosystems for power tools or camera brands for lens compatibility. The investment cost is lighter, and it encourages me to try different things out of curiosity.

The end goal is to close the gap between the idea dreamt up in my head and the experience that users have when they use the final product. The idea has a few layers to travel through before it makes it to the end user, and I'll discuss these in sequential order.

## Layer 1: Keyboard

The first layer is the computer keyboard. It's the only physical medium I'll be covering here, as it's had one of the biggest impacts in my workflow. Any thought or question I have must be inputted as text into the computer, and this requires the idea to travel through my fingers into the keyboard, which in turn passes the collection of scan codes into the system. Perhaps this interface will change in coming years as AI and speech-to-text systems continue to improve, but as of writing this article it remains the best way to transfer my ideas into the computer.

My delve into custom keyboards began with the desire to feel more comfortable switches and see better looking keycaps. Comfort while typing is a tangible improvement, and aesthetics serve to put the mind at ease while working. Out of the two, comfort is far more important in my opinion, and so my keyboard journey took me across a variety of form-factors. I've tried 60% keyboards, then wandered down to the 40% space, then down to 35% where I find myself typing now. Contesting the validity of such a small form factor deserves its own article, but for now I will defend it by recalling the importance of comfort. I've found that a keyboard where all keys can be reached without moving my fingers off the home row helps me stay dialed in. Furthermore, custom keyboards enable me to define a key map that caters to my preferences. Each key now has 2 or three functions, spanning from the base function of inputting a character, to text navigation, media control, and macros. While there is a learning curve associated with such customization, I get to decide how steep it is and how far I want to stray from conventional keyboard layouts. Currently I still use QWERTY instead of a more optimized layout like Colemak, mostly due to having settled into Vim keybinds and having no desire to juggle two layouts when switching from a custom layout to the standard that most of the world uses. For more content on why someone would willingly remove keys from their keyboard, check out the [40s wiki](https://40s.wiki/en/why).

## Layer 2: Operating System

This is the foundation for all of your code. Scheduling processes, allocating memory, mediating every file read and write, and handling every network connection your software makes. After it's selected and configured, it ideally fades into the background, the silent Atlas that holds up everything you load up on top. My opinion is that if you think about your OS throughout the workday, perhaps it isn't running as it should. My preferred choice has been Linux for some time, most of my time has been spent in Ubuntu. Recently though I've tried out CachyOS, and haven't looked back. Package management is substantially improved, I'm thankful to leave behind flatpaks and snaps in favor of AUR. With recent updates, the desktop environment space has also felt quite modern, with GNOME feeling almost Mac-like with its touchpad gestures and workspaces. Although I enjoy the keyboard focused approach of tiling window managers like i3, I have not yet dedicated the time to make it my full-time window manager. There is a fine balance between customizability and ease-of-use, and i3, along with its cousins, tend to hang out on the side of blank canvases that require a good chunk of time to flesh out so that the desktop environment doesn't feel half-baked.

## Layer 3: Code Editor & Peripherals

This layer is a menagerie of tools and extensions that I've found myself coming back to over the years. VSCode is the linchpin and it's what I use to write the majority of my code. It has been the standard for web development for a long time, and even now new editors like Cursor and Windsurf use it as a backbone. The catalog of extensions make it even more robust and relevant in all kinds of development settings. My favorite extensions are these:

**1. Vim**<br/>
I am still intimidated by a terminal-only coding environment, so using it as an extension on VSCode is the perfect compromise. I retain the power of Vim keybindings, visual mode, and macros, and on top of that I can still use VSCode's AI tooling, file navigation, and built-in terminal. The learning curve is definitely worth mentioning, but now that I've scaled the initial slope, I prefer Vim whenever possible.

**2. Prettier**<br/>
One of the most downloaded extensions out there. The name is self-explanatory, it makes your code prettier by formatting it using either a standard config or your own preferences.

**3. Gruvbox Theme**<br/>
If you couldn't tell by the color scheme of this blog, Gruvbox is my go-to palette. The warmth of the desaturated colors is inviting and I find myself coming back to it time and again after trying other popular colors schemes like Dracula or Monokai, although [Catpuccin's](https://catppuccin.com/) pastels are also high on my list.

VSCode captures the majority of what I need in order to build out a web app, however there are some peripherals that help push the process along.

**Git**
If the code editor is where ideas take shape, Git is where they're tracked, tested, and trusted. I use Git from the terminal the majority of the time. After setting up [aliases for commands](https://www.eficode.com/blog/10-levels-of-git-aliases-beginner-to-intermediate-concepts) I find it faster than using a GUI, especially when the terminal is built into my code editor.
The habit worth mentioning here isn't just using Git, it's using it intentionally. Commits are documentation, and a history full of messages like "fix" or "update ui" is technically version control, but practically useless. A well-written commit message is a small act of kindness to whoever touches the code next — including you, six months from now, wondering what you were thinking. [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) is a great standard to adopt early; it brings consistency to commit messages and plays nicely with automated tooling down the road.

**Obsidian**
For documentation, note-taking, and writing articles, [Obsidian](https://obsidian.md/) is the endgame. Local-first notetaking means that I don't need to worry about cloud subscriptions, although I do use [SyncThing](https://syncthing.net/) to keep things up to date between my devices. Obsidian lets me link notes within notes, write in the familiar Markdown format, and even use Vim keybindings. The community plugins are also worth mentioning, they range from simple QOL addons to powerful indexing tools that let you query and organize notes with SQL-like queries.

There isn't much else a developer needs in order to get things shipped. An argument could be made for other tools like Postman or DataGrip to improve the backend experience, however I consider these non-essential since endpoints can be tested in other ways and databases can be managed directly with their respective query language.

If you've made it this far, you're clearly the kind of person who thinks carefully about their craft — and that already puts you ahead.

Worth noting: you won't find any mention of monitors, desk setups, or ergonomic chairs here. My goal has been a workflow that fits on a single laptop screen and travels with me wherever I go. The best setup is the one that works where you are.

None of this is prescriptive — the right toolkit is whatever closes the gap between your idea and the finished product. What matters is that you stay curious and keep iterating. A tool is only as good as the person wielding it, and the best engineers are those who rely not on the perfect development environment, but their own expertise, experience, and will.
