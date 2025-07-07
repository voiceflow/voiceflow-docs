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

## Basic usage

To use the prompt step, add it to the canvas, connect it to a previous step, then select the prompt you'd like to use with it. If you don't already have a prompt created in your project, you'll be prompted (😉) to create one. We recommend using the templates provided at the bottom of the prompt window as a starting point.

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSzVYvHMyQXUw9e3lryuWbOH7E5ApCIBaitDYK" />

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