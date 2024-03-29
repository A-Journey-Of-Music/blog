---
title: First Steps with MonoGame
comments: true
disqus_title: First Steps with MonoGame
tags: 
- Game
- Blog
keywords: [MonoGame, Character movement, Keyboard input, Animation, MonoGame.Extended, MonoGame.Aseprite, Aseprite Editor, Sprite animations, MGCB Editor, Importing files, Documentation, Library integration, Game development, Cross-platform development, Programming, Coding, Learning, Development process, Project updates]
---
![](notes/images/Pasted%20image%2020230226174657.webp)
We can announce, that we have made first steps in MonoGame (literally!).

We can move the character up and down, left and right, by inputting the keyboard.
What we haven't figured out yet, but are now closer to it, is how to animate the player:
Today we took a look at [MonoGame.Extended](https://www.monogameextended.net/) only to find out, that it seems to be discontinued. We really don't know, so we tried [MonoGame.Aseprite](https://monogameaseprite.net/) as it is build for the support of Sprite Animations build by the [Aseprite Editor](https://www.aseprite.org/).
We successfully can now import `.ase` and `.aseprite` Files with the [MGCB-Editor](notes/Getting%20MGCB%20Editor%20to%20work%20on%20Linux.md).
We expect the first Animations to work tomorrow, after some fixing and reading the documentation :).

Furthermore, we do also plan to explain the process of adding libraries to the MonoGame project.

Added: For the Tilemaps, we are still in search of a capable library, because MonoGame.Extended uses features deprecated in recent MonoGame versions. 
For our Animations, we ended up, writing the code ourself. 