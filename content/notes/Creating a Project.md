---
title: Creating a Project
comments: true
disqus_title: Creating a Project
tags: 
- Game
- Tutorial
keywords: [MonoGame project, Template, Arguments, Project folder, dotnet new command, TemplateID, Project name, Fedora, mgdesktopgl, AJourneyOfMusic, MGCB Editor, Linux, Getting MGCB Editor to work on Linux, Linux development, Game development on Linux, Cross-platform game development, Programming, Coding]
---
To create a MonoGame project, you have to navigate into your project folder and fill this template with the correct arguments:
```zsh
dotnet new <TemplateID> -o <ProjectName>
```
For Jan, the solution on Fedora being:
```zsh
dotnet new mgdesktopgl -o AJourneyOfMusic
```

To read, how Jan got the MGCB Editor to run on Linux, read [here](notes/Getting%20MGCB%20Editor%20to%20work%20on%20Linux.md).