---
title: VS Code extension
description: Read an overview of IntelliCode for Visual Studio Code. The IntelliCode extension provides AI-assisted IntelliSense for Python, Java, TypeScript, and JavaScript.
ms.custom: SEO-VS-2020
ms.date: 04/24/2019
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
author: markw-t
ms.author: mwthomas
manager: jmartens
---
# IntelliCode for Visual Studio Code overview

The [IntelliCode extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.vscodeintellicode) provides artificial intelligence-assisted IntelliSense for Python, Java, TypeScript, and JavaScript. AI-assisted IntelliSense predicts the most likely correct API for the developer to use rather than just presenting an alphabetical list of members. It uses the developer's current code context and patterns to provide this dynamic list.

![IntelliCode for Python in Visual Studio Code](media/python-intellicode.gif)

IntelliCode provides AI-assisted IntelliSense completions for the following languages:

- Java
- JavaScript and TypeScript
- Python
- SQL


### Prerequisites

The extension is supported by Visual Studio Code June 2021 Release 1.58 or later.

AI-assisted IntelliSense for Java requires Java 8 Update 151 or higher. 


## Troubleshoot

This section provides some troubleshooting tips for common problems with IntelliCode.

### No completion lists

If you don't see any IntelliSense completion lists, try these steps:

- Look at the output window for the language you're trying to use and see if there's an actionable error message.

- Try disabling the IntelliCode extension and see if you get any IntelliSense completions. If you do see IntelliSense completions with IntelliCode disabled, look through the [existing issues](https://github.com/MicrosoftDocs/intellicode/issues) or open a new one.

You can also try the following troubleshooting steps for your language:

- JavaScript / TypeScript: [VS Code IntelliSense troubleshooting](https://code.visualstudio.com/docs/editor/intellisense#_troubleshooting) or [JavaScript IntelliSense in VS Code](https://code.visualstudio.com/docs/languages/javascript#_intellisense)

- Java: [How to troubleshoot and contribute to the Java language server](https://code.visualstudio.com/docs/java/java-faq#_how-to-troubleshoot-and-contribute-to-the-java-language-server)

- Python: [Meta issue for the Python language server](https://github.com/Microsoft/vscode-python/issues/2177)


### No starred suggestions

If you see IntelliSense completion lists, but none of the completion items are starred, look at the **VS IntelliCode** output window.

- Is there a network error?

  - Are you able to access the internet normally?

  - Are you behind a proxy or restrictive firewall?

   When using IntelliCode, you may see the error message "Couldn't download IntelliCode model. Please check your network connectivity or firewall settings.", or see similar messages in the IntelliCode output window pane in Visual Studio Code. You might also see no IntelliCode starred suggestions. If you connect to the internet through a proxy or restrictive firewall, that may cause these issues.

   As a first step, try updating to Visual Studio Code 1.30 or later, and [turning on network proxy support](https://code.visualstudio.com/updates/v1_30#_network-proxy-support-for-extensions) .

   If turning on network proxy support doesn't work for you, check the corresponding [github issue](https://github.com/MicrosoftDocs/intellicode/issues/4) and let us know more.
- If you're a Java user experiencing the  error message **java.security.InvalidKeyException: Illegal key size**, check to make sure you're using Java 8 Update 151 or later.
- Is there an actionable message that helps?

If you're still facing a problem, look through the [existing issues](https://github.com/MicrosoftDocs/intellicode/issues) or open a new one.

## Provide feedback

If you encounter a problem, you can browse [existing issues](https://github.com/MicrosoftDocs/intellicode/issues) and upvote them using a 👍 "thumbs up" reaction. If you don't see your particular problem, click the **Send feedback about** > **This product** button at the bottom of this page to create a new issue. Include any **Output** window log entries from Visual Studio IntelliCode, Python, Java, JavaScript, TypeScript, or SQL with the bug.
## See also

- [IntelliCode for Visual Studio](intellicode-visual-studio.md)
- [IntelliCode general FAQ](faq.yml)
