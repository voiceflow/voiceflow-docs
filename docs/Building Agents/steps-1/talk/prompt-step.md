---
title: Prompt step
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The **Prompt step** allows you to incorporate advanced AI-driven responses into your conversational agents. By leveraging pre-defined prompts, you can create dynamic and context-aware interactions that enhance the user experience. The Prompt step simplifies the integration of complex prompts, making it easier to design intelligent and responsive agents.

## Migrating to the Prompt step

If you're currently using the legacy AI steps, you must migrate to the Prompt step before June 3rd 2025. Follow the instructions in the video below to do so

<Embed url="https://www.youtube.com/watch?v=8zv8le6VApc" title="AI in Voiceflow is Changing: Upgrade to the New Prompt Step" favicon="https://www.youtube.com/favicon.ico" image="https://i.ytimg.com/vi/8zv8le6VApc/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=8zv8le6VApc" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252F8zv8le6VApc%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253D8zv8le6VApc%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252F8zv8le6VApc%252Fhqdefault.jpg%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

<br />

## What is the Prompt Step?

The Prompt step is a component you can add to your workflow that utilizes prompts defined in your **Prompts CMS**. It allows your agent to generate responses based on these prompts, which can include system prompts, user-agent message pairs, variables, and more. This step enables you to:

* Select an existing prompt from your Prompts CMS.
* Create a new prompt directly from the workflow.
* Edit prompts on the fly without leaving the canvas.
* Seamlessly integrate AI-generated content into your conversation flow.

## How to Use the Prompt Step

![](https://files.readme.io/f58e61e654fac3090a31b87705f8ded3c7d976a81ce9ff8de332bb5ac385b161-CleanShot_2024-11-04_at_21.41.082x.png)

**1. Adding the Prompt Step to Your Workflow**

* **Navigate to Your Workflow**: Open the workflow where you want to add the Prompt step.
* **Drag and Drop**: From the step toolbar, select the **Prompt step** and drag it onto the canvas.

**2. Configuring the Prompt Step**

When you add the Prompt step, you’ll have two options:

**Option A: Select an Existing Prompt**

1. **Select a Prompt**: Click on the dropdown menu within the Prompt step editor.
2. **Choose from the List**: You’ll see a list of prompts you’ve previously created in the Prompts CMS.
3. **Select the Desired Prompt**: Click on the prompt you want to use.
4. **No Additional Configuration Needed**: Once selected, the Prompt step is ready to use with the chosen prompt.

<Image align="center" width="70% " src="https://files.readme.io/05c330f9aa43fd3d5399d8b0612e2cbbd5f7cb044f7029fdd8a8d5177697b757-CleanShot_2024-11-04_at_21.24.012x.png" />

**Option B: Create a New Prompt**

1. **Click “New Prompt”**: Within the Prompt step editor, click the **New Prompt** button.

2. **Prompt Editor Opens**: A modal window appears, allowing you to create a new prompt.

3. **Define Your Prompt**: Enter the prompt name, description, and content as you would in the Prompts CMS.

4. **Save the Prompt**: After configuring your prompt, it will now be available in your Prompts CMS and selectable in the dropdown.

**3. Editing a Prompt from the Workflow**

* **Edit Prompt Button**: After selecting a prompt, an **Edit Prompt** button appears below the dropdown.
* **Make Changes**: Click this button to open the Prompt Editor directly from the canvas.
* **Save Changes**: Modify your prompt as needed. Changes are reflected wherever the prompt is used.

**4. Integrating the Prompt Step into Your Flow**

<Image align="center" width="75% " src="https://files.readme.io/2201646b591e92de947024f0e5e06938c333944ac8ae9954a07a4bc3c380c383-CleanShot_2024-11-04_at_21.22.222x.png" />

<br />

* **Connect Steps**: Link the Prompt step to other steps in your workflow to define the conversation path.
* **Testing**: Use the built-in prototype tool to test how the Prompt step functions within your agent.
* **Adjust as Needed**: Based on testing, you can return to the Prompt step to select different prompts or edit existing ones.

## Best Practices

**Use Clear Prompt Names**

* **Consistency**: Ensure prompt names are descriptive to make selection easier.
* **Organization**: Helps maintain clarity, especially when managing multiple prompts.

**Test Your Prompts**

* **Validate Responses**: Use the prototype tool to ensure the prompt generates the desired output.
* **Variable Checks**: Confirm that any variables used in the prompt are correctly populated at runtime.

## Example Scenario

Imagine you’re building an agent that provides personalized product recommendations.

**Steps:**

1. **Create a Prompt**: Define a prompt in the Prompts CMS that generates recommendations based on user preferences.

2. **Add Prompt Step**: Drag the Prompt step into your workflow where the recommendation should occur.

3. **Select the Prompt**: Choose your recommendation prompt from the dropdown.

4. **Connect Steps**: Link the Prompt step after collecting user preferences and before presenting the recommendations.

5. **Test the Flow**: Use the prototype tool to ensure the agent provides appropriate recommendations.

<br />

## Learn more

* [Prompt CMS and Editor](https://docs.voiceflow.com/docs/prompts-cms-and-editor): Explore the central hub for creating, testing, and managing prompts within your agent.
* [Set step](https://docs.voiceflow.com/docs/variables-set): Discover how to dynamically assign prompt outputs to variables for greater control over agent behaviour.