---
title: Share user-associated models
description: Share team completions in IntelliCode so that you can share any model you've created. Automatically update users that have access when you retrain the model.
ms.custom: SEO-VS-2020
ms.date: 05/21/2019
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
author: markw-t
ms.author: mwthomas
manager: jmartens
---
# How to: Share team completions in Visual Studio IntelliCode

IntelliCode lets you share repository-associated team models you've created and automatically update users that have access when you retrain the model.

By creating a team completions model, you get IntelliCode completion recommendations for code that's not in the base model. Sharing a team completions model with collaborators extends the enhanced IntelliSense recommendations to everyone; they don't have to create or retrain a team completions model themselves.

## Share a repository-associated team completions model

Repository-associated models are **automatically shared** with others working in the same codebase.  Automatic model acquisition is enabled by default in Visual Studio. 

If you wish to opt out, go to **Tools** > **Options** > **IntelliCode** > **Acquire team models for completion**  and set to disabled.

When anyone clones and opens the codebase the model was trained on, any completions models associated with the configured Git remote repositories will be downloaded and activated. If you are working on a fork of the codebase, simply add the upstream codebase as a remote repository to get the completions model.

Access to the repository is access to the model. When training, we collect some information about the checked-out commit. Anyone who requests that model must have the same commit in their repository and be able to produce the same information that was collected during training in order to receive the team model.

>[!NOTE] 
>The ability to share your user-associated team completions models via a sharing link, available in some preview releases of Team completions, is now deprecated

## Common sharing scenarios

This section describes how to set up model sharing for some common cases.

### Open Source project (git-based)

Suppose you have an existing codebase that contains good patterns for using types contained in a shared library. You'd like IntelliCode to learn from usage in that codebase to kickstart you and your collaborators when you start work on your next project that uses the same library. The new project, being new, has no usage to learn from. So what do you do?

The best approach here is:

1. [Train a repo-associated model for team completions](custom-models.md#repository-associated-team-models) on the existing codebase.

2. When anyone clones and opens the codebase the model was trained on, any completions models associated with the configured Git remote repositories will be downloaded and activated. If you are working on a fork of the codebase, simply add the upstream codebase as a remote repository to get the completions model. Access to the repository is access to the model. When training, we collect some information about the checked-out commit. Anyone who requests that model must have the same commit in their repository and be able to produce the same information that was collected during training in order to receive the team model.

3. Automate retraining your model with [the Azure Pipelines IntelliCode task](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.VSIntelliCodeTeamModelTraining) or [GitHub Action](https://aka.ms/vsic/xtn/github) to keep completions up-to-date with code changes. Your team automatically gets updates whenever the repo is trained. 

## See also

- [IntelliCode models based on your code](custom-models.md)
