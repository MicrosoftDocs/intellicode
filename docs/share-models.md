---
title: Share user-associated models
ms.date: 05/21/2019
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
author: markw-t
ms.author: mwthomas
manager: jillfra
---
# How to: Share team completions in Visual Studio IntelliCode

IntelliCode has team completions sharing features that let you share any model you've created and automatically update users that have access when you retrain the model.

By creating a team completions model, you get IntelliCode completion recommendations for code that's not in the base model. Sharing a team completions model with collaborators extends the enhanced IntelliSense recommendations to everyone; they don't have to create or retrain a completions model themselves.

## Share a repository-associated team completions model

Repository-associated models are **automatically shared** with others working in the same codebase as long as users have enabled automatic acquisition of team models in Visual Studio. 

Enable automatic acquisition by going to **Tools** > **Options** > **IntelliCode** > **Acquire team models for completion**.

When anyone clones and opens the codebase the model was trained on, any completions models associated with the configured Git remote repositories will be downloaded and activated. If you are working on a fork of the codebase, simply add the upstream codebase as a remote repository to get the completions model.

Access to the repository is access to the model. When training, we collect some information about the checked-out commit. Anyone who requests that model must have the same commit in their repository and be able to produce the same information that was collected during training in order to receive the team model.

You can also share your model by going to **View** > **Other Windows** > **IntelliCode Model Management**, selecting your model from the left pane, and hitting the **Share** button. This generates a sharing link you can send to anyone you'd like to share the model with.

## Share a user-associated team model

After you've trained a model, the **Share model** button appears. Click the button to copy the sharing link. From there, you can share the link with your collaborators.

 > [!NOTE]
 > Anyone who has the sharing link can access the model and its suggestions, so make sure that everyone who receives the link is aware of this.

You can share your model with as many people as you like via the sharing feature. Team members can't retrain the model but they do see the same completion recommendations as you do.

## Add a user-associated team completions model

To use a model link that someone shared with you, follow these steps:

1. (Optional) If you're using a version of Visual Studio prior to Visual Studio 2019 version 16.1, first install the IntelliCode extension.

1. Open the IntelliCode page by choosing **View** > **Other Windows** > **IntelliCode Model Management**.

1. On the IntelliCode page, choose **Add model**. It's underneath **Shared With Me** in the left-hand navigation.

   ![Add model for IntelliCode in Visual Studio](media/add-model.png)

1. Paste the sharing link URL into the dialog box and choose **Add**.

   ![Add shared model in IntelliCode](media/add-shared-model.png)

   The shared model appears under **Shared With Me**. If you want to unlink the model, choose **Unlink**.

## Common sharing scenarios

This section describes how to set up model sharing for some common cases.

### Brand new project

Suppose you have an existing codebase that contains good patterns for using types contained in a shared library. You'd like IntelliCode to learn from usage in that codebase to kickstart you and your collaborators when you start work on your next project that uses the same library. The new project, being new, has no usage to learn from. So what do you do?

The best approach here is:

1. [Create a team model](custom-models.md#user-associated-team-models) on the existing codebase.

2. [Share the link](custom-models.md#user-associated-team-models) to the model with everyone who'll be using the new codebase.

   You can do this in various ways, for example, by checking it in to your codebase's *README* file, sending it in email, posting it on a project's wiki, or via a chat channel&mdash;whatever makes sense for your collaborators.

   > [!CAUTION]
   > Anyone who has the sharing link can access the model and its suggestions. Make sure that everyone who receives the link is aware of this.

3. Collaborators then [use the sharing link](#add-a-user-associated-team-completions-model) to add the model to their list of models, which tells IntelliCode to apply that model for completions in the new codebase too.

If you need to retrain the custom model, there's no need for collaborators to reapply it. The IntelliCode service automatically updates their copies.

### Open-source package

If you own a library or other package and want to help your users out with IntelliCode suggestions:

1. [Create a team model](custom-models.md#user-associated-team-models) on a codebase that has good sample usage of your library (for example, some sample code that makes a good selection of typical calls to the library).

2. [Share the link](custom-models.md#user-associated-team-models) with everyone who'll be using the library.

   For example, place the link in your library's documentation or in the *README.md* file of your repo, so it can easily be found and used.

3. Library users then [use the sharing link](#add-a-user-associated-team-completions-model) to add the model to their list, which tells IntelliCode to apply that model for completions.

Library users receive automatic updates if you retrain the model.

### Other sharing scenarios

If there are other sharing scenarios you feel are important, we want to hear about them. If you're using Visual Studio, you can [suggest a feature](/visualstudio/ide/suggest-a-feature) on Developer Community. If you're using Visual Studio Code, use the **Send feedback about** > **This page** button at the bottom of this page.

## See also

- [IntelliCode models based on your code](custom-models.md)
