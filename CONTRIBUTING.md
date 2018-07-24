<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# Contributing

## TLDR

In short:

- **Known issues:** See [bugs](https://github.com/MicrosoftDocs/intellicode/issues) and up-vote using a 👍 reaction.
- **VS Code bugs:** [Log a new issue](https://github.com/MicrosoftDocs/intellicode/issues/new). Include any OUTPUT window log entries from VS-IntelliCode and Python with the bug.
- **VS bugs:** [Help > Send Feedback > Report a Problem...](https://docs.microsoft.com/en-us/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) Repro the problem before sending and logs will be auto-attached.

More details below.

## Up-Vote an existing problem report or feature request

If you are wondering if someone has already encountered a problem or requested a feature, you can check out [open issues for VS Code IntelliCode](https://github.com/MicrosoftDocs/intellicode/issues) or [developer community for Visual Studio](https://developercommunity.visualstudio.com/search.html?f=&type=question+OR+problem+OR+idea&type=question+OR+problem+OR+idea&c=&redirect=search%2Fsearch&sort=relevance&q=IntelliCode). 

If you find your issue already exists, feel free to make relevant comments and add your [reaction on github](https://github.com/blog/2119-add-reactions-to-pull-requests-issues-and-comments). Use a reaction in place of a "+1" comment.

👍 - upvote

👎 - downvote

## File a problem report

### Step 1 - [Optional] Check output logs (VS Code)

If you're seeing an error pop up that is not very descriptive, and you are working in Visual Studio Code, the output logs can sometimes help you understand if this is a known issue.  Simply go to the "Output" window and select the "VS IntelliCode" log stream and the "Python" log stream. Including the contents of these logs can also help us diagnose issue reports.

### Step 1A - check to see if the problem has already been reported

- For Visual Studio users, check for existing issues by searching the [developer community](https://developercommunity.visualstudio.com/search.html?f=&type=question+OR+problem+OR+idea&type=question+OR+problem+OR+idea&c=&redirect=search%2Fsearch&sort=relevance&q=IntelliCode) for items relating to IntelliCode. 
- For Visual Studio Code users, search the GitHub [issue repository](https://github.com/MicrosoftDocs/intellicode/issues).

### Step 2A - File a Visual Studio problem (if using Visual Studio when you see the issue)

If you're using IntelliCode in Visual Studio, it has a built in feedback mechanism via the "Report a Problem..." tool that provides the engineering team detailed information about your installation that you should use to log bugs or problems you encounter when using VS.

Logs will be automatically attached.

Note that after your problem report is filed, it may be converted to a [GitHub issue](https://github.com/MicrosoftDocs/intellicode/issues) for future tracking if it applies to multiple clients or turns out to be a feature request. In this event, a link to the corresponding GitHub issue number will be referenced in comments on your raised problem report. 

Check out the tips in "[Writing Good Problem Reports and Feature Requests](#tip-writing-good-problem-reports-and-feature-requests)" for additional suggestions.

### Step 2B - File a VS Code problems (if using VS Code when you see the issue)

1. **Capture logs:** Go to the OUTPUT window and copy the contents of the VS-IntelliCode and Python log streams after reproducing your issue.

2. **Raise a new issue:** [Click here to draft a new issue](https://github.com/MicrosoftDocs/intellicode/issues/new) and please add following information into the description:


    - **VS Code Version:**  VS Code for Mac, VS Code for Windows, and version number
    - **OS and Version:** Windows 7/8/8.1/10, macOS Sierra/High Sierra
    - **VS IntelliCode and Python Extension versions:** Mention the version you installed with your VS/VSCode.
    - **Target Platform/Language:** e.g. Python
    - **Repro steps:** Give as much detail as you can about what you did when the bug happened, and whether you can easily reproduce it

3. **Attach logs:** Paste in the logs you captured at step 1.

4. **Click "Submit new issue"**

Check out the tips in "[Writing Good Problem Reports and Feature Requests](#tip-writing-good-problem-reports-and-feature-requests)" for additional suggestions.

### Tip: Writing Good Problem Reports and Feature Requests

Here are a few tips that will help us understand your problem or feedback quickly.

> **Tip:** You may be able to save yourself some time by searching the [issue repository](https://github.com/MicrosoftDocs/intellicode/issues) to see if the problem/request already exists so you can simply up-vote it.

First, try to file a single issue per problem or request.

* Do not enumerate multiple bugs or requests in the same issue.
* Do not add your issue as a comment to an existing issue unless it's for the identical input. Many issues look similar, but have different causes.

The more information you can provide, the more likely someone will be successful reproducing the issue and finding a fix. 

* Reproducible steps (1... 2... 3...) and what you expected versus what you actually saw. 
* Images, animations, or a link to a video can really help clarify what is happening.
* A code snippet that demonstrates the issue or a link to a code repository we can easily pull down onto our machine to recreate the issue. 

Don't feel bad if we can't reproduce the issue and ask for more information! We'd rather hear about problems sooner than later.

## Other ways to contact us!

- Hit us up on Twitter using [#vsintellicode](https://twitter.com/search?f=tweets&q=%23vsintellicode&src=typd)!

## Contributing to documentation

You may contribute to Visual Studio IntelliCode's documentation by submitting pull requests to this repository. Most contributions require you to agree to a Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

## Discussion Etiquette

In order to keep the conversation clear and transparent, please limit discussion to English and keep things on topic with the issue. Be considerate to others and try to be courteous and professional at all times. This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).

For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
