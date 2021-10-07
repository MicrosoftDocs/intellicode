<!-- What the feature does.
How it works.
Two modes: typing and completions-driven. Tab vs Tab Tab.
Tab to accept hint shown briefly each session.
Local model, privacy focus.
How to turn it on and off.
How to provide us with feedback. -->

# Visual Studio IntelliCode Inline Completions

IntelliCode Inline Completions predicts the next chunk of your code based on your current code so far, and presents it as a gray text inline suggestion. Think gray text autocompletion that you see when typing emails but for code! 

![Inline Completion by IntelliCode in Visual Studio](media/intellicode-vs-wlc-small.png)

## How it works

IntelliCode uses a large scale transformer model, trained on around half a million public, open-source repos from GitHub. This model makes predictions on what you'll type next based on a rich knowledge of what you have coded so far, which includes:
- Variable names and positions
- Libraries you're using
- Functions in nearby code
- The IntelliSense list

The model runs on your local machine, and covers many programming languages including Python, JavaScript, TypeScript, C# etc. 

## Two Modes

IntelliCode provides completions in two ways - one, when the user is typing normally and two, when the user has an item selected in the IntelliSense menu.  

### IntelliSense Completions Driven
When the user has an item from the IntelliSense menu selected, IntelliCode uses what the user has typed + what the user has selected as the context for providing predictions. In this case, you will see "Tab Tab to accept" prediction. The first Tab accepts the selected item from the IntelliSense menu and the second Tab accepts the Inline Completion. 

![Tab Tab to accept selected completion item and inline completion](media/intellicode-vs-wlc-tabtab-small.png)

If there is no item selected from the IntelliSense menu, the user sees "Tab to accept" where the Tab accepts the Inline Completion. 

## Privacy 

### Local Model 
IntelliCode uses an Onnx Runtime model which runs locally on your machine. Your code is never sent to Microsoft. 

## Turning it On/Off

In Visual Studio, you will see a small purple bulb at the bottom right of the editor. You can turn this feature on/off using this setting. 

![Turning IntelliCode Inline Completions On/Off](media/intellicode-vs-wlc-quietmode-small.png)

## Providing Feedback 

Click on the Feedback icon on the top right of Visual Studio. You can upload your log files to the feedback ticket. Log files can be found at %LOCALAPPDATA%\Temp\VSFeedbackIntelliCodeLogs

![Feedback for IntelliCode](media/intellicode-vs-wlc-feedback-small.png)




