---
title: How to find and replace by example
description: Use IntelliCode find-and-replace by example to perform complex find/replaces without needing to author your own regular expressions.
ms.custom: SEO-VS-2020
ms.date: 07/26/2021
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
author: markw-t
ms.author: mwthomas
manager: jmartens
---

# How to find and replace by example

Find and replace can be used to do some refactoring operations but, except in the simplest cases, these require you to write a complex regular expression.  Fortunately, Find and Replace by example can create those regular expressions for you just using samples of the before and after state you desire. What's more, you don't need to understand regular expressions to use it - Visual Studio generates one or more possible expressions and lets you preview the changes that would happen if you applied that expression in a find/replace.

## Providing an example of before-and-after
All you need to do is provide an example of the desired state before and after, right in the find and replace fields. 

You can do this in both the [find and replace control](/visualstudio/ide/finding-and-replacing-text?#find-and-replace-control) and the [find and replace in files dialog](/visualstudio/ide/finding-and-replacing-text?#find-in-files-and-replace-in-files).

Once a pattern is found, Visual Studio will let you know by showing a lightbulb next to the replace field in the find/replace control; clicking on that lightbulb shows the detected set of pattern matches in a list. Hovering or navigating through that list shows a preview of the changes it would make, and you can simply hit enter to commit the suggested regular expression and use it in find/replace as if you had written it yourself.

>[!NOTE] 
>TRY IT NOW: 
>You can try out the example below right away, by cloning [this repo](https://github.com/markw-t/NewFtoC) and opening Program.cs

In the program.cs file you'll find multiple examples of a hardcoded formula like this:

![Find replace by example code before](../media/intellicode-frbe-before-code.png)

Suppose you wanted to replace all of those with a call to a helper function like this on the same variable name:

![Find replace by example code after](../media/intellicode-frbe-after-code.png)

Remembering that there are multiple locations to replace with multiple variable names.

All you need to do is simply provide the examples shown below in the find and replace boxes, whether in the [find and replace control](/visualstudio/ide/finding-and-replacing-text?#find-and-replace-control) or  [find and replace in files dialog](/visualstudio/ide/finding-and-replacing-text?#find-in-files-and-replace-in-files) - the examples below use the control.

![Find replace by example find box and replace control populated and suggestions found](../media/intellicode-frbe-suggestions-found.png)

Once you do so, the lightbulb icon will appear next to the replace box to let you know that Visual Studio has found pattern based find/replace options for your case. 
1.	Click the lightbulb to reveal the possible patterns Visual Studio has detected for you
2.	Pick one from the list of possible patterns – you can preview the effect of each pattern by selecting it in the list

![Find replace by example list of suggestions found](../media/intellicode-frbe-suggestions-list.png)

3.	Select by pressing enter or clicking - your chosen match will now be used in the Regular Expression find/replace and you can navigate/act as usual for find/replace to change instances in your document and beyond. If the choice turns out not to be what you needed, you can always get back to your original search via the lightbulb - just choose "Original Text" from the popup menu.
