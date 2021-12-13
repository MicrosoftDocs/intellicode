---
title: IntelliSense based on your code
description: Use IntelliCode team models for completions to get AI-assisted IntelliSense recommendations based on your C# and C++ code bases.
ms.custom: SEO-VS-2020
ms.date: 04/24/2019
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
author: markw-t
ms.author: mwthomas
manager: jmartens
---
# IntelliCode team completions: AI-assisted IntelliSense based on your code

Use IntelliCode team models for completions to get AI-assisted IntelliSense recommendations based on your C# and C++ codebases. Team completions are useful when working with your own types or domain-specific libraries that aren’t commonly used in open source code. This is because IntelliCode’s base model recommendations are based solely on patterns learned from open-source GitHub repos. When working with code that isn’t in that set of repos, those recommendations aren't as useful to you. C# and C++ users in Visual Studio can now use IntelliCode to learn patterns from their code to make recommendations tailored to _your_ code.

An IntelliCode model is an encapsulation of a set of rules that allow prediction of some useful information (for example, recommendations in the IntelliSense list) based on an analysis of code. IntelliCode creates team models using the same learning process as for the IntelliCode base models, except they are trained on your own code. The more code you provide to illustrate your patterns of usage, the more capable your team model will be at offering useful recommendations.

To build your team model, we extract a summary file with metadata on your types and their usages and [securely upload](#data-and-privacy) it to our service.

## How models get applied

IntelliCode generates its recommendations from multiple models by merging together:

- The base model for the language you're using (which is trained on thousands of public GitHub repos)
- Any team models you've trained
- Any team models which are associated with the Git repository you’re working in

You don't need to manage which models apply to which solution or codebase because IntelliCode takes care of this for you.

## Types of team completions models

There are two ways you can obtain team completions models:

1. **Repository-associated**: 
Models are tied to the repository - all users who can clone and edit the repository are granted automatic access to the model. Your codebase must be under Git source control and pushed to a remote using our [Azure Pipelines Task](https://aka.ms/vsic/xtn/ado) or our [GitHub Action](https://aka.ms/vsic/xtn/github) from your CI build to create a repository-associated model.

2. **Machine-associated**: Models are available only on the machine they are trained upon. 
   
## Repository-associated team models

Repository-associated team models are available to users who train them using either Azure Pipelines or GitHub Actions.

- Learn how to configure and automate your CI workflow (i.e. .yml file) to train Team Completions using a GitHub Action [here](https://aka.ms/vsic/xtn/github).
- Learn how to configure your Azure DevOps pipeline to train Team Completions [here](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.VSIntelliCodeTeamModelTraining)

### Sharing your repository-associated models

Repository-associated models are automatically shared with others working in the same codebase as long as users have enabled automatic acquisition of team models in Visual Studio. 
Enable automatic acquisition by going to **Tools** > **Options** > **IntelliCode** > **Acquire team models for completion**.

When anyone clones and opens the codebase the model was trained on, any models associated with the configured Git remote repositories will be downloaded and activated. If you are working on a fork of the codebase, simply add the upstream codebase as a remote repository to get the model.

Access to the repository is access to the model. When training, we collect some information about the checked-out commit. Anyone who requests that model must have the same commit in their repository and be able to produce the same information that was collected during training in order to receive the team model.

>[!NOTE] 
>The ability to share your user-associated team completions models via a sharing link, available in some preview releases of Team completions, is now deprecated

### Delete your model

You can remove models from your account so they can no longer be used.

#### Delete a user-associated model created within Visual Studio

While your solution is open in Visual Studio, simply uncheck the checkbox accepting model training, on the View > Other Windows > IntelliCode page. The model will be deleted.

#### Delete a repository-attached model created using Azure DevOps or a GitHub CI workflow

Simply remove the training task from your pipeline - the associated model will be removed within 30 days if not trained.

## Machine-associated models

### Create and retrain your model

Train a machine-associated model:
1.	Open the project or solution in Visual Studio.
2.	Open the IntelliCode page by choosing **View** > **Other Windows** > **IntelliCode**
3.	Review and accept the license terms checkbox at the bottom of the page. A machine-associated model will be trained automatically. 
>[!NOTE] 
> You must repeat the above steps for each solution you want to train on.

Visual Studio will automatically retrain your machine-associated team completions models, periodically.

### Train on a public codebase

Before you train on your own code, you might want to create a completions model on a public codebase. You can see how the completions model affects IntelliSense, or if you're concerned about the kind of data that IntelliSense collects, you can inspect the extracted data. Some interesting samples to train on are:

- [Azure ConferenceBuddy](https://github.com/Azure/ConferenceBuddy)

   Fork the repo to your personal account, clone the repo, open the *ConferenceBuddy.sln* solution, build to check that it's working, and then train the model. You'll find some good completions on instances of the **AskWhoTask** class.

- [Windows RSS reader](https://github.com/Microsoft/Windows-appsample-rssreader)

   Fork the repo to your personal account, clone the repo, open the *RssReader.sln* solution, build to check that it's working, and then train the model. You'll find some good completions on instances of the **MainViewModel** class.

## Autotraining models for your codebase

After successfully building a solution, you may be prompted to enable IntelliCode to autotrain a model for IntelliCode completions for that solution.

By enabling autotraining models for IntelliCode completions, IntelliCode will train a machine-learning model for completions for the active solution and only the user who has access to the solution on the machine where the autotraining was enabled will have access to the respective model. If you'd like to share your custom code completions with anyone who can access your repository, you should [set up automatic training Team completions as part of your CI workflow](https://aka.ms/vsic-teamcompletions-quickstart).

> [!NOTE]
> For autotraining a model for IntelliCode custom code completions for your solution in Visual Studio, there are no source control requirements. However, if you'd like to share your custom completions with your team, your codebase must be under Git source control and pushed to a remote to create a repository-associated model.

### Enabling autotraining models for custom code completions in Visual Studio

To enable automatic model training for IntelliCode completions for your code in Visual Studio, follow these steps:

1. Open the solution or repository folder in Visual Studio.

1.	Enable autotraining a model for custom code Completions via the infobar prompt after a successful build, through the IntelliCode UI found at **View** > **Other windows** > **IntelliCode**, or through **Tools** > **Options** > **IntelliCode** setting "Autotraining team models for IntelliSense completions" or by searching for **"IntelliCode autotrain"** in Visual Studio Search (**Ctrl + Q**).

1.	Upon successful creation of the model, it will be automatically downloaded to Visual Studio. You can track the model’s progress by opening the Output Window and switching to IntelliCode in the dropdown OR in **View** > **Other windows** > **IntelliCode**. 

> [!NOTE]
> Be sure that you have installed at least [Visual Studio version 16.7 Preview 3](/visualstudio/releases/2019/release-notes-v16.0) or above. Once the preview has been installed, you can enable automatic models for custom code completions through the infobar after a successful solution build OR via **Tools** > **Options** > **IntelliCode**.

Once the training is complete, try writing some code using the classes/types that are particular to your repo - you should see starred suggestions for the most common cases.

Once you are happy with the custom code completions on your solution, you can set up to automatically create, retrain, and share IntelliCode custom code completions with your entire dev team as part of your continuous integration pipeline in [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) or [GitHub Action for Team Completions](https://aka.ms/vsic/github).

## Data and privacy

To build your team model, we extract a summary file with metadata on your types and their usages. For example, the summary file contains the names of classes and methods and how often they're called in different circumstances. IntelliCode doesn't track your keystrokes or extract whole expressions, statements, or literal values (such as strings) from your code.

When you enable IntelliCode to kickoff training and/or autotraining your model for custom code completions:

- We analyze your code locally.
- We extract a summary file with metadata on your types and their usages.
- We securely upload it to the IntelliCode service and train a completions model tailored to your code.
- Your completions model is never shared with those who have access to your repo (if a cloned git repository). 
- We allow you to delete your model at any time and/or cancel the model training directly in the IntelliCode UI found at **View** > **Other windows** > **IntelliCode**. Simply uncheck the box in the UI to delete the model for the custom code completions immediately.
- You can refresh your learned patterns directly in the IntelliCode UI found at **View** > **Other windows** > **IntelliCode**.

You will see the training progress in your Visual Studio output window's IntelliCode section or IntelliCode UI found at **View** > **Other windows** > **IntelliCode**. Once the training is complete, you will be able to see your summary and the new model tailored to your code. You can then try writing some code using the classes/types that are particular to your repo - you should see starred suggestions for the most common cases.  

### View extracted data

To inspect the contents of the extracted data:

1. Open the extracted data directory:
   - For repository-associated models: %temp%\Intellicode_Extraction_2019-10-23—234524
   - For machine-associated models: *%TEMP%\Visual Studio IntelliCode*

1. To find and open the training for your most recent training session, sort the folder view by date (descending). The folder for your most recent training session is now at the top.

   > [!TIP]
   > There's one folder per training session in the *%TEMP%\Visual Studio IntelliCode* directory, each with a randomized name.

The folder contains the entire set of files that are sent to Microsoft when extraction is complete. The *UsageOutput* subfolder contains a JSON file that has the information IntelliCode extracts from your code to train the model. The *UsageOutput_ErrorStats* file contains any errors found when trying to build the extracted file and can help if Microsoft needs to debug issues.

![IntelliCode model-training directory ](media/model-training-directory.png)

If you want to inspect the extracted data for a different codebase before trying it on your own code, train a model on a public codebase.

### How we secure your data

All data you send to and receive from the IntelliCode service is transmitted over HTTPS. You must [sign in to Visual Studio](/visualstudio/ide/signing-in-to-visual-studio) in order to communicate with the service. 

Models can only be retrieved:
- machine-associated models: by the machine which submitted the extracted data for training
- repo-associated models: by users who can prove they have access to the repository for [repository-associated models](#sharing-your-repository-associated-models). 

This means that your model and what is learned about your code stays private to you and your intended collaborators.

If Microsoft needs to troubleshoot, authorized Microsoft service personnel may be granted access to your models and extracted data for diagnostic purposes only.

## See also

- [Share models](share-models.md)
- [Overview of IntelliCode](overview.md)
- [General IntelliCode FAQ](faq.yml)
- [IntelliCode for Visual Studio](intellicode-visual-studio.md)
