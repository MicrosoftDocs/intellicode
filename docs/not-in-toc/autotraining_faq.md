---
title: Autotraining Visual Studio IntelliCode custom models for completions
titleSuffix: Visual Studio IntelliCode
ms.date: 08/03/2020
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
author: catycaldwell
ms.author: ccaldwel
manager: jillfra
---
# IntelliCode completions learned from your own code

Visual Studio IntelliCode uses machine learning to offer useful, contextually rich code completion suggestions in-line as you code.

When you enable autotraining, IntelliCode will train a machine-learning model based on patterns in your code, giving you IntelliCode's starred contextual completion suggestions for your own types, and other types not commonly found in open source. IntelliCode will retrain this model as you update your code, ensuring that the model changes alongside your code.

Autotraining models for IntelliCode custom code completions is a preview feature capability in [Visual Studio version 16.7](https://docs.microsoft.com/visualstudio/releases/2019/release-notes-v16.0) and above and are disabled by default. You can enable autotraining these custom code completions via the infobar prompt after a successful build, through the IntelliCode UI found at **View** > **Other windows** > **IntelliCode**, or through **Tools** > **Options** > **IntelliCode**. They are currently available only for C# and C++ code.
   
## How does autotraining models for IntelliCode custom code Completions work?

After successfully building a solution, you may be prompted to enable IntelliCode to autotrain a model for IntelliCode completions for that solution. 
By enabling autotraining models for IntelliCode completions, IntelliCode will train a machine-learning model for completions for the active solution and only the user who has access to the solution on the machine where the autotraining was enabled will have access to the respective model. If you'd like to share your custom code completions with anyone who can access your repository, you should [set up automatic training Team completions as part of your CI workflow](https://aka.ms/vsic-teamcompletions-quickstart).

**NOTE:** For autotraining a model for IntelliCode custom code completions for your solution in Visual Studio, there are no source control requirements. However, if you'd like to share your custom completions with your team, your codebase must be under Git source control and pushed to a remote to create a repository-associated model.

### Enabling autotraining models for custom code completions in Visual Studio

To enable automatic model training for IntelliCode completions for your code in Visual Studio, follow these steps:

1.  Open the solution or repository folder in Visual Studio.
1.	Enable autotraining a model for custom code Completions via the infobar prompt after a successful build, through the IntelliCode UI found at **View** > **Other windows** > **IntelliCode**, or through **Tools** > **Options** > **IntelliCode** setting "Autotraining team models for IntelliSense completions" or by searching for **"IntelliCode autotrain"** in Visual Studio Search (**Ctrl + Q**).
1.	Upon successful creation of the model, it will be automatically downloaded to Visual Studio. You can track the model’s progress by opening the Output Window and switching to IntelliCode in the dropdown OR in **View** > **Other windows** > **IntelliCode**. 

   > [!NOTE]
   > Be sure that you have installed at least [Visual Studio version 16.7 Preview 3](https://docs.microsoft.com/visualstudio/releases/2019/release-notes-v16.0) or above. Once the preview has been installed, you can enable automatic models for custom code completions through the infobar after a successful solution build OR via **Tools** > **Options** > **IntelliCode**.

Once the training is complete, try writing some code using the classes/types that are particular to your repo - you should see starred suggestions for the most common cases.

Once you are happy with the custom code completions on your solution, you can set up to automatically create, retrain, and share IntelliCode custom code completions with your entire dev team as part of your continuous integration pipeline in [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) or [GitHub Action for Team Completions](https://aka.ms/vsic/github).

## What happens when you enable IntelliCode to autotrain models for custom code completions?

When you enable IntelliCode to kickoff training and/or autotraining your model for custom code completions:
* We analyze your code locally.
* We extract a summary file with metadata on your types and their usages.
* We securely upload it to the IntelliCode service and train a completions model tailored to your code.
* Your completions model is never shared with those who have access to your repo (if a cloned git repository). 
* We allow you to delete your model at any time and/or cancel the model training directly in the IntelliCode UI found at **View** > **Other windows** > **IntelliCode**. Simply uncheck the box in the UI to delete the model for the custom code completions immediately.
* You can refresh your learned patterns directly in the IntelliCode UI found at **View** > **Other windows** > **IntelliCode**.

You will see the training progress in your Visual Studio output window's IntelliCode section or IntelliCode UI found at **View** > **Other windows** > **IntelliCode**. Once the training is complete, you will be able to see your summary and the new model tailored to your code. You can then try writing some code using the classes/types that are particular to your repo - you should see starred suggestions for the most common cases.  

If you want more information about what data is used and transferred in this process see [IntelliCode data and  privacy](https://docs.microsoft.com/visualstudio/intellicode/custom-models#data-and-privacy).
