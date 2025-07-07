---
title: Prompt step
excerpt: Generate responses to a user's question.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<Image align="center" src="https://files.readme.io/3dec4418994820012e8a1be5ba75458022e0ac7a8f4651020b332a83fac576b9-Prompt_1.png" />

<br />

The Prompt step allows your agent to generate responses to a user's message using an LLM. It’s useful for injecting AI into a specific point in your flow, such as generating product suggestions, summarizing information, or rephrasing user input. Each prompt step will generate a single response - if you're looking to build a fully agentic conversational agent, we recommend using the [Agent step](doc:agents).

<br />

## Basic usage

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSzVYvHMyQXUw9e3lryuWbOH7E5ApCIBaitDYK" />

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