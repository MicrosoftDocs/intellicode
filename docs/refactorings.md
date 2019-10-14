---
title: IntelliCode refactorings
ms.date: 09/12/2019
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
description: IntelliCode refactorings - non-AB update version for TOC at 16.4 P1 onward
author: markw-t
ms.author: mwthomas
manager: jillfra
---
# Refactorings - Suggestion Level (preview)
IntelliCode improves your editing experience when you're making similar edits in multiple places in your code. It locally tracks your edits, detects when you're performing a repetitive action, and offers to apply that same action in other places where you may want it. For example, if you're making a refactoring and have missed locations where it could be applied, IntelliCode helps you find those locations and fix them.

![Refactorings illustration](media/intellicode-refactorings-message-level-noprompt.png)

As shown in the screenshot, opportunities to apply refactorings appear as a [Quick Action light bulb](/visualstudio/ide/quick-actions) in the Visual Studio editor, along with grey-dotted [suggestion-level squiggles](/visualstudio/get-started/csharp/visual-studio-ide#popular-productivity-features) and message-level entries in the [Error List](/visualstudio/ide/reference/error-list-window). By default, Visual Studio doesn't show messages in the Error List. To display them, select the blue Messages icon in the toolbar at the top of the Error List. When you see a light bulb on a line of code with a suggestion, select it to display a menu from which you can apply the suggested change.

> [!NOTE]
> Prior to Visual Studio 2019 version 16.4 Preview 1, refactorings were shown as warning-level entries. 

## Changes IntelliCode can detect
IntelliCode is aware of the semantic structure of your code. It detects situations where the variable names in your changes are different but the essential structure of the change is the same:

![Illustration of refactorings showing how repeated edits lead to finding other refactorings](media/refactorings-illustrated.png)

If you don’t like a suggested change, select the **Ignore** option on the light bulb, and IntelliCode won’t bother you about that pattern again unless you recreate it. 

## Enable refactorings
Refactorings is a preview feature, so it is turned off by default. 
To turn it on, choose **Tools** > **Options**, **IntelliCode General** tab, **Preview features** area, and then switch **C# refactorings** to **Enabled**:

![Tools-Options showing the IntelliCode General tab with refactorings turned on](media/refactorings-toolsoptions.png)

After you change this setting, close any open files, and then restart Visual Studio.
