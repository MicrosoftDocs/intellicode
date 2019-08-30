---
title: IntelliCode refactorings
ms.date: 08/28/2019
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
author: markw-t
ms.author: mwthomas
manager: jillfra
---
# IntelliCode refactorings (Preview)

IntelliCode refactorings improves your editing experience when you're making similar edits in many places in your code. It locally tracks your edits, detects when you are performing a repetitive action, and offers to apply that same action in other places you may need to do so.  For instance, if you are making a refactoring, and have missed locations where it could be applied, IntelliCode will help you find those locations and fix them.

   ![Video showing IntelliCode refactorings experience in Visual Studio](media/IntelliCoderefactorings.mp4)

As shown in the video above, opportunities to apply refactorings show up in the Visual Studio editor as a [lightbulb](/visualstudio/ide/quick-actions) in the editor, along with green [warning-level squiggles](/visualstudio/get-started/csharp/visual-studio-ide#popular-productivity-features), and warnings in the [error list](/visualstudio/ide/reference/error-list-window). The [code cleanup indicator](/visualstudio/ide/find-and-fix-code-errors?#run-code-cleanup) will also show any opportunities found in the current file. Clicking on the lightbulb displays a menu from which you can apply the change to the detected location.

Refactorings is aware of the semantic structure of your code. One advantage is it will detect cases where the variable names in your changes are different but the essential structure of the change is the same:

   ![Illustration of IntelliCode refactorings showing how repeated edits lead to finding other refactorings](media/refactorings-illustrated.png)

If you don’t like a suggested change, you can select the ignore option on the lightbulb and we won’t bother you about that pattern again unless you recreate it. 

## Enabling IntelliCode refactorings
Refactorings is a preview feature, so it is turned off by default. 
Go to the Tools-Options page, IntelliCode General tab, Preview features area, and switch C# refactorings to “Enabled” to turn it on:

  ![Tools-Options showing the IntelliCode General tab with refactorings turned on](media/refactorings-toolsoptions.png)

Once you change this setting, close any files you may have open, then restart Visual Studio.
