---
title: Tips for getting the most out of sharing custom models
ms.date: 12/18/2018
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
manager: douge
author: markw-t
ms.author: mwthomas
---
# How to get the most out of sharing custom models in Visual Studio IntelliCode

IntelliCode's custom model creation feature lets you get IntelliCode completion recommendations for code that is not in the base model. However, you don't want everyone who collaborates on your code to have to train their own model or worry about keeping it up to date.

To solve these problems, IntelliCode has a model sharing feature which lets you share _any_ model you've created with _anyone you provide a link to_. Users with your shared model will automatically receive the latest updates whenever you retrain your model. 

# How models get applied 
Before talking about using shared models, it's helpful to understand how IntelliCode applies all models to generate its recommendations. 

Models are applied to a given user by merging together, per signed-in user:

- The base model for the language you are using (trained on 1000s of public GitHub repos)
- Any custom models you have trained
- Any custom models you have added to your profile from sharing links provided by others (via the "Add model" link in the Visual Studio IntelliCode UI)

This means you don't need to micromanage which models apply to which solution or codebase.

# How to enable common sharing scenarios
Next we'll describe how to set up for some common cases:

## You have a codebase that's a good example of usage for you and your collaborators' next project
Suppose you have an existing codebase that contains good patterns for using types contained in a shared library. You'd like IntelliCode to learn from usage in that codebase to kickstart you and your collaborators when you start work on your _next_ project that uses the same library. The new project, being new, has no usage to learn from. So what do you do?

The best approach here is 
- [Train a custom model](custom-model-faq.md#q-how-do-i-train-a-model) on the existing codebase
- Share it with everyone who will be using the new codebase
- Collaborators then [use the sharing link](custom-model-faq.md#q-how-do-i-use-a-sharing-link-to-see-a-model-that-someone-else-shared-with-me) to add the model to their list, which tells IntelliCode to apply that model for completions in the new codebase too
- If you need to re-train the custom model, there's no need for collaborators to re-apply it; the system will take care of updating their copy automatically for you

## You have a library and want to share out a model that embodies good usage of that library
In the same way, if you own a library
- [Train a custom model](custom-model-faq.md#q-how-do-i-train-a-model) on a codebase that has good sample usage of that library (for example if you have some sample code that makes a good selection of typical calls to the library)
- Share it with everyone who will be using the library, for example by placing the URL on your library's web site documentation
- Library users then [use the sharing link](custom-model-faq.md#q-how-do-i-use-a-sharing-link-to-see-a-model-that-someone-else-shared-with-me) to add the model to their list, which tells IntelliCode to apply that model for completions
- Library users will recieve automatic updates if you re-train the model

# Other sharing scenarios?

We know that there are likely more scenarios for sharing, and would love to hear your feedback about your particular needs. [Raise a suggestion](https://aka.ms/vsicissues) and let us know more.
