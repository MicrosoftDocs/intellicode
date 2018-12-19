---
title: Share custom models
ms.date: 12/18/2018
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
manager: douge
author: markw-t
ms.author: mwthomas
---
# How to: Share custom models in Visual Studio IntelliCode

IntelliCode's custom model creation feature lets you get IntelliCode completion recommendations for code that's not in the base model. However, you don't want everyone who collaborates on your code to have to train their own model or keep the model up-to-date.

To solve these problems, IntelliCode has a model sharing feature that lets you share any model you've created with anyone you provide a link to. Users that have access to your shared model automatically receive the latest updates when you retrain the model. 

## How models get applied 

Before talking about using shared models, it's helpful to understand how IntelliCode generates its recommendations from multiple models. Recommendations are applied to by merging together the following models:

- The base model for the language you're using (trained on thousands of public GitHub repos)
- Any custom models you've trained
- Any custom models you've added to your profile from sharing links that others gave you (via the **Add model** link in the Visual Studio IntelliCode UI)

This means you don't need to micromanage which models apply to which solution or codebase.

## How to enable common sharing scenarios

Next we'll describe how to set up model sharing for some common cases.

### You have a codebase that's a good example of usage for you and your collaborators' next project

Suppose you have an existing codebase that contains good patterns for using types contained in a shared library. You'd like IntelliCode to learn from usage in that codebase to kickstart you and your collaborators when you start work on your next project that uses the same library. The new project, being new, has no usage to learn from. So what do you do?

The best approach here is:

1. [Train a custom model](custom-model-faq.md#how-to-train-custom) on the existing codebase.

2. [Share the link](custom-model-faq.md#how-to-share-custom) to the model with everyone who'll be using the new codebase. You can do this in various ways, for example by checking it in to your codebase's README file, sending it in email, posting it on a project's wiki, or via a chat channel you all use&mdash;whatever makes sense for your collaborators.

   > [!NOTE]
   > Anyone who has the sharing link can access the model and its suggestions, so make sure that everyone who receives the link is aware of this.

3. Collaborators then [use the sharing link](custom-model-faq.md#q-how-do-i-use-a-sharing-link-to-see-a-model-that-someone-else-shared-with-me) to add the model to their list, which tells IntelliCode to apply that model for completions in the new codebase too.

If you need to retrain the custom model, there's no need for collaborators to reapply it. The system takes care of updating their copy automatically for you.

### You have an open source package and want to share out a model that helps users incorporate the package into their code

If you own a library or other package and want to help your users out with IntelliCode suggestions:

1. [Train a custom model](custom-model-faq.md#how-to-train-custom) on a codebase that has good sample usage of that library (for example, if you have some sample code that makes a good selection of typical calls to the library).

2. [Share the link](custom-model-faq.md#how-to-share-custom) with everyone who'll be using the library. For example, place the link on your library's documentation or in the README.md of your repo, so it can easily be found and used.

3. Library users then [use the sharing link](custom-model-faq.md#q-how-do-i-use-a-sharing-link-to-see-a-model-that-someone-else-shared-with-me) to add the model to their list, which tells IntelliCode to apply that model for completions.

Library users receive automatic updates if you retrain the model.

## Other sharing scenarios

We know that there are likely more scenarios for sharing, and would love to hear your feedback about your particular needs. [Raise a suggestion](https://aka.ms/vsicissues) and let us know more.
