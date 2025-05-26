---
title: Custom Blocks
excerpt: A guide on how to use Custom Blocks and getting access
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
> 🚧 Trial Expiry
>
> The Custom Block feature trial is now over. Stay tuned for more updates regarding a broader rollout in the future.

## Introducing: Custom Blocks

Custom Blocks extends your steps menu by offering an opportunity to build your own custom UI components to use on the Voiceflow canvas. 

![Dev to Design Handoff](https://files.readme.io/746b14b-Screen_Shot_2022-09-29_at_11.43.01_AM.png)

> 📘 What is a feature trial?
>
> We are releasing Custom Blocks to a selection of users who have expressed interest in the feature and are willing to provide product feedback to inform how this evolves.
>
> **As a result of this being an experimental feature, we recommend to avoid using custom blocks in any production assistant.**

### Get started

To quickly get up to speed on the feature, below is a walkthrough video using Custom Blocks to support a Telegram assistant. 

<HTMLBlock>{`
<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/6aa025c3e6984cdf93d542061f1ecc4f" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

***

## Step 1 | Create a new block

To start, navigate to the *Library* menu, as shown in the imagine below, where you can find the *Custom* tab. 

The *Custom* tab is where you will find all your available custom blocks that are ready to drag onto the canvas and it is where you will find the option to create new blocks. 

To create a new block:

1. Select *Add Custom Block*.

![Canvas](https://files.readme.io/b5353b4-Screen_Shot_2022-09-27_at_8.57.50_PM.png)

2. In the builder modal, configure your block using the below options:

   2.1 **Name**: This will be the name of your new block and it will also be the name of the trace sent from the Voiceflow Dialog Manager (more information below). 

   2.2 **Action Body**: This is where you will add your UI object that will be returned by the Dialog Manager API. For any dynamic values which require input from the runtime, surround them with curly braces `{var}`, which will render them as inputs when used on the canvas. 

   2.3 **Wait for user input**: By checking this box, your custom block will wait for the user to interact with this element for continuing the conversation. An example of this would be a button or carousel step. 

   2.4 **Paths**: For steps that require interaction, here is where you can specify the branches the conversation can take depending on the user response. To add additional path options, select the **+** sign and name your new path.  For non-interaction steps, the conversation will always continue down the default path.

3. Once you are happy with your setup, select *Add Custom Block* to save your new step. 

![Create Block](https://files.readme.io/d7f5e74-Screen_Shot_2022-09-27_at_9.01.03_PM.png)

## Step 2 | Use new block on canvas

Once you've added the new block to your canvas, you will notice that the dynamic values that were set in your *Action Body* are now available as input fields in the step configuration panel. The paths that are also available to connect into other blocks in your design. 

The input fields support both hardcoded values and Voiceflow variables. 

![Design View for Block](https://files.readme.io/f9c63fa-Screen_Shot_2022-09-27_at_9.02.46_PM.png)

## Step 3 | Update or delete block

**Edit**

To update an existing block, navigate to your Custom menu and right-click on *Edit*.  **NOTE:** Every instance of the edited block on your canvas will immediately be updated with the changes. 

![Edit block](https://files.readme.io/de18c93-Screen_Shot_2022-09-28_at_9.19.25_AM.png)

**Delete**

To remove the custom block, right-click on which block you would like to delete and select *Delete* . **NOTE:** All data related to this block will be removed and you will see that all instances of this block will be empty and require manual deletion from the canvas. 

![Delete block](https://files.readme.io/1911caa-Screen_Shot_2022-09-28_at_9.30.03_AM.png)

## Step 4 | Integration

For the integration, below you will see an example trace type from a custom block which is returned from the Voiceflow Dialog Manager and a payload that can be mapped to your front-end client:

```json
[
  //Custom trace
  {
    "type": "Example", // name of block
    "payload": "{"latitude": 2.338629,"longitude": 48.86029}", // returned body with inputs
    "defaultPath": 0,
    "paths": [
      {
        "event": {
          "type": "Path A" // path name to return as action
        }
      },
      {
        "event": {
          "type": "Path B"
        }
      }
    ]
  }
]
```

**For interaction-based steps**, the client will be required to determine which action to take next based on the user input. To trigger the next action, return an action request with the type being the path to conversation should continue down. 

```json
{
  "action": { "type": "Path A" }
}
```

## Step 5 | Say Hello 👋🏼 to your new toolbox

With Custom Blocks, you will now have a selection of new options to build your assistants. We recommend to bring in your UX developers to the Voiceflow canvas, leveraging their specialty in the front-end to build new steps that designers can use to create new flows and new use-cases, bridging the gap of what is in the design and in production. 

Happy Building. 

***

## Future Improvements

Below are some known limitations with the current feature which we will be addressing in a later version. 

* **Rendering UI in Voiceflow prototype.** To test your custom blocks, you will be required to connect directly to your chat or messaging channel which supports rendering the component. We are investigating adding more support to this in Voiceflow in the future
* **Dynamic Responses**. As the *Action Body* only supports hardcoded text, there is no option to modify the response based on the type of data that is input. In a later iteration, we will be looking to add support to dynamically produce the response returned via the Dialog Manager API. 
* **Input types are limited to text fields.** To improve designer accessibility and UX, we will be evaluating the addition of a block kit to support a wide variety of input types in the step configuration panel.
* **Scoped to a project.** Custom blocks will be scoped to the project and will not support copy/pasting between projects. In a future release, we will be making custom blocks global at a workspace level so they can be used in any project.
