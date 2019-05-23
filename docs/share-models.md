---
title: Share custom models
ms.date: 05/21/2019
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
author: markw-t
ms.author: mwthomas
manager: jillfra
---
# How to: Share custom models in Visual Studio IntelliCode

IntelliCode has a model sharing feature that lets you share any model you've created with anyone you provide a link to. Additionally, users that have access to the shared model automatically receive the latest updates when you retrain the model.

By creating a custom model, you get IntelliCode completion recommendations for code that's not in the base model. Sharing a model with collaborators extends the enhanced IntelliSense recommendations to everyone; they don't have to create or retrain a custom model themselves.

## Share a custom model

After you've trained a model, the **Share model** button appears. Click the button to copy the sharing link. From there, you can share the link with your collaborators.

 > [!NOTE]
 > Anyone who has the sharing link can access the model and its suggestions, so make sure that everyone who receives the link is aware of this.

You can share your model with as many people as you like via the sharing feature. Team members can't retrain the model but they do see the same completion recommendations as you do.

## Add a custom model

To use a model link that someone shared with you, follow these steps:

1. (Optional) If you're using a version of Visual Studio prior to Visual Studio 2019 version 16.1, first install the IntelliCode extension.

1. Open the IntelliCode page by choosing **View** > **Other Windows** > **IntelliCode**.

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

1. [Train a custom model](custom-models.md#train-a-model) on the existing codebase.

2. [Share the link](custom-models.md#share-a-custom-model) to the model with everyone who'll be using the new codebase.

   You can do this in various ways, for example, by checking it in to your codebase's *README* file, sending it in email, posting it on a project's wiki, or via a chat channel&mdash;whatever makes sense for your collaborators.

   > [!CAUTION]
   > Anyone who has the sharing link can access the model and its suggestions. Make sure that everyone who receives the link is aware of this.

3. Collaborators then [use the sharing link](#add-a-custom-model) to add the model to their list of models, which tells IntelliCode to apply that model for completions in the new codebase too.

If you need to retrain the custom model, there's no need for collaborators to reapply it. The IntelliCode service automatically updates their copies.

### Open-source package

If you own a library or other package and want to help your users out with IntelliCode suggestions:

1. [Train a custom model](custom-models.md#train-a-model) on a codebase that has good sample usage of your library (for example, some sample code that makes a good selection of typical calls to the library).

2. [Share the link](custom-models.md#share-a-custom-model) with everyone who'll be using the library.

   For example, place the link in your library's documentation or in the *README.md* file of your repo, so it can easily be found and used.

3. Library users then [use the sharing link](#add-a-custom-model) to add the model to their list, which tells IntelliCode to apply that model for completions.

Library users receive automatic updates if you retrain the model.

### Other sharing scenarios

If there are other sharing scenarios you feel are important, we want to hear about them. If you're using Visual Studio, you can [suggest a feature](/visualstudio/ide/suggest-a-feature) on Developer Community. If you're using Visual Studio Code, use the **Send feedback about** > **This page** button at the bottom of this page.

## See also

- [IntelliCode models based on your code](custom-models.md)