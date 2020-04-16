---
title: IntelliCode suggestions
ms.date: 04/08/2019
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
description: IntelliCode suggestions
author: markw-t
ms.author: mwthomas
manager: jillfra
---
# IntelliCode suggestions 
IntelliCode suggestions assists you when making similar edits in multiple places in your code. It tracks your edits locally, and detects repetition. It then offers to apply those same edits in other places where they might apply. For example, if you have missed locations where a refactoring could be applied, IntelliCode suggestions helps you find those locations and fix them.

You will see a lightbulb when IntelliCode detects a repeated edit and finds opportunities to apply it in your currently open documents. The lightbulb has an action which will show you a list of the suggestions found. This opens the IntelliCode suggestions window, so you can locate and act on the suggestions.

![IntelliCode suggestions discovery](media/intellicode-suggestions-discovery-and-toolwindow.png)

Suggestions show up in the Visual Studio editor as a [Quick Action light bulb](/visualstudio/ide/quick-actions), along with grey-dotted [suggestion-level squiggles](/visualstudio/get-started/csharp/visual-studio-ide#popular-productivity-features) and in the IntelliCode suggestions tool window, as shown in the screenshot below:

![IntelliCode suggestions lightbulb](media/intellicode-suggestions-lightbulb.png)

When you see a light bulb on a line of code with a suggestion, select it to display a menu from which you can apply the suggested change.

> [!NOTE]
> In Visual Studio 16.6 and newer, IntelliCode suggestions no longer show in the Visual Studio Error List; instead they are shown in the IntelliCode suggestions tool window.

## Changes IntelliCode can detect
IntelliCode is aware of the semantic structure of your code. That structure is used to detect situations where changes can be applied, even if variable names are different:

![Illustration of suggestions showing how repeated edits lead to finding suggestions](media/refactorings-illustrated.png)

If you don’t like a suggested change, select the **Ignore** option on the light bulb. IntelliCode won’t bother you about that pattern again unless you recreate it.

## Enable suggestions
Suggestions is turned on by default in Visual Studio 16.6 and newer.
If you wish to turn it off, choose **Tools** > **Options**, **IntelliCode General** tab, and then switch **C# suggestions** to **Disabled**:

After you change this setting, close any open files, and reopen them.
