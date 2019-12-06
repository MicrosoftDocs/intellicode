---
title: Quickstart: IntelliCode Team completions
ms.date: 04/24/2019
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
author: catycaldwell
ms.author: catycaldwell
manager: jillfra
---
# Quickstart: IntelliCode team completion - AI-assisted IntelliSense based on your code

## A-B-Cs on IntelliCode team completions

Visual Studio IntelliCode uses machine learning to offer useful, contextually-rich code completion suggestions as you type. Although IntelliCode's base model was trained on over 3000 top open source C# GitHub repositories, it does not include all the custom types in your team's codebase. 
You can now acquire IntelliCode team completions for better AI-assisted IntelliSense recommendations tailored to your codebase. Team completions are useful when working with your own types or domain-specific libraries that aren’t commonly used in open source code. This is because IntelliCode’s base model recommendations are based solely on patterns learned from open-source GitHub repos. When working with code that isn’t in that set of repos, those recommendations aren't as useful to you. C# and C++ users in Visual Studio can now use IntelliCode to learn patterns from their code to make recommendations tailored to _your_ code.

To build your team model, we extract a summary file with metadata on your types and their usages and securely upload it to our service.

   > [!NOTE]
   > Team completions are a preview feature in [Visual Studio version 16.4](https://docs.microsoft.com/visualstudio/releases/2019/release-notes) and above and are disabled by default. It can be enabled through **Tools** > **Options** > **IntelliCode**. They are currently available only for C# and C++ code.
   
## How to obtain team completions

You can train models for team completions to a repository and all users who can clone and edit the repository are granted automatic access to your completions. See [automatic acquisition of team models for more information](#sharing-your-repository-associated-models).
    - Your codebase must be under Git source control and pushed to a remote to create a repository-associated model.

## 2 steps to team completions

### Train models for team completions

Requirements:

- The repository must not already have a repository-associated model already trained on it.
- The repository must be under Git source control.
- You must enable the following settings in **Tools** > **Option** > **IntelliCode**.
   - C# or C++ team models for completions
   - Acquire team models for completions
   
   > [!NOTE]
   > If you don't see the above settings in Visual Studio, be sure that you have installed at least [Visual Studio version 16.4](https://docs.microsoft.com/visualstudio/releases/2019/release-notes) or above. Once the preview has been installed, you can enable acquiring team models for completions through **Tools** > **Options** > **IntelliCode**.

To train team completions on your repo, follow these steps:

1.  Clone the repository with the solution you’d like to train on.
1.  Open the solution or repository folder in Visual Studio.
1.	Create a model by going to **View** > **Other Windows** > **Train IntelliCode model on this repository** or by searching for the command in Visual Studio Search (**Ctrl + Q**).
1.	You’ll be prompted to sign-in with the account you’d like to use.
1.	Upon successful creation of the model, it will be automatically downloaded to Visual Studio. You can track the model’s progress by opening the Output Window and switching to IntelliCode in the dropdown. 

Once you are happy with the team completions on your repo, you can set up to automatically create and retrain team completions as part of your continuous integration pipeline in [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) with the IntelliCode build task.

## Automate model retraining

Before you start, make sure that: 
1. You have permission to create and edit pipelines for the project.
1. The build agent has the minimum required version of Visual Studio installed. 
1. For C# repositories: Visual Studio 2017 or higher
1. For C++ repositories: Visual Studio 2019 Update 4 or higher

### Setup
1. [Install](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.VSIntelliCodeTeamModelTraining) the Visual Studio IntelliCode team model training task from Visual Studio Marketplace to your Azure DevOps organization or Azure DevOps Server to automatically retrain your team completions whenever your code changes.
1. Set up a service connection for IntelliCode. This connection is used to upload the training data to create the model.
1. In the task configuration pane, type the branch that you want to train the model on. 
1. Select the IntelliCode service connection you'd like to use for this tak form the downdown.
1. Ensure that the IntelliCode Model Training task occurs after your build step.
1. Save and run your pipeline to create your model.
1. Open the corresponding repository from your pipeline in Visual Studio to download the newly created model. 
1. Your model will be automatically updated and shared with each CI build.

## See also
- [Comprehensive documentation on Team Completions](custom-models.md)
- [Setting up a build task](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.VSIntelliCodeTeamModelTraining)
- [Share models](share-models.md)
- [Overview of IntelliCode](overview.md)
- [General IntelliCode FAQ](faq.md)
- [IntelliCode for Visual Studio](intellicode-visual-studio.md)
