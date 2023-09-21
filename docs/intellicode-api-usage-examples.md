---
title: IntelliCode API Usage Examples
ms.date: 07/15/2022
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
description: IntelliCode API Usage Examples
author: markw-t
ms.author: mwthomas
manager: jmartens
---

# IntelliCode API Usage Examples

IntelliCode API Usage Examples is a preview feature that lets you see real-world examples of how other developers have used a given function. Examples shown are from public open source repositories on GitHub.

This preview feature is currently available as a [Visual Studio Code extension](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.intellicode-api-usage-examples), and currently supports Python, JavaScript and TypeScript (including JSX and TSX files). 

![Screenshot of IntelliCode API Usage Examples in Visual Studio Code.](https://aka.ms/IntelliCodeUsageExamplesv2)

## How to use API Usage Examples

1. Install the [Visual Studio Code extension](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.intellicode-api-usage-examples)
1. Open any supported file (PY,JS,JSX and TSX), and hover your mouse over any function call (the call must have open and close parentheses). 
1. An info window will appear, below where you're hovering. If the function you hovered is supported by the feature, a link to "See Real World Examples From GitHub" will appear in that window. Note: you may need to scroll the informational window to see the link.
1. Click on the "See Real World Examples From GitHub" link - a results view will appear displaying code examples grouped by how common the API usage is. The API usage will be highlighted in blue.
1. Alternatively, you can go directly to the results view using the keyboard. Move your editing caret onto the function and press Ctrl+. , then hit enter to select "See real world examples from GitHub". 
1. You can optionally click on the GitHub-labelled hyperlink within the results view to see the example in the context of the originating GitHub repository.

## How does it work?
It uses a scan of public GitHub repositories, which creates a mapping from function names to code snippets. These code snippets represent real world usages of those functions. The mapping is used to provide the examples you see when using the feature, via a web service. When you hover a function, the feature only ever sends the names of functions found in public open source repos to the service. It will never send your own custom function names. You can read more about the privacy characteristics of the feature [here](/docs/intellicode-privacy.md#intellicode-api-usage-examples)
