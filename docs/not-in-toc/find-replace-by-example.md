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
All you need to do is provide an example of the desired state before and after, right in the find and replace boxes. You can do this both in Quick Find and Find/Replace in files dialogs.

Once a pattern is found, Visual Studio will let you know by showing a lightbulb in the find/replace dialog; clicking on that lightbulb shows the detected set of pattern matches in a list. Hovering or navigating through that list shows a preview of the changes it would make, and you can simply hit enter to commit the suggested regular expression and use it in find/replace as if you had written it yourself.

>[!NOTE] 
>TRY IT NOW: 
>You can try out the example below right away, by cloning [this repo](https://github.com/markw-t/NewFtoC) and opening Program.cs

For example, suppose you wish to replace all instances of methods in a file that have a signature like this:

![Find replace by example code before](../media/intellicode-frbe-before-code.png)

With a signature like this (changing doubles for decimals)

![Find replace by example code after](../media/intellicode-frbe-after-code.png)

There are multiple method names to replace.

All you need to do to accomplish this is simply provide the examples above in the find and replace boxes

![Find replace by example find box and replace box populated and suggestions found](../media/intellicode-frbe-suggestions-found.png)

On doing so, the lightbulb icon appears next to the replace box and lets you know that Visual Studio has found pattern based find/replace options for your case. 
1.	Click the lightbulb to reveal the possible patterns Visual Studio has detected for you
2.	Pick one from the list of possible patterns – you can preview the effect of each pattern by selecting it in the list

![Find replace by example list of suggestions found](../media/intellicode-frbe-suggestions-list.png)

3.	Select by pressing enter or clicking - your chosen match will now be used in the Regular Expression find/replace and you can navigate/act as usual for find/replace to change instances in your document and beyond.
