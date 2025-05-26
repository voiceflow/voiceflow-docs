---
title: Intents
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Intents represent the goals or purposes behind the user's input. They are the actions that the user wants to perform or the information they seek through their query. Intents guide the flow of the conversation by helping your Voiceflow agent understand what the user is trying to achieve. From inside Voiceflow, intent objects store representations of these intents with descriptions and examples, and can then be recognized to guide conversations through [Choice](https://developer.voiceflow.com/v2.0/docs/choice) or [Button](https://developer.voiceflow.com/v2.0/docs/buttons) steps for branching paths, or with [Triggers](https://developer.voiceflow.com/v2.0/docs/trigger) to jump conversation topic. See [Intents vs Entities](https://developer.voiceflow.com/v2.0/docs/intents-vs-entities) for further explanation.

# Intent CMS

Voiceflow's Intent CMS is a powerful tool that helps you define and manage the intents for your AI agent. An intent represents what a user means or intends to do when they interact with your application.

![](https://files.readme.io/1639dc0-image.png)

## Intent Table Overview

1. **Name**: Displays the name of the intent. This should be descriptive and indicative of the user's goal when triggering the intent.
2. **Description**: A brief summary that gives context to the intent, explaining its purpose within the conversational flow.
3. **Confidence**: An indicator that shows how confidently the AI can recognize and match the user's utterance to the intent.
4. **Last Editor**: Indicates the last person (user) who edited the intent. This is helpful for teams working collaboratively.
5. **Updated**: Shows when the intent was last modified, providing a timeline of changes.

The CMS allows you to sort the intents to better organize your view. Here are common sorting options you may have:

1. **Alphabetical**: Sort intents by name in alphabetical order, either A-Z or Z-A.
2. **Confidence Score**: Arrange the intents by their confidence score, either from highest to lowest or vice versa.
3. **Last Editor**: Sort by the last editor, which can be useful when tracking changes by specific team members.
4. **Updated**: Order the intents based on the most recently updated to the least recent.

# Creating an Intent

![](https://files.readme.io/f42bdee-CleanShot_2024-06-06_at_13.08.402x.png)

1. In the Intent CMS, click on the '**New intent**' button in the upper right area of the screen.
   1. *Note: Intents and Entities created in the Intent CMS are available globally within the assistant.*
2. A modal will appear prompting you to enter details for the new intent.
3. **Enter a name** for the intent in the 'Name' field—choose a name that clearly represents the user's goal, such as "Book Appointment".
4. **Provide a description** in the 'Description' text box, which explains the intent’s purpose, like "This intent is for users looking to book an appointment." It's important to add descriptions in the form of instructions because they are used for LLM intent classification.
5. Under 'Utterances,' **type in examples** of what users might say to trigger this intent, e.g., "I want to schedule a meeting," "Can I book a time for a call?"
6. If the intent requires specific information, **click the '+' icon** next to 'Required entities' to add entities like "date," "time," or "service type." 
7. **Enter the reprompt text** to the required entity. This text should guide the user to give the specific information that is missing. For instance, if the entity is 'date', the reprompt could be, "What date are you interested in?"
8. Once all information is entered, click 'Create intent' to save the new intent to your CMS.

### Creating intents with dynamic utterances

If you're looking to create an intent where the utterances include something dynamic (ie. I want to modify my \{item}) - you can simply include the entity within your utterance. This will train the system to look for any combination of the main phrase with an item.

See the **Entities** section to learn more.

<br />

## Editing Intent Details

1. In the intent editor, **select an existing utterance**, required entity or description to edit it.
2. **Add new utterances** to improve recognition by adding new utterances or clicking 'Generate' to have an LLM generate example utterances on your behalf.
3. **Remove irrelevant utterances** or required entities by clicking the '-' to remove them from the list.
4. **Add or edit your entity reprompts** in the required entities section.
5. Make sure to **update the description** if the intent's purpose has evolved over time.

![](https://files.readme.io/46412cc-image.png)

## Deleting an Intent

**Single Intent**

1. To delete a single intent, select the intent you wish to remove, and in the editor view click the '...' (more options) button, and select 'Delete' from the dropdown menu.
2. Confirm the deletion when prompted to remove the intent from your CMS.

**Bulk Deleting Intents**

1. For bulk actions, select multiple intents by selecting the checkboxes next to the intent names.
2. Once selected, on the bulk action toolbar above the table, click the 'Delete' button to initiate the bulk deletion process.
3. Confirm the bulk deletion to remove all selected intents simultaneously.

## Preview

Previewing your intent classification method is an essential step in ensuring the accuracy and performance of your agent's ability to understand your users queries. This feature simulates real-world interactions, allowing you to assess and refine the agent’s intent recognition.

![](https://files.readme.io/9af5e8d-image.png)

1. **Access the Preview**: Locate the 'Preview' button positioned in the header of the Intent CMS page.
2. **Input Your Utterance**: In the 'Utterance' field of the preview modal, enter a question or query that a user might say. This should be representative of the actual queries you expect once your agent is live.
3. **Send the Query**: After typing your utterance, click the 'Send' button. The system will process the query using the intent classification method you've selected.
4. **Review the Response**: The result will be displayed in the classification section. There are two versions of this depending on which method is configured:
   1. *Classify intents using***NLU**: The NLU classification section will show up to 10 intents triggered from the utterance, sorted by confidence score. The first result will be the selected result from the NLU. NLU intent classification is detailed further below.
   2. *Classify intents using***LLM**: An additional section called LLM classification will appear above the NLU classified intents which returns the intent triggered by the LLM. LLM intent classification is detailed further below and is much more powerful than NLU intent classification.\
      ***Note**: Only intents that are used in your agent will be seen in the results. For example, you will need to add intents to a supported step (see Usage section below) for it to be considered in preview.*
5. **Feedback**: You can optionally provide feedback by selecting the thumbs up or thumbs down button in the results section. This data will be used, in aggregate, to improve Voiceflow's intent classification services. 
   1. If you select thumbs down, there will be an option to select which intent was the intended target of your utterance.

![](https://files.readme.io/4a75a4d-image.png)

6. **Refine and Iterate**: Based on the preview results, you may find it necessary to adjust your training data or tweak the model settings to improve the accuracy of your model. You can select the 'Re-use last utterance' button to resend the previous utterance again with the updated settings.

## Tips for Effective Previewing:

* **Test with Variety**: Use a wide range of utterances to ensure robustness in the models intent classification accuracy.
* **Test with Different Settings**: View the previewing process as iterative. The goal is to continuously enhance the models ability to respond accurately. 
  * **Preview-Specific Settings**: Changes made in Preview are temporary and will not impact the agents overall settings. For example, if you wanted to try different AI models when using LLM classification, you can do so easily in the preview without updating the model used by your agent.
  * **Overriding Defaults**: To test different behaviours, you can adjust the AI model, temperature, and prompt wrapper which will override the global intent classification settings. You can see how many settings have been changed, or reset back the settings back to default by selecting the link at the top of the settings modal.

![](https://files.readme.io/922d540-image.png)

* **Permanent Changes**: If satisfied with the preview results, you must manually update these preferences in the Intent Settings to apply them globally.

![](https://files.readme.io/363bf57-image.png)

# Usage

Intents that you create can be utilized in your designs in the:

* [Trigger step](https://developer.voiceflow.com/v2.0/docs/trigger) (which used to be the intent step)
* [Button step](https://developer.voiceflow.com/v2.0/docs/buttons)
* [Choice step](https://developer.voiceflow.com/v2.0/docs/choice)

# Best Practices for Intents

* **Be specific**: Create intents that are focused on specific tasks, avoiding broad or ambiguous intents that can confuse the AI.
* **Use representative utterances**: Provide a variety of examples that cover different ways users might express the same intent.
* **Capture variability**: Include synonyms, slang, and common misspellings in your utterances to account for the diverse ways users may communicate.
* **Categorize logically**: Group intents in a way that makes sense for your application, such as by function or by the part of the conversation they belong to.
* **Maintain consistency**: Follow a consistent naming convention and structure for your intents to make them easily identifiable.
* **Update regularly**: Add new utterances based on real user interactions to keep the AI’s understanding up to date.
* **Balance quantity and quality**: While having more utterances can improve accuracy, ensure that each utterance is a quality example that adds value.
* **Analyze confidence levels**: This helps determine how well each intent is understood by the system.
* **Perform routine testing**: Testing to ensure the intents are capturing user queries accurately.

# LLM Intent Classification

## Overview

The LLM-based intent classifier introduces a novel hybrid methodology, blending traditional Natural Language Understanding (NLU) with the expansive capabilities of Large Language Models (LLMs) to classify user intents. This synthesis allows for the precision and targeted understanding of NLU with the contextual breadth and depth provided by LLMs, delivering a robust and nuanced approach to intent recognition.

![](https://files.readme.io/5c2cbc6-image.png)

## Key Features

* **Efficient Agent Building**: Unlike traditional models that require extensive datasets for training, our approach necessitates only a handful of sample utterances and an intent description. This streamlined process reduces the workload and accelerates the development of sophisticated conversational agents, enabling teams to focus on refining interactions rather than compiling large datasets.
* **Performance Enhancement**: Leveraging LLMs significantly improves intent recognition accuracy, enabling the system to understand and classify a wide array of user intents with minimal ambiguity. This results in more relevant and accurate responses, enhancing user interaction quality.
* **Predictability Through Hybrid Approach**: By combining the strengths of LLMs with traditional NLU techniques, this feature offers a balanced and predictable approach to intent classification. This hybrid model ensures reliability in classification while embracing the advanced capabilities of LLMs for context understanding and ambiguity resolution.
* **Customization Flexibility**: The system is designed with customization at its core. Developers can modify the prompt wrapper code to perfectly align with their specific use case, allowing for a tailored conversational experience that meets the unique needs of their application.

> 📘 Example template
>
> Download our Banking Agent template [here](https://drive.google.com/uc?export=download\&id=1hNdxZ4KSiBWVO0R8l7vCNVFmsQsiLKG_) to start testing immediately.

## How It Works

### Step 1: Initial Intent Classification

* **Process**: The user's utterance is sent to the Natural Language Understanding (NLU) system, requesting classification.
* **Outcome**: The NLU returns the most probable intent and its entities, alongside a list of max. 9 alternative intents with confidence scores. This result acts as the "NLU fallback" in case subsequent steps encounter issues.

### Step 2: Metadata Fetching and Prompt Generation

* **Process**: Upon receiving the intents, the system fetches associated intent descriptions for each intent. A custom or default prompt is then generated using the prompt wrapper.
* **Fallback**: In case of errors during intent fetching or prompt generation  the system resorts to the "NLU fallback."

### Step 3: Interaction with LLM

* **Process**: The generated prompt is passed with specific metadata settings, including temperature, to the selected AI model.
* **Validation**: The LLM response is parsed to confirm if it represents a valid intent name. Failure to identify a valid intent triggers the "NLU fallback."

### Step 4: Entity Filling and Final Intent Classification

* **Process**: For intents associated with entities, the original utterance is re-evaluated by the NLU, focusing solely on the identified intent to populate the necessary entities.
* **Outcome**: The NLU returns the refined intent classification complete with entities, ready for use within the conversational flow.

<Image align="center" className="border" width="70% " border={true} src="https://files.readme.io/593acd3-image.png" />

## Training Data Requirements

* **Utterance**: Supply at least one example utterance per intent to give the NLU training data necessary to fetch up to 10 relevant intents.
* **Clear Intent Descriptions**: Accompany utterances with a direct intent description, setting explicit conditions for when the intent should be triggered. *Examples* include:
  * *Customer Support Inquiry*: "Trigger this intent when the user is seeking assistance with their account, such as password reset or account recovery."\
    *Product Inquiry*: "Trigger this intent when the user inquires about product features, availability, or specifications."\
    *Booking Request*: "Trigger this intent when the user wants to make a reservation for services like dining, accommodation, or transportation."
* **Efficient Learning**: With just an utterance and a description, LLMs leverage their pre-trained knowledge to effectively classify intents, requiring far less data than traditional methods.

To help with generating intent descriptions here is a prompt template to help:

```
Given the following user utterances and the intent name, generate a concise intent description that begins with "Trigger this intent when":

Intent Name: YOUR INTENT NAME HERE
User Utterances:
Utterance here
Utterance here
Utterance here
...

---

Intent Description:
```

## Integration Steps

* **Enable LLM Intent Classification**: This feature can be activated within your project's settings, within the Intent page settings menu.
* **Configure Prompt Wrapper (*optional*):** Specify the logic for prompt generation, ensuring alignment with your conversational model's requirements. A default prompt wrapper is provided for immediate use.
* **Customize Settings**: Tailor the performance using model selection and temperature settings to fine-tune performance and response characteristics.

## Understanding the Prompt Wrapper

The prompt wrapper serves as a crucial intermediary layer, which dynamically crafts the prompts that are sent to the LLM for intent classification. It is essentially a piece of code that translates the agent’s needs into instructions that the language model understands and can act upon.

* **Customization of Prompt Logic:** Developers can tailor the prompt wrapper to fit the specific needs of their conversational model. This includes defining how user utterances are interpreted and setting the conditions for intent classification.
* **Default Prompt Wrapper**: A default template is provided to ensure quick deployment and **should satisfy most agent requirements**. It structures the information by introducing the AI’s role, the actions and their descriptions, and then it poses the classification challenge based on a user utterance.

Here is the default prompt wrapper:

```javascript
export default async function main(args) {
  const prompt = `
You are an action classification system. Correctness is a life or death situation.

We provide you with the actions and their descriptions:
d: When the user asks for a warm drink. a:WARM_DRINK
d: When the user asks about something else. a:None
d: When the user asks for a cold drink. a:COLD_DRINK

You are given an utterance and you have to classify it into an action. Only respond with the action class. If the utterance does not match any of action descriptions, output None.
Now take a deep breath and classify the following utterance.
u: I want a warm hot chocolate: a:WARM_DRINK
###

We provide you with the actions and their descriptions:
${args.intents.map((intent) => `d: ${intent.description} a: ${intent.name}`)}
You are given an utterance and you have to classify it into an action based on the description. Only respond with the action class. If the utterance does not match any of action descriptions, output None.
Now take a deep breath and classify the following utterance.
u:${args.query} a:`;

  return { prompt };
}
```

Here is a detailed breakdown of the default prompt wrapper's components:

**Function Declaration**

```javascript
export default function main(args) {
```

* **Purpose**: Declares and exports a default function named main, making it accessible to other parts of the application.
* **Parameters**: `args` - This object contains arguments passed into the function, which in this context, includes the intents (name and description) returned by the Voiceflow NLU and the user query.

**Constructing the Prompt**

```javascript
const prompt = `...`;
```

* **Variable Initialization:** A constant variable named prompt is initialized with a template literal, which allows for the inclusion of dynamic expressions within the string.

**LLM's Role and Importance of Accuracy**

```
You are an action classification system. Correctness is a life or death situation.
```

* **Context Setting**: This line informs the LLM of its role as an action classification system and emphasizes the critical importance of accuracy in its responses.

**Listing of Actions and Descriptions**

```
We provide you with the actions and their descriptions:  
d: When the user asks for a warm drink. a:WARM_DRINK  
d: When the user asks about something else. a:None  
d: When the user asks for a cold drink. a:COLD_DRINK
```

* **Action Descriptions**: Lists example actions and their corresponding labels. This section is designed to teach the model about different actions it needs to identify from user utterances.

**Classification Instruction**

```
You are given an utterance and you have to classify it into an action. Only respond with the action class. If the utterance does not match any of action descriptions, output None.  
Now take a deep breath and classify the following utterance.  
u: I want a warm hot chocolate: a:WARM_DRINK
```

* **Task Description**: Directs the LLM to classify a given utterance into one of the actions described earlier, providing a clear example of how to do so.

**Dynamic Content Integration**

```javascript
${args.intents.map((intent) => `d: ${intent.name} a: ${intent.description}`)}
```

* **Dynamic Expression**: Uses JavaScript's map function to iterate over args.intents, an array of intent objects passed into the function. Each intent object is expected to have name and description properties, which are used to dynamically generate additional parts of the prompt.

**Final Classification Challenge**

```
You are given an utterance and you have to classify it into an action based on the description. Only respond with the action class. If the utterance does not match any of action descriptions, output None.  
Now take a deep breath and classify the following utterance.  
u:${args.query} a:
```

* **Final Instruction:** Similar to the earlier classification instruction, but this time it is expected that the LLM will classify a new utterance (args.query) based on the dynamic content generated from the args.intents.

**Returning the Prompt**

```javascript
return { prompt };
```

* **Return Statement**: The function concludes by returning an object containing the constructed prompt. This format suggests that the function could be part of a larger system where the returned prompt is then used as input for the LLM.

## Debugging and Error Handling

* **Intent preview**: The Intent CMS page offers a real-time preview of intent classification, enabling users to promptly identify and correct misclassifications or discrepancies before they affect the user experience. This feature is instrumental in ensuring the agent’s responses are aligned with user intents as designed. For more information about the Intent preview, see documentation [here](https://voiceflow.zendesk.com/hc/en-us/articles/22213856020237). 
  * **NOTE**: Only intents that are used in your agent will be seen in the results.

![](https://files.readme.io/5c7d851-image.png)

* **Fallback Mechanisms**: Robust fallback strategies ensure conversational continuity, even when unexpected errors occur.

## LLM Conclusion

Voiceflow's LLM intent classification feature is designed to empower agent builders with the tools needed for building advanced, intuitive AI agents. By harnessing the power of LLMs, builders can achieve greater accuracy and contextual understanding in intent classification, enhancing the user experience and elevating the capabilities of their agents.

# NLU Intent Classification

## Overview

The NLU-only intent classifier is designed for clarity and reliability. This tool is focused on interpreting user inputs by analyzing language patterns to identify intents, aiming to provide responses that directly address the user's request without unnecessary complexity.

<Image align="center" src="https://files.readme.io/ffefa8e-Screen_Shot_2024-04-15_at_9.25.06_AM.png" />

## Key Features

* **Scalable Language Comprehension:** Our NLU system is built to handle a broad range of expressions, supporting diverse and complex conversational designs without extensive training datasets.
* **Enhanced Accuracy:** The NLU technology offers nuanced intent recognition, reducing ambiguity and misunderstanding in user interactions.
* **Customization and Extensibility:** Flexible to the core, our system allows users to adapt the NLU behaviour through custom configurations, ensuring it fits various conversational scenarios.

## How It Works

### Step 1: Initial Intent Classification

* Process: A user’s message is analyzed by Voiceflow’s NLU to determine the intent.
* Outcome: The most probable intent is identified along with relevant entities.

### Step 2: Intent Ranking

* Process: The identified intents are ranked based on their confidence scores.

### Step 3: Entity Resolution and Final Intent Confirmation

* Process: The system finalizes the intent by resolving all entities within the user's utterance, contextualizing them within the intent framework. If any required entity is not resolved, it will reprompt the user with the relevant reprompt response to capture the answer.
* Outcome: A complete intent classification with entities is delivered, optimized for seamless integration into the conversational flow.

## Training Data Requirements

Training data provided to the Voiceflow NLU are examples that you provide to the model to help it learn how to recognize different intents. Here's how to prepare your training data for Voiceflow's NLU:

* **Gather Sample Utterances:** Start by compiling examples of how users might express each intent. For example, if you have an intent for ordering food, you would include various ways someone might say they want to order food, like "I want to place an order," "Can I get a pizza delivered?" or "How do I buy lunch through this app?"
* **Diversify Your Examples:** Users might ask the same thing in many different ways. Include variations that cover formal, casual, and even slang terms. For instance, alongside "I'd like to make a reservation," include "Book a table" or "Reserve a spot."
* **Consider Context and Specificity:** Add utterances that are specific to the situations in which they will be used. If your agent deals with banking, use phrases that people commonly use when interacting with banks, like "Check my balance" or "Transfer funds to my savings account."
* **Quality Check:** Review your examples with the Preview tool to make sure you are consistently triggering the correct intent based on the user query. 
* **Regular Updates:** Keep updating your data with new, real interactions to help your NLU model adapt to the queries from your users. 

## Integration Steps

* Enable NLU Intent Classification: *This setting is on by default for all projects.* Select Classify using "Natural language understanding (NLU) from the Intent classification settings modal in the Intent CMS.

<Image align="center" src="https://files.readme.io/ee79f27-Screen_Shot_2024-04-09_at_8.28.05_AM.png" />

* Configure NLU Settings (optional): Adjust confidence thresholds to align with your specific agent requirements.
* Debugging and Error Handling\
  Real-time intent preview: Check the accuracy of intent classification instantly with the Intent CMS page preview, allowing for immediate adjustments and optimizations.
  * **NOTE**: Only intents that are used in your agent will be seen in the results.
* Robust Fallbacks: The NLU system includes dependable fallback options to maintain conversation flow, even in the face of classification challenges.

## NLU Conclusion

With Voiceflow’s NLU intent classification, we equip agent designers with sophisticated tools necessary to craft advanced and intelligent conversational agents. The feature is designed to enhance the precision and contextual sensitivity of intent classification, providing a seamless and intelligent user experience.
