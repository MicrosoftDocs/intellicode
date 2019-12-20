---
title: Quickstart - IntelliCode Team completions
titleSuffix: ""
ms.date: 12/19/2019
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
author: catycaldwell
ms.author: ccaldwel
manager: jillfra
---
# Quickstart: IntelliCode team completion - AI-assisted IntelliSense based on your code

## Why do I want team completions? 

Visual Studio IntelliCode uses machine learning to offer useful, contextually-rich code completion suggestion, in-line as you code.

If you use a lot of types that are not common in the open source codebases we train our base models on, you can get IntelliCode's contextual completion suggestions (the items in the IntelliSense list with the stars) using team completions. Team completions trains a model just for your codebase, and lets you share it just with those who have access to your code. You can also keep it up to date automatically by including a task in your CI build pipeline.

To train your own model for team completions, we extract a summary file with metadata on your types and their usages and securely upload it to our service.

   > [!NOTE]
   > IntelliCode team completions is a preview feature in [Visual Studio version 16.4](https://docs.microsoft.com/visualstudio/releases/2019/release-notes) and above and are disabled by default. It can be enabled through **Tools** > **Options** > **IntelliCode**. They are currently available only for C# and C++ code.
   
## How to obtain team completions

You can train models for team completions to a repository and all users who can clone and edit the repository are granted automatic access to your completions. See [automatic acquisition of team models for more information](share-models.md).
    - Your codebase must be under Git source control and pushed to a remote to create a repository-associated model.

## 2 steps to team completions

Getting team completions on your codebase is very quick and easy, with just 2 steps:

Step 1: Train your repo manually and try out the completions on your code
Step 2: Automate the training as part of your CI build

### Train models for team completions

To train team completions on your repo, follow these steps:

1.  Clone the repository with the solution you’d like to train on.
1.  Open the solution or repository folder in Visual Studio.
1.	Create a model by going to **View** > **Other Windows** > **Train IntelliCode model on this repository** or by searching for **"Train"** in Visual Studio Search (**Ctrl + Q**).
1.	You’ll be prompted to sign-in with the account you’d like to use. This should be the account you normally log in to Visual Studio with.
1.	Upon successful creation of the model, it will be automatically downloaded to Visual Studio. You can track the model’s progress by opening the Output Window and switching to IntelliCode in the dropdown. 

Requirements:

- The repository must not already have a repository-associated model already trained on it.
- The repository must be under Git source control.
- You must enable the following settings in **Tools** > **Option** > **IntelliCode**.
   - C# or C++ team models for completions
   - Acquire team models for completions

   > [!NOTE]
   > If you don't see the above settings in Visual Studio, be sure that you have installed at least [Visual Studio version 16.4](https://docs.microsoft.com/visualstudio/releases/2019/release-notes) or above. Once the preview has been installed, you can enable acquiring team models for completions through **Tools** > **Options** > **IntelliCode**.

Once the training is complete, try writing some code using the classes/types that are particular to your repo - you should see starred recommendations for the most common cases.

Once you are happy with the team completions on your repo, you can set up to automatically create and retrain team completions as part of your continuous integration pipeline in [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) with the IntelliCode build task.

## Automate model retraining
To keep your completions up-to-date as your code changes, you can automate training your model in Azure Dev Ops with the IntelliCode CI build task.

Before you start, make sure that: 
1. You have permission to create and edit pipelines for the project. Or, ask your CI Admin.
1. The build agent has the minimum required version of Visual Studio installed:
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

## Troubleshooting FAQ


## See also
- [Comprehensive documentation on Team Completions](custom-models.md)
- [Setting up a build task](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.VSIntelliCodeTeamModelTraining)
- [Share models](share-models.md)
- [Overview of IntelliCode](overview.md)
- [General IntelliCode FAQ](faq.md)
- [IntelliCode for Visual Studio](intellicode-visual-studio.md)
