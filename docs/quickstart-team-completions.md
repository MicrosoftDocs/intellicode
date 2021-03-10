---
title: Visual Studio IntelliCode team completions - Quickstart
titleSuffix: Visual Studio IntelliCode
description: Use IntelliCode team completions to get starred contextual completion suggestions for your own types, or for other types not commonly found in open source.
ms.custom: SEO-VS-2020
ms.date: 12/19/2019
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
author: markw-t
ms.author: mwthomas
manager: jmartens
---
# Quickstart - IntelliCode team completions - AI-assisted IntelliSense suggestions based on your code

Visual Studio IntelliCode uses machine learning to offer useful, contextually rich code completion suggestion, in-line as you code.

To get IntelliCode's starred contextual completion suggestions for your own types, or other types not commonly found in open source, use team completions. Team completions [trains a model](quickstart-team-completions.md#what-happens-when-you-train-your-model) just for your codebase. You can also share it just with anyone with access to your code and keep it up to date automatically, by including a task in your CI build pipeline.

## How to obtain team completions

Getting team completions on your codebase is quick and easy. 

For a local model, simply agree to train a machine-associated model by accepting the prompt or checking the "I accept these terms" checkbox - we'll take care of the rest
If you want to share models with other users of your repo, you should automate the training as part of your CI build

### Train models for team completions

To train team completions on your repo, follow these steps:

1.  Open the repository with the solution you’d like to train on.
1.  Visual Studio will prompt you via a "gold bar" to train a model for that repository. You can choose to do so right from the gold bar
1.	 If you declined the gold bar you can stil create a model by going to **View** > **Other Windows** > **IntelliCode** or by searching for **"IntelliCode"** in Visual Studio Search (**Ctrl + Q**) and selecting "IntelliCode". Once that window is open, check the "I accept these terms and would like to train IntelliCode models on my currently open codebase: <name of your solution>" checkbox.

1.	Upon successful creation of the model, the model will be automatically downloaded to Visual Studio. You can track the model’s progress by opening the Output Window and switching to IntelliCode in the dropdown. 

Requirements:
- Ensure these options are enabled the following settings in **Tools** > **Option** > **IntelliCode**. They are enabled by default in Visual Studio 2019 16.8 and higher.
   - Team models for completions
   - Acquire team models for completions
 
   > [!NOTE]
   > If you don't see the above settings in Visual Studio, be sure that you have installed at least [Visual Studio version 16.8](https://docs.microsoft.com/visualstudio/releases/2019/release-notes) or above.

Once the training is complete, try writing some code using the classes/types that are particular to your repo - you should see starred suggestions for the most common cases.

Once you are happy with the team completions on your repo, you can set up to automatically create and retrain team completions as part of your continuous integration pipeline in [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) with the IntelliCode build task.

## What happens when you train your model?

When you kickoff training your model for team completions:
* We analyze your code locally.
* We extract a summary file with metadata on your types and their usages.
* We securely upload it to the IntelliCode service and train a completions model tailored to your code.
* Your completions model is automatically shared with those who have access to your repo. 

You will see the training progress in your Visual Studio output window's IntelliCode section. Once the training is complete, you will be able to see your summary and the new model tailored to your code. You can then try writing some code using the classes/types that are particular to your repo - you should see starred suggestions for the most common cases.  

If you want more information about what data is used and transferred in this process see [IntelliCode data and  privacy](https://docs.microsoft.com/visualstudio/intellicode/custom-models#data-and-privacy).

## Automate model retraining
To keep your completions up-to-date as your code changes, and share the model with others who have access to your repo, you can automate training your model in Azure DevOps with the IntelliCode CI build task.

Before you start, make sure that: 
* You have permission to create and edit pipelines for the project. Or, ask your CI Admin.
* The build agent has the minimum required version of Visual Studio installed:
  *  For C# repositories: Visual Studio 2017 or higher
  * For C++ repositories: Visual Studio 2019 Update 4 or higher

### Setup
1. [Install](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.VSIntelliCodeTeamModelTraining) the Visual Studio IntelliCode team model training task from Visual Studio Marketplace to your Azure DevOps organization or Azure DevOps Server to automatically retrain your team completions whenever your code changes.
1. Set up a service connection for IntelliCode. This connection is used to upload the training data to create the model.
1. In the task configuration pane, type the branch that you want to train the model on. 
1. Select the IntelliCode service connection you'd like to use for this task from the drop down.
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
