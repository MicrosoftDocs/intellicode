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

IntelliCode's custom model creation facility lets you get IntelliCode completions for code that is not in the public "Base Model" which we train on open source code, for example types you own yourself, or specialist common components and libraries. However, you don't want everyone who collaborates on your code to have to train their own model or worry about keeping it up to date.

To solve these problems, IntelliCode has a model sharing feature which lets you share _any_ model you've created with _anyone you provide a link to_, and also keeps those who use the link updated whenever you retrain your model. 

# How models get applied 
Before talking about using shared models, it's useful to understand how Intellicode applies all models to generate its recommendations. 

Models are applied to a given user by merging together, per signed-in user:

- The "base model" for the language they are using (trained on 1000s of public GitHub repos)
- Any custom models they have trained themselves
- Any custom models they have added to their profile from sharing links provided by others (via "add model")

This means you don't need to micromanage which models apply to which solution or codebase.

# How to enable common sharing scenarios
Next we'll describe how to set up for some common cases:

- I have a codebase that's a good example for usage for other codebases I work on with others
- I own a library and want to share out good examples of usage to consumers of the library


# What to do when you have a codebase that's a good example of usage 
IntelliCode's custom model training learns from the usage of code in the codebases you train it on. It's not uncommon that you have a completed or mature codebase that is actually a great example of your usage of your own types and/or common components, that you want to leverage when you and your collaborators start work on your next project of that type. The new project, being new, has no usage to learn from. So what do you do?

The best approach here is to [train a custom model](visualstudio/intellicode/custom-model-faq/#q-how-do-i-train-a-model) on the completed codebase, then share it with everyone who will be using the new codebase. They can then [use the sharing link](visualstudio/intellicode/custom-model-faq#q-how-do-i-use-a-sharing-link-to-see-a-model-that-someone-else-shared-with-me) to tell IntelliCode to apply that model for completions in the new codebase too. If you need to re-train the custom model, there's no need for consumers of the link to re-apply it - the system will take care of updating their copy automatically for you.

# What to do when you have a library and want to share out a model that embodies good usage of that library
In the same way, if you own a library, you can [train a custom model](visualstudio/intellicode/custom-model-faq/#q-how-do-i-train-a-model) on a codebase that has good sample usage of that library, then share it with everyone who will be using the library so they see completions.

We know that there are likely more scenarios for sharing, and would love to hear your feedback.

