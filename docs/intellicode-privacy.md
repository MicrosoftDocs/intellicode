---
title: IntelliCode privacy
ms.date: 08/24/2021
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
description: IntelliCode privacy
author: markw-t
ms.author: mwthomas
manager: jmartens
---
# IntelliCode privacy

This article describes privacy information and settings for IntelliCode for Visual Studio and Visual Studio Code.

## IntelliCode Whole Line Completions

IntelliCode whole line completions runs entirely on the local machine and does not send any code to Microsoft in order to make its predictions.

## Firewall and proxy settings

For IntelliCode to gain access to web services, network managers will need to add `*.intellicode.vsengsaas.visualstudio.com` on https/443 to an allowlist. Conversely, adding it to a blocklist will prevent IntelliCode from working in your network.

Additional information can be found at [Install and use Visual Studio and Azure Services behind a firewall or proxy server](/visualstudio/install/install-and-use-visual-studio-behind-a-firewall-or-proxy-server).

## IntelliCode API Usage Examples

IntelliCode API Usage Examples uses a web service to return real-world usage examples of functions which it has found on public GitHub repos. The feature maintains a local list of function names for which it has examples, based solely on scanning public GitHub repositories. It maintains that list on your local machine by downloading it from a web service.  When you interact use API usage examples to look up a given function name, that name is checked against that local list. A query to retrieve examples from the web service is issued only if the function is found there. In this way the feature will never send any information (even the function name) about your own code's custom functions over the internet. 

## IntelliCode Team completion models
Certain IntelliCode features require access to web services to obtain model files, or to submit code metadata to train new custom models for your own code. The IntelliCode web services don't keep a copy of your custom model once it has been delivered to your instance of Visual Studio. If your instance of Visual Studio never collects a custom model that it sent up for training, we automatically delete it from our services 29 days after the model is produced.

Additional information can be seen in the [Custom Models Data and Privacy](custom-models.md#data-and-privacy) section.

### Data residency
Note that when you submit code metadata to train team completion models for your code, the data may leave your geography to be processed by IntelliCode services located in the United States of America.

### Corporate controls over Team completion model training
Team completion model training and acquisition can be disabled by corporate policy across all the machines that run Visual Studio in your organization, via registry keys.

Global policy:
  - Path: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\IntelliCode`
  - Key: DisableRemoteAnalysis
  - Key type:  DWORD (32-bit)
  - A value of 1 indicates opt-out

Local policy:
  - Path: `HKEY_CURRENT_USER\SOFTWARE\Microsoft\VSCommon\16.0\IntelliCode` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\VSCommon\17.0\IntelliCode`
  - Key: DisableRemoteAnalysis
  - Key type:  DWORD (32-bit)
  - A value of 1 indicates opt-out

