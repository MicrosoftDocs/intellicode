---
title: IntelliCode completions for Python: Deep Learning (beta) extension in Visual Studio Code 
ms.date: 11/25/2019
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: error
description: Turning off IntelliCode deep learning beta features - note this doc is for turning off the beta extension and is not in TOC
author: catycaldwell
ms.author: catycaldwell
manager: mwthomas
---
# Install IntelliCode beta extension to get completions for Python: Deep Learning
IntelliCode improves your authoring experience when you're writing python code.
Download this [internal Microsoft dogfood feature](https://devdiv.visualstudio.com/_apis/resources/Containers/4851656?itemPath=vsix-merge%2Fvscodeintellicode-1.2.1.vsix) for VS Code powered by Deep LSTM model, you should expect significant recommendation precision improvement over our IntelliCode preview version.

After downloading the above .vsix, you can install by: 
  *_Manually from VS Code_: Via the extensions tab, right-click the ... and select "Install from VSIX..." as shown in screenshot below
  *_Via Command Prompt_: type code --install-extension<path_to_vsix>\vscodeintellicode-1.2.1.vsix

![Illustration of Manual VSIX Visual Studio Code extension install](docs/media/visual-studio-code-extension-install-from-vsix.png)

> [!NOTE] 
> To try out completions for Python based on a Deep Learning model, you can use any Visual Studio Code version, however, you will need to
> have at minimum the [Visual Studio Code Python extension version 2019.8.29288](https://marketplace.visualstudio.com/items?itemName=ms-python.python) (an August 2019 release). 

## How to enable completions for Python: Deep Learning beta
completions for Python: deep learning is a beta feature, so it is turned on by default.
![Illustration of enabling completions for python:deep learning](docs/media/deep-learning-extension-vscode-setting.png)

If you would like to enable completions for Python: deep learning feature, select the **enabled** option in _File_ > _Preferences_ > _Settings_ > _Extensions_ > _Visual Studio IntelliCode_ 

## How to disable completions for Python: Deep Learning beta 
To turn it off, choose **File** > **Preferences** > **Settings** > **Extensions** > **Visual Studio IntelliCode**, and then switch **Python:Deep Learning** to **disabled**.

After you change this setting, close any open files, and then restart Visual Studio Code.

Please report any issues [aka.ms/vsicissues](https://aka.ms/vsicissues). 

