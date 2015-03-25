---
layout: post
title: Windows 10 Universal App Platform & Caliburn.Micro
---

Yesterday Microsoft released the [Windows 10 Technical Preview tools](http://dev.windows.com/en-US/windows-10-developer-preview-tools). I've finally managed to get a chance to test out Caliburn.Micro on the new platform and can quickly talk about building these apps using Caliburn.Micro.

### Installing

Out of the box Windows 10 can use Windows 8.1 assemblies with no changes so using the Windows 8.1 version of Caliburn.Micro will work. Just carry on as you normally do and add a [nuget reference](https://www.nuget.org/packages/Caliburn.Micro/), Visual Studio 2015 will use the Win 8.1 assemblies in the package (and checkout out the new nuget UI at the same time).

The nuget package does add a reference to the Behaviours SDK as part of the install. It appears this SDK has been rolled into the platform so this reference will fail, you can remove it. However Caliburn.Micro still needs those assemblies, by default they reside at the path below so you can add manual reference and things will run fine.

`C:\Program Files (x86)\Microsoft SDKs\Windows\v8.1\ExtensionSDKs\BehaviorsXamlSDKManaged\12.0\References\CommonConfiguration\Neutral`


### Platforms
Because the platform picked the Windows 8.1 assemblies to reference we don't have access to any specific Windows Phone 8.1 functionality which is currently limited to the `INavigationService.BackPressed` event. 

Releases of Caliburn.Micro that specifically target this platform will correct this.

### The Future
Overall this new platform won't have a major impact on Caliburn.Micro has it's incredibly similar to Windows 8.1. We will need to add some new functionality to make use of the new controls such as `SplitView` and the like and I'm really looking forward to being able to announce Caliburn.Micro running on an Xbox.

You can follow progress on this at [GitHub](https://github.com/Caliburn-Micro/Caliburn.Micro/issues/141).