---
title: VS Code Completions
description: Learn about IntelliCode code autocompletions in Visual Studio Code.
ms.custom: SEO-VS-2020
ms.date: 09/26/2023
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
author: aayim
ms.author: aayim
manager: andster
---

# IntelliCode Completions for Visual Studio Code

The [IntelliCode Completions extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.vscodeintellicode-completions) predicts up to a whole line of code based on your current context. Predictions appear as grey-text to the right of your cursor. This extension supports Python, JavaScript, and TypeScript.

![IntelliCode Completions for Python in Visual Studio Code](media/wlc.gif)

For users of [C# Dev Kit](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csdevkit), IntelliCode completions are available for C# in VS Code through a separate extension: [IntelliCode for C# Dev Kit](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.vscodeintellicode-csharp)

## How to use
![IntelliCode Completions interpreting IntelliSense completion list selection in Visual Studio Code](media/intellisenseSelection.gif)

Completions will appear after your cursor as you type, with a faded color. When the IntelliSense list is open, its selection is used to inform the whole-line autocompletion.

At any time you can accept the suggestion by pressing the `TAB` key (you will need to press it twice if the IntelliSense list is visible). If you don't want to accept the suggestion, you can just keep on typing or press ESC.

### Snippet Completion

![Accepting a grey text completion with empty string automatically moves the cursor to the empty string](media/vsc-wlc-snippetcompletion.gif)

If the whole-line autocompletion includes empty strings:

1. The cursor will automatically move to the first empty string upon accepting the prediction with the `TAB` key.
2. If further empty strings exist within the prediction, pressing the `TAB` key again will automatically move the cursor to the next empty string.

## Installation

The extension can be aquired at the following link: [IntelliCode Completions extension for VS Code](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.vscodeintellicode-completions)

The extension is supported by Visual Studio Code November 2021 Release 1.63 or later.

## Provide feedback

If you encounter a problem, you can browse [existing issues](https://github.com/MicrosoftDocs/intellicode/issues) and upvote them using a 👍 "thumbs up" reaction. If you don't see your particular problem, we'd love to hear from you. Include any **Output** window log entries from Visual Studio IntelliCode, Python, Java, JavaScript, or TypeScript with the bug.

## See also

- [IntelliCode for Visual Studio](intellicode-visual-studio.md)
- [IntelliCode general FAQ](faq.yml)



