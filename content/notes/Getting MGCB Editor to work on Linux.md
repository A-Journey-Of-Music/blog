---
title: Getting MGCB Editor to work on Linux
comments: false
---
To add media to your project MonoGame uses a proprietary file format to map the media to game entities. 
To edit the specified file, you need an editor, which runs in your project folder (!!!).
In your project folder, you have to run the following commands:
```zsh
dotnet mgcb-editor
```
If it doesn't work the first time, don't worry, because you have to run the obvious command of
```zsh
dotnet tool restore
```

If your output looks like this, you've succeeded!
![](notes/images/Pasted%20image%2020230225171434.png)

Now you can easily open it with the command 
```zsh
mgcb-editor
```
Or, in Jan's Case
```zsh
mgcb-editor-linux
```

![](notes/images/Pasted%20image%2020230225171754.png)

Great Success!!!