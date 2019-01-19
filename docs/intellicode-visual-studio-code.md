---
title: VSCode extension
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

## Q. I'm not seeing any IntelliSense completion lists

1. Take a look at the output window for the language you're trying to use, and see if there's an actionable error message
2. If not, try disabling the IntelliCode extension and see if you get any IntelliSense completions.
3. If you do see IntelliSense completions, re-enable the IntelliCode extension and see the next heading: "I see IntelliSense completion lists, but none of the completion items are starred"
4. If not, try the following for the language you're trying to use
    * JavaScript / TypeScript: [VS Code IntelliSense troubleshooting](https://code.visualstudio.com/docs/editor/intellisense#_troubleshooting) or [JavaScript IntelliSense in VS Code](https://code.visualstudio.com/docs/languages/javascript#_intellisense)
    * Java: [How to troubleshoot and contribute to the Java language server](https://code.visualstudio.com/docs/java/java-faq#_how-to-troubleshoot-and-contribute-to-the-java-language-server)
    * Python: [Meta issue for the Python language server](https://github.com/Microsoft/vscode-python/issues/2177)

## Q. I see IntelliSense completion lists, but none of the completion items are starred

Take a look at the `VS IntelliCode` output window.

* Is there a network error?
  * Are you able to access the internet normally?
  * Are you behind a proxy or restrictive firewall? Take a look at the heading "I'm having trouble getting IntelliCode to download models behind my firewall".
  * If not to both of these, please look at our [open issues](https://github.com/MicrosoftDocs/intellicode/issues) or open a new one.
* Is there an actionable message? If so, did it help?
* Please look at our [open issues](https://github.com/MicrosoftDocs/intellicode/issues) or open a new one.

## Q. What functionality does the extension provide?

The IntelliCode extension for Visual Studio Code provides artificial intelligence-assisted IntelliSense for Python, Java, TypeScript, and JavaScript. AI-assisted IntelliSense predicts the most likely correct API for the developer to use, rather than just presenting an alphabetical list of members. It uses the developer's current code context and patterns to provide this dynamic list.

![IntelliCode for Python in Visual Studio Code](media/python-intellicode.gif)

## Q. Will any other features be added to this extension?

We'll update the Visual Studio Code extension with more capabilities in the coming months.

## Q. Which version of Visual Studio Code do I need to run the Visual Studio Code IntelliCode extension?

You’ll need Visual Studio Code October 2018 Release 1.29 or later to use this extension.

## Q. Which version of Java do I need to get AI-assisted IntelliSense for Java?

You'll need Java 8 Update 151 or higher.

If you try previous Java 8 versions, you'll see the error "java.security.InvalidKeyException: Illegal key size", and IntelliCode AI-assisted IntelliSense recommendations won't work.

## Q: What about privacy? Are you sending my code to the cloud? What customer data is being sent to Microsoft?

Please see our [general FAQ on privacy](faq.md#-q-what-about-privacy-are-you-sending-my-code-to-the-cloud-what-customer-data-is-being-sent-to-microsoft).

## See also

- [IntelliCode extension for Visual Studio](intellicode-visual-studio.md)
- [IntelliCode general FAQ](faq.md)
