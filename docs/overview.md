---
title: Visual Studio IntelliCode
titleSuffix: ""
ms.date: 04/24/2019
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
---
# Overview of IntelliCode

Visual Studio IntelliCode enhances software development using artificial intelligence. IntelliCode delivers [context-aware code completions](#context-aware-code-completions) and guides developers to adhere to the [patterns and styles of their team](code-style-inference.md). IntelliCode extensions are available for [Visual Studio](intellicode-visual-studio.md) and [Visual Studio Code](intellicode-visual-studio-code.md).

For more information and to sign up for news and updates, see [Visual Studio IntelliCode](https://visualstudio.microsoft.com/services/intellicode/).

## Context-aware code completions

IntelliCode provides AI-assisted IntelliSense in the extensions for both Visual Studio and Visual Studio Code. IntelliCode suggestions appear at the top of the completion list with a star icon next to them:

![Starred IntelliSense suggestions using IntelliCode in Visual Studio](media/starred-intellisense-suggestions.png)

The completion list suggests the most likely correct API for a developer to use rather than presenting a simple alphabetical list of members. To provide this dynamic list, IntelliCode uses the developer's current code context as well as patterns based on thousands of highly rated, open-source projects on GitHub. The results form a model that predicts the most likely and most relevant API calls.

### Supported languages

The supported languages for AI-assisted IntelliSense completions are:

- C#, C++, XAML, JavaScript, and TypeScript for Visual Studio.

- Java, JavaScript, TypeScript, and Python for Visual Studio Code.

## Telemetry

We capture some anonymized usage and error-reporting data from the extension to help improve the product. No user-defined code is sent to Microsoft, but we collect information about your use of the IntelliCode results.

For base model suggestions, which are open source or .NET types and members, we capture whether you selected an IntelliCode suggestion and log the name of the suggestion. Microsoft uses the data to monitor the quality of the base model. For custom models, we capture whether you selected an IntelliCode suggestion but *do not* log the names of your user-defined types or methods.

In Visual Studio, you can opt out of the [Visual Studio Experience Improvement Program](/visualstudio/ide/visual-studio-experience-improvement-program), which turns off data collection for the IntelliCode extension too. From the menu bar, select **Help** > **Send Feedback** > **Settings**. In the **Visual Studio Experience Improvement Program** dialog, select **No, I would not like to participate** and then select **OK**.

In Visual Studio Code, you can disable telemetry reporting by following [these instructions](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting).

The IntelliCode extension may periodically ask you to complete an anonymous survey. You can also sign up for news and updates but are not required to do so.

## See also

- [Visual Studio IntelliCode FAQ](faq.md)