---
title: IntelliCode extension for VSCode
ms.date: 12/04/2018
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
manager: douge
author: markw-t
ms.author: mwthomas
---
# IntelliCode for Visual Studio Code FAQ

You can [download an experimental extension](https://go.microsoft.com/fwlink/?linkid=2006060) for Visual Studio Code. This article has answers to some frequently asked questions about the extension.

## Q. What functionality does the extension provide?

The IntelliCode extension for Visual Studio Code provides artificial intelligence-enhanced IntelliSense for Python, Java, TypeScript, and JavaScript. AI-enhanced IntelliSense predicts the most likely correct API for the developer to use, rather than just presenting an alphabetical list of members. It uses the developer's current code context and patterns to provide this dynamic list.

![IntelliCode for Python in Visual Studio Code](media/python-intellicode.gif)

## Q. Will any other features be added to this extension?

We'll update the Visual Studio Code extension with more capabilities in the coming months.

## Q. I'm having problems with Python IntelliSense in Visual Studio Code. Can you help?

For more information and tips, see the [Python language server troubleshooting](https://github.com/Microsoft/vscode-python/issues/2177) page.

## Q. Which version of Visual Studio Code do I need to run the Visual Studio Code IntelliCode extension?

You’ll need Visual Studio Code October 2018 Release 1.29 or later to use this extension

## Q. Which version of Java do I need to get AI-assisted IntelliSense for Java?
You will need Java 8 Update 151 or higher.

If you try previous Java 8 versions you will see an error "java.security.InvalidKeyException: Illegal key size", and IntelliCode AI-assisted IntelliSense recommendations won't work.


## See also

- [IntelliCode extension for Visual Studio](intellicode-visual-studio.md)
- [IntelliCode general FAQ](faq.md)
