---
title: IntelliSense based on your code
ms.date: 04/24/2019
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
author: markw-t
ms.author: mwthomas
manager: jillfra
---
# IntelliCode models based on your code

Use a custom IntelliCode model to get AI-assisted IntelliSense recommendations based on *your* C# codebase. Custom models are useful if you use code such as internal utility and base class libraries or domain-specific libraries that aren’t commonly used in open-source code. This is because IntelliCode’s *base model* recommendations are based solely on patterns learned from open-source GitHub repos. If you’re using code that isn’t in that set of repos, those recommendations aren't as useful to you. For C# users, IntelliCode can learn patterns from your code to make recommendations for things that aren’t in the open-source domain.

An IntelliCode model is an encapsulation of a set of rules that allow prediction of some useful information (for example, recommendations in the IntelliSense list) based on well-understood inputs. IntelliCode creates *custom* models using the same learning process as for the IntelliCode base models, except they are trained on your own code. The more code you provide to illustrate your patterns of usage, the more capable the custom model will be of offering good recommendations.

> [!NOTE]
> Custom model training is a preview feature. It is currently available only for C# code.

## How models get applied

IntelliCode generates its recommendations from multiple models by merging together:

- The base model for the language you're using (which is trained on thousands of public GitHub repos)
- Any custom models you've trained
- Any custom models you've added to your profile from sharing links that others gave you; you add a custom model by clicking the **Add model** link in the Visual Studio IntelliCode UI

You don't need to manage which models apply to which solution or codebase because IntelliCode takes care of this for you.

## Train a model

To get useful predictions, a codebase should represent the common usage patterns for the APIs, objects, and methods that you use. The larger the variety of common usages that a codebase illustrates, the more useful the resulting model is in predicting those usages.

To train a model, follow these steps:

1. Open the project or solution in Visual Studio.

1. Open the IntelliCode page by choosing **View** > **Other Windows** > **IntelliCode**.

1. Choose **Train on my code**.

   ![Train an IntelliCode model in Visual Studio](media/train-on-my-code.png)

> [!NOTE]
> You must open a solution in Visual Studio in order to train a model. You can't train on just a folder of code.

### Train on a public codebase

Before you train on your own code, you might want to create a custom model on a public codebase. You can see how the custom model affects IntelliSense, or if you're concerned about the kind of data that IntelliSense collects, you can inspect the extracted data. Some interesting samples to train on are:

- [Azure ConferenceBuddy](https://github.com/Azure/ConferenceBuddy)

   Clone the repo, open the *ConferenceBuddy.sln* solution, build to check that it's working, and then train the model. You'll find some good completions on instances of the **AskWhoTask** class.

- [Windows RSS reader](https://github.com/Microsoft/Windows-appsample-rssreader)

   Clone the repo, open the *RssReader.sln* solution, build to check that it's working, and then train the model. You'll find some good completions on instances of the **MainViewModel** class.

## Data and privacy

To train a model based on your code, the IntelliCode extension extracts only those elements of the code that are needed to create a model for recommending completion values. For example, it extracts the names of classes and methods and how often they're called in different circumstances. IntelliCode doesn't track your keystrokes or extract whole expressions, statements, or literal values (such as strings) from your code.

The extracted data is transmitted, over HTTPS, to the IntelliCode service. The service then uses machine learning algorithms to train a model for your code. It returns the model to your computer where it's merged with the base model.

### View extracted data

To inspect the contents of the extracted data:

1. Open the *%TEMP%\Visual Studio IntelliCode* directory.

1. To find and open the training for your most recent training session, sort the folder view by date (descending). The folder for your most recent training session is now at the top.

   > [!TIP]
   > There's one folder per training session in the *%TEMP%\Visual Studio IntelliCode* directory, each with a randomized name.

The folder contains the entire set of files that are sent to Microsoft when extraction is complete. The *UsageOutput* subfolder contains a JSON file that has the information IntelliCode extracts from your code to train the model. The *UsageOutput_ErrorStats* file contains any errors found when trying to build the extracted file and can help if Microsoft needs to debug issues.

![IntelliCode model-training directory ](media/model-training-directory.png)

If you want to inspect the extracted data for a different codebase before trying it on your own code, train a model on a public codebase.

### How we secure your data

Your models are private to you and those people that have the sharing links that you generate by choosing **Share model**.

All data you send to and receive from the IntelliCode service is transmitted over HTTPS. You must [sign in to Visual Studio](/visualstudio/ide/signing-in-to-visual-studio) in order to communicate with the service. Models can only be retrieved either by the authenticated user who submitted the extracted data for training or by someone they authorized by sharing the link to the model. This means that your model and what is learned about your code stays private to you and your intended collaborators.

If Microsoft needs to troubleshoot, authorized Microsoft service personnel may be granted access to your models and extracted data for diagnostic purposes only.

## Share a custom model

After you've trained a model, the **Share model** button appears. Click the button to copy the sharing link. From there, you can share the link with your collaborators.

 > [!NOTE]
 > Anyone who has the sharing link can access the model and its suggestions, so make sure that everyone who receives the link is aware of this.

You can share your model with as many people as you like via the sharing feature. Team members can't retrain the model but they do see the same completion recommendations as you do.

For more information about sharing models, see [How to: Share custom models](share-models.md).

## Retrain a model

For AI-assisted IntelliSense recommendations, the model becomes stale if you change method usages and names, add new methods, and so forth. The model doesn't know about those new usages and names until you train it again. If you've made numerous changes or additions to a codebase, consider retraining any models that were created from it.

After you make changes, you must manually retrain your model. However, there's no benefit to retraining your model unless you’ve made significant code changes and are looking to see those changes reflected in your recommendations from IntelliCode.

## Delete a model

You can remove models from your account so they can no longer be used. To do this, choose the **Delete** button on the IntelliCode training page in Visual Studio.

![Delete an IntelliCode model in Visual Studio](media/delete-model.png)

To completely remove your data from the training service, send a request to [vsintellicodedata@microsoft.com](mailto:vsintellicodedata@microsoft.com) from the personalization account you're using.

## See also

- [Tips on sharing models](share-models.md)
- [General IntelliCode FAQ](faq.md)
- [IntelliCode extension for Visual Studio](intellicode-visual-studio.md)
- [IntelliCode extension for Visual Studio Code](intellicode-visual-studio-code.md)
- [IntelliCode news and updates](https://aka.ms/intellicode)
