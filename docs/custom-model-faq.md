---
title: IntelliCode FAQ for IntelliSense based on your code
ms.date: 12/04/2018
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
manager: douge
author: markw-t
ms.author: mwthomas
---
# FAQ for IntelliCode models based on your code

IntelliCode’s recommendations have previously been based on learning patterns from thousands of open-source GitHub repos. But what if you’re using code that isn’t in that set of repos? Perhaps you use numerous internal utility and base class libraries, or domain-specific libraries that aren’t commonly used in open-source code, and you'd like to see IntelliCode recommendations for them too. For C# users, IntelliCode can learn patterns from your code so it can make recommendations for things that aren’t in the open-source domain.

## Q. What is a model and what should I expect from it?

A model is an encapsulation of a set of rules that allow prediction of some useful information (for example, recommendations in the IntelliSense list) based on well-understood inputs.

IntelliCode’s AI-based IntelliSense has always worked on a model&mdash;the so-called "base model"&mdash;which we derived by training a machine learning model on thousands of highly rated, open-source projects on GitHub. A new service enables the creation of *custom models*. Custom models use the same learning process but are applied to your own code. Using a custom model enables IntelliCode to make recommendations for things found only in your codebase. The more code you can provide to illustrate your patterns of usage, the more capable the custom model will be of offering good recommendations.

## Q. What happens when my model is trained, and what data is sent to Microsoft?

To train a model based on your code, the IntelliCode extension extracts only those elements of the code that are needed to create a model for recommending completion values. For example, it extracts the names of classes and methods and how often they're called in different circumstances. The extracted data is transmitted to the IntelliCode service, which uses a machine learning algorithm to extract a model for your code. It then returns the model to your computer where it's merged with the base model.

We don’t track your keystrokes or extract the values of literals (such as strings) from your code. All communication with the IntelliCode service is over HTTPS (see [how secure is this]() for more information).

If you wish to inspect the detailed contents of the extracted data file, you can do so during the training process by following the "show extracted data" link. If you like, you can try the process on a public or sample codebase first to see the kind of data we collect.

## Q. How secure is this? Can others see the models I create?

Your models are private to you and those you explicitly share them with via the "share" function.

All data you send to and receive from the IntelliCode service is transmitted over HTTPS. You must also be authenticated via your Visual Studio account in order to communicate with the service. Models can only be retrieved either by the authenticated user who submitted the extracted data for training, or by someone they explicitly authorized. This means your model and what is learnt about your code stays private to you and your collaborators.

We expect that organizations may wish to have ways of sharing models that are unique to their organizational structure, access control models, et cetera. We’re interested to hear more from you about this subject.

## Q. How often should I retrain the model – does it get better over time?

For AI-enhanced IntelliSense recommendations, the model becomes stale if you change method usages and names, add new methods, et cetera. The model won't know about those new usages and names until you train it again. If you’ve made numerous changes or additions to a codebase, consider retraining any models that were created from it.

Retraining is manual at present, so the model won't improve unless you elect to retrain. In the future, we’d like to automate this process. For example, we're considering ways you may be able to include retraining as part of your continuous integration (CI) build steps.

## Q. Are there limits to the amount of training I can or should do?

There is no benefit to retraining your model unless you’ve made significant code changes and are looking to see those changes reflected in your recommendations from IntelliCode.
In our current experimental preview release, we're not limiting training by default, but may do so if it's necessary to maintain acceptable service performance. Future versions of the service may impose limits to the amount of retraining you can perform.

## Q. How much does this service cost? Is there a free tier?

IntelliCode will always have a substantive free tier. During the free preview, we are evaluating capabilities that may be charged for once we exit preview

## Q. What else is coming? What's the roadmap? What can I expect?

We're actively working to expand IntelliCode’s AI-assisted development capabilities. We're excited to share them publicly as they become available. You can sign up for news and updates at [https://aka.ms/intellicode](https://aka.ms/intellicode) to be the first to know when new capabilities are available.

## Q. What languages AND TOOLS are supported?

Currently, only C# users in Visual Studio 2017 version 15.7 and higher can take advantage of training models on their own code in the experimental preview. We'll track feedback on the experience of C# and refine the training service as we proceed.

Other languages and tools (Visual Studio: C++, Java, XAML; Visual Studio Code: JavaScript, TypeScript, Python, and XAML) are supported with models pre-trained on a large number of open-source codebases.

## Q. Can I opt out and have my models removed?

Yes. You can delete your models through the IntelliCode training user interface in Visual Studio, which removes them from the service.

## Q. Is there a restriction on the size of the model, or sizes and numbers of models I can train?

In our current experimental preview release, we don't limit training. In the future, we may impose training limits if we can't maintain acceptable service performance.

## Q. What size codebase is ideal for training a model?

To get useful predictions, a codebase should represent the common usage patterns for the APIs, objects, and methods that you use. The larger the variety of common usages that a codebase illustrates, the more useful the resulting model is.

Training your own model is useful for those cases where your frequently used classes are either private to your codebases or aren't common in the open-source codebases we train with. All IntelliCode users get the benefit of the "base model" that's trained on thousands of public repos, for commonly used classes. Unless you have unusual usage patterns on those common classes, you won’t need to train on your own code to see good recommendations for them.

## Q. How many people in my team can I share the model I create with?

You can share your model with as many people as you like via the sharing feature. Those team members won't be able to retrain the model, but will see the same completion recommendations as you do.

## See also

- [General IntelliCode FAQ](faq.md)
- [IntelliCode extension for Visual Studio](intellicode-visual-studio.md)
- [IntelliCode extension for Visual Studio Code](intellicode-visual-studio-code.md)
