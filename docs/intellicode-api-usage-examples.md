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

# IntelliCode API Usage Examples

IntelliCode API Usage Examples allows developers to look up real-world example usages of a given function from public open source repositories on GitHub, without leaving their editor.

This preview feature is currently available as a [Visual Studio Code extension](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.intellicode-api-usage-examples), and currently supports Python, JavaScript and Typescript (including JSX and TSX files). 

![Screenshot of IntelliCode API Usage Examples in Visual Studio Code.](media/IntelliCodeUsageExamplesV2.gif)

## How to use API Usage Examples

1. Install the [Visual Studio Code extension](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.intellicode-api-usage-examples)
1. Open any supported file (.py, .js, .jsx, .tsx), and hover your mouse over any existing or new call (must have open and close parentheses).
1. If that function is a found in IntelliCode API Usage Examples' list, you will see a window appear below where you are hovering.
1. Scroll inside the appearing window until you see ★ Top API Usages for and click the See Real World Examples From GitHub link.
1. A results view will appear displaying code examples grouped by how common the API usage is. The API usage will be highlighted in blue.

## How does it work ?
IntelliCode API Usage examples uses a web service to look up real-world examples of functions from public GitHub repositories. You can read more about the privacy characteristics of the feature [here](intellicode-privacy)
