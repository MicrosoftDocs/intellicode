---
title: IntelliCode Visual Studio Inline Completions
ms.date: 10/10/2021
ms.prod: visual-studio-family
ms.technology: intellicode
ms.topic: conceptual
description: IntelliCode Visual Studio Inline Completions
author: juihanamshet1
ms.author: juihanamshet
manager: jmartens
---

# Visual Studio IntelliCode Inline Completions

IntelliCode Inline Completions predicts the next chunk of your code based on your current code so far, and presents it as a gray text inline suggestion. Think gray text autocompletion that you see when typing emails but for code. This feature will be available in Visual Studio 2022. 

![Screenshot of Inline Completion by IntelliCode in Visual Studio.](media/intellicode-vs-wlc-small.png)

## How it works

IntelliCode uses a large scale transformer model, trained on around half a million public, open-source repos from GitHub. This model makes predictions on what you'll type next based on a rich knowledge of what you have coded so far, which includes:
- Variable names and positions
- Libraries you're using
- Functions in nearby code
- The IntelliSense list

The model runs on your local machine. This allows the feature to be available in offline and air gapped environments. The feature supports many programming languages including Python, JavaScript, TypeScript, C#, and Visual Basic.  

## Two Modes

IntelliCode provides completions in two ways - one, when the user is typing and two, when the user has an item selected in the IntelliSense list. 

### Mode 1: Inline completions when typing
When the user is typing, we show inline completions which can be accepted by "Tab to accept". To dismiss the prediction, you can use the `Esc` or `Delete` keys. 

![Screenshot displaying Tab to accept inline completion.](media/intellicode-vs-wlc-small.png)

### Mode 2: Inline completions when IntelliSense item is selected
When the user has an item from the IntelliSense list selected, IntelliCode uses what the user has typed + what the user has selected as the context for providing predictions. In this case, you will see "Tab Tab to accept" prediction. The first Tab accepts the selected item from the IntelliSense list and the second Tab accepts the Inline Completion. To dismiss the prediction, you can use the `Esc` or `Delete` keys. 

![Screenshot displaying Tab Tab to accept selected completion item and inline completion.](media/intellicode-vs-wlc-tabtab-small.png)

### Accept or Dismiss inline completions
By default, the `Tab` key is used to accept inline completions. To change the default accept key, go to Tools -> Options -> IntelliCode -> Completions for whole lines of code. Enable the setting named `Apply completions for whole lines on right arrow`. 

![Screenshot of Settings menu to change setting to make right arrow as accept character.](media/intellicode-vs-wlc-change-to-rightarrow.png)

This will change the accept key from `Tab` to the right arrow `->`

![Screenshot of Settings menu to change right arrow to accept inline completion.](media/intellicode-vs-wlc-rightarrow.png)

To dismiss inline completions, the `Esc` or `Delete` keys can be used. 


## Privacy 

[See Privacy](intellicode-privacy.md#intellicode-line-completions)

## Controlling Inline Completions

You can control the inline completions feature using the small purple lightbulb shown at the bottom right of the editor, next to the zoom control. 

![Screenshot of Setting for Turning IntelliCode Inline Completions On/Off.](media/intellicode-vs-wlc-quietmode-small.png)

The first setting, `Show completions for lines of code` allows you turn this inline completions on or off. 

The second setting, `Wait for pauses in typing before showing line completions`, when enabled, will make inlined completions only show up if the user has paused typing.The user may prefer this if they find the inline completions distracting in the default mode.

The third setting, `Show completions on new lines` can be turned on or off depending on whether the user wants to see line completions when they have entered a new line i.e. by pressing `Return` or `Enter`. 

## Providing Feedback 
Click on the Feedback icon on the top right of Visual Studio to file a feedback ticket. Optionally, you can upload your IntelliCode log files to the feedback ticket in order to provide us with additional context. Make sure you review the contents of the log files and address any privacy concerns you may have. This data, when shared with us, will not be used for any purpose other than providing support assistance to you. You can find the logs at `%LOCALAPPDATA%\Temp\VSFeedbackIntelliCodeLogs`

![Screenshot of submitting feedback for IntelliCode.](media/intellicode-vs-wlc-feedback-small.png)




