---
title: Visual Studio extension
ms.date: 04/22/2019
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
manager: jillfra
author: markw-t
ms.author: mwthomas
---
# IntelliCode for Visual Studio overview

The [IntelliCode extension for Visual Studio](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.VSIntelliCode) provides the following functionality:

- **AI-assisted IntelliSense** for C#, C++, and XAML that predicts the most likely correct API for the developer to use instead of just an alphabetical list of members. It uses the developer's current code context and patterns to provide this dynamic list.

- AI-assisted [IntelliSense recommendations based on your own code](custom-models.md) (C# only).

- [Inference of code style and formatting conventions](code-style-inference.md) to dynamically create an [.editorconfig file](/visualstudio/ide/create-portable-custom-editor-options) from your codebase (C# only).

## Prerequisites

The [IntelliCode extension for Visual Studio](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.VSIntelliCode) is supported on:

- Visual Studio 2019, or,
- Visual Studio 2017 version 15.8 and later (all SKUs)

To see AI-assisted IntelliSense for certain languages, you may need a more recent version than that required just to install the extension:

- C++ requires Visual Studio 2019 or later
- XAML requires Visual Studio 2017 version 15.9 or later

## Troubleshoot

If you don't see any IntelliCode suggestions, you may have extensions installed that are overriding the IntelliSense UI. This can prevent the IntelliCode "starred" suggestions from appearing at the top of the list. You can verify if extensions are causing this behavior by turning them off and then trying IntelliSense again, or, if the extension supports it, by turning off its auto-completion features.

If this doesn't solve the problem for you, please report your issue by using the Visual Studio [Report a Problem](/visualstudio/ide/how-to-report-a-problem-with-visual-studio) feature and mention IntelliCode in your report.

## See also

- [IntelliCode models based on your code](custom-models.md)
- [IntelliCode FAQ](faq.md)
- [IntelliCode extension for Visual Studio Code](intellicode-visual-studio-code.md)
