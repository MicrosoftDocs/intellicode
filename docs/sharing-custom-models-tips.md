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

IntelliCode's custom model creation facility is useful because it allows you to get IntelliCode completions for code that is not in the public "Base Model" training set, for example types you own yourself, or specialist common components and libraries. However, you don't want everyone who collaborates on your code to have to train their own model in order to benefit. Nor do you want to have to worry about everyone keeping their model up to date.

To solve these problems, IntelliCode has a model sharing feature which lets you share any model you've created with anyone you provide the link to, and also keeps those who use the link updated whenever you retrain your model. 

# Model application process

In using shared models, it's useful to understand how Intellicode applies all models to generate its recommendations. 

Models are applied to a given user by merging together, per signed-in user:

- The "base model" for the language they are using (trained on 1000s of public GitHub repos)
- Any custom models they have trained themselves
- Any custom models they have added to their profile from sharing links provided by others (via "add model")

This means you don't need to micromanage which models apply to which solution or codebase.

# How to enable common sharing scenarios

Next we'll describe how to set up for some common cases:

- I have a codebase that's a good example for usage for other codebases I work on with others
- I own a library and want to share out good examples of usage to consumers of the library
- I have a codebase I'm extending/adding to with others


