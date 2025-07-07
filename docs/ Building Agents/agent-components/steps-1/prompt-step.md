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

<br />

## What is the Prompt Step?

The Prompt step is a component you can add to your workflow that utilizes prompts defined in your **Prompts CMS**. It allows your agent to generate responses based on these prompts, which can include system prompts, user-agent message pairs, variables, and more. This step enables you to:

* Select an existing prompt from your Prompts CMS.
* Create a new prompt directly from the workflow.
* Edit prompts on the fly without leaving the canvas.
* Seamlessly integrate AI-generated content into your conversation flow.
* Output customized structured JSON for data formatting.

<br />

## How to Use the Prompt Step

![](https://files.readme.io/f58e61e654fac3090a31b87705f8ded3c7d976a81ce9ff8de332bb5ac385b161-CleanShot_2024-11-04_at_21.41.082x.png)

<br />

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

<br />

## Best Practices

**Use Clear Prompt Names**

* **Consistency**: Ensure prompt names are descriptive to make selection easier.
* **Organization**: Helps maintain clarity, especially when managing multiple prompts.

**Test Your Prompts**

* **Validate Responses**: Use the prototype tool to ensure the prompt generates the desired output.
* **Variable Checks**: Confirm that any variables used in the prompt are correctly populated at runtime.

## Structured JSON Output

Structured outputs allow your AI to return predictable, machine-readable JSON objects instead of plain text. This is useful when responses need to be **parsed or reused programmatically** inside your Voiceflow assistant.

***

#### What are Structured Outputs?

Structured outputs use a JSON schema to constrain and validate the format of AI responses. This ensures the returned data follows a specific shape, making it easier to use within:

* Loops and repeat blocks
* Conditional branches
* Dynamic UI components (e.g. buttons, tables)
* Variable mapping

Structured output is configured in the **Prompt Step** by enabling the `JSON output` toggle.

***

#### When to Use Structured Output

Use structured output when:

* You need to extract and reuse parts of an AI response
* You expect a list of formatted results (e.g. cities, products, FAQs)
* You want predictable, deterministic formatting for validation or logic

***

#### Example Schema

**Prompt**

```
get me the top 5 cities in {country} according to their population
```

**Output Schema**

```json
{
  "type": "object",
  "required": ["cities"],
  "properties": {
    "cities": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "name": { "type": "string" },
          "population": { "type": "number" }
        },
        "required": ["name", "population"],
        "additionalProperties": false
      }
    }
  },
  "additionalProperties": false
}
```

**Expected Output**

```json
{
  "cities": [
    { "name": "Tokyo", "population": 37393128 },
    { "name": "Delhi", "population": 30290936 },
    { "name": "Shanghai", "population": 27058480 },
    { "name": "São Paulo", "population": 22043028 },
    { "name": "Mexico City", "population": 21918936 }
  ]
}
```

***

#### Configuration Summary

| Setting           | Description                                                                |
| ----------------- | -------------------------------------------------------------------------- |
| **Prompt Step**   | Used to send the instruction to the AI                                     |
| **JSON Output**   | Toggle this ON to enable structured response mode                          |
| **Output Format** | Paste the JSON Schema here                                                 |
| **Model Choice**  | Lower-temp models (e.g. GPT-4o mini, Temp 0.3) recommended for consistency |

***

### 🎥 Reference Video

[Watch the video guide on structuring JSON output →](https://your-video-link-here.com)

## Prompt Step; Example Scenario

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