---
title: How to opt-out of sending personal data to IntelliCode services from Visual Studio
description: Learn how to opt-out of sending personal data to IntelliCode services in Visual Studio.
ms.date: 09/18/2020
ms.topic: how-to
author: markw-t
ms.author: mwthomas
ms.workload: intellicode
---
# What personal data is sent to IntelliCode services from Visual Studio

> Applies to Visual Studio 2019 16.8 and newer

Learn how to use group policy to manage your organization's sending personal data to IntelliCode services from Visual Studio. First,
we'll describe what IntelliCode collects and sends to the service. Then we'll walk
through how to opt-out your organization.

## Prerequisites

The following items are required for applying group policy for IntelliCode capabilities:

- A Visual Studio 2019 Admin Role, see [Visual Studio Subscriptions Admin Responsibilites](https://docs.microsoft.com/visualstudio/subscriptions/admin-responsibilities?view=vs-2019&preserve-view=true) for more information about the Admin role.
- Visual Studio 2019 version 16.8 or newer

Some [Visual Studio IntelliCode](https://aka.ms/intellicode) capabilities require sending personal data from Visual Studio to the IntelliCode service, such as [Team Completions](https://aka.ms/vsic-teamcompletions). When using these capabilities, IntelliCode may collect: 

- [information about your types and type usage](https://aka.ms/vsic/data-and-privacy), collected when you train personalized models
- metadata about the Git repository you are working in, used to locate any models for Team Completions that you can benefit from

This information is sent to the IntelliCode service over an HTTPS connection, The information that's collected allows IntelliCode to securely train and distribute personalized models. This document covers how to opt in or out of using IntelliCode capabilities that send data to IntelliCode services.
## User-level Opt in or out in Visual Studio
All released IntelliCode capabilities are turned **on** by default, and all Preview IntelliCode capabilities are turned **off** by default. Users can turn capabilities off, or back on again, by following these instructions:

1. In Visual Studio, go to **Tools** > **Options** > **IntelliCode**.
1. To explicitly opt out, select **Disabled** for the respective capability. To opt in, select **Enabled** for the respective capability.


## Registry settings for Global Policy opt-out

Enterprise customers can construct a group policy to opt in or out of IntelliCode capabilities that send personal data to IntelliCode services {i.e. Team Completions} by setting a registry-based policy.

The relevant registry key and settings are as follows:

- On a 64-bit OS, Key = **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\VSCommon\16.0\IntelliCode**
- On a 32-bit OS, Key = **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VSCommon\16.0\IntelliCode**
- When Group Policy is enabled, Key = **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\VisualStudio\IntelliCode**


Entry = **DisableRemoteAnalysis**

Value = (DWORD)

- **0** is opted in (turn on machine-wide access to IntelliCode services)
- **1** is opted out (turn off machine-wide access to IntelliCode services)

> [!CAUTION]
> Incorrectly editing the registry may severely damage your system. Before making changes to the registry, you should back up any valued data on the computer. You can also use the **Last Known Good Configuration** startup option if you encounter problems after manual changes have been applied.

For more information about the information collected, processed, or transmitted by IntelliCode, see [IntelliCode Data & Privacy](https://docs.microsoft.com/visualstudio/intellicode/custom-models#data-and-privacy).

## See also
* [IntelliCode Overview](https://aka.ms/intellicode)
* [IntelliCode Data & Privacy](https://aka.ms/vsic/data-and-privacy)
* [IntelliCode Team Completions](https://aka.ms/vsic-teamcompletions)
* [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement)
