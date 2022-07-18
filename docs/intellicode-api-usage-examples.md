---
title: IntelliCode API Usage Examples (preview)
ms.date: 15/07/2022
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
description: IntelliCode API Usage Examples
author: markw-t
ms.author: mwthomas
manager: jmartens
---

# IntelliCode API Usage Examples (Preview)

IntelliCode API Usage Examples is a preview feature which lets you look up real-world example usages of a given function from public open source repositories on GitHub, without leaving your code editor.

This preview feature is currently available as a [Visual Studio Code extension](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.intellicode-api-usage-examples), and currently supports Python, JavaScript and Typescript (including JSX and TSX files). 

![Screenshot of IntelliCode API Usage Examples in Visual Studio Code.](media/IntelliCodeUsageExamplesV2.gif)

## How to use API Usage Examples

1. Install the [Visual Studio Code extension](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.intellicode-api-usage-examples)
1. Open any supported file (.py, .js, .jsx, .tsx), and hover your mouse over any function call (the call must have open and close parentheses).
1. You will see an info window appear below where you are hovering. If the function you hovered is found in IntelliCode API Usage Examples' list, a list of top API usages for that function, and a link to "See Real World Examples From GitHub", will appear in that window. Note: you may need to scroll the informational window to see this.
1. Click on the "See Real World Examples From GitHub" link - a results view will appear displaying code examples grouped by how common the API usage is. The API usage will be highlighted in blue.
1. You can optionally click on the GitHub-labelled hyperlink within the results view to see the code in the context of the originating GitHub repository.

## How does it work ?
IntelliCode API Usage examples uses a web service to look up real-world examples of functions from public GitHub repositories. You can read more about the privacy characteristics of the feature [here](intellicode-privacy#intellicode-api-usage-examples)
