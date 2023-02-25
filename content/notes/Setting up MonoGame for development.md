---
title: Setting up Monogame for development
comments: false
---
Before any Game could be implemented, there is a setup for the development environment todo. Of course you could just follow the [Setup-Guide](https://docs.monogame.net/articles/getting_started/0_getting_started.html) at MonoGame's website.

# Setting up MonoGame for Linux
Jan's choice of an operating system consists of Fedora Workstation for his laptop and Windows for his desktop gaming pc. As development is mainly done on his laptop he followed the [Linux-Guide](https://docs.monogame.net/articles/getting_started/1_setting_up_your_development_environment_ubuntu.html) for setting up MonoGame.

## Install .Net 6 SDK
As MonoGame is based on Microsofts Mono and XDA libraries you have to install [.Net 6 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/6.0)
## Install Visual Studio Code
Of course you can get any Code-Editor to somehow work with MonoGame, but for Jan [Visual Studio Code](https://code.visualstudio.com/download) was the obvious choice, as it is tightly integrated with MonoGame.
Here you can also add plugins to support your development:
1. C# extension ```
```zsh
code --install-extension ms-dotnettools.csharp
```
2. MonoGame Content Builder ```
```zsh
code --install-extension mgcb-vscode.mgcb-vscode
```

## Install MonoGame templates
There are additional templates and tools available you can install via CLI:
```zsh
dotnet new --install MonoGame.Templates.CSharp
```

> [!info] Optional
> On Linux you can install Wine and a tool by MonoGame to better compile effects. Jan opted for not installing it yet

To read how Jan set up our game, read [here](notes/Creating%20a%20Project.md).
