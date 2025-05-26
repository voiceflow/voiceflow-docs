---
title: Intent Classification using LLMs (Hybrid)
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
## Overview

The LLM-based intent classifier introduces a novel hybrid methodology, blending traditional Natural Language Understanding (NLU) with the expansive capabilities of Large Language Models (LLMs) to classify user intents. This synthesis allows for the precision and targeted understanding of NLU with the contextual breadth and depth provided by LLMs, delivering a robust and nuanced approach to intent recognition.

![](https://files.readme.io/5c2cbc6-image.png)

## How It Works

> 📘 Example template
> 
> Download our Banking Agent template [here](https://drive.google.com/uc?export=download&id=1hNdxZ4KSiBWVO0R8l7vCNVFmsQsiLKG_) to start testing immediately.

### Step 1: Initial Intent Classification

- **Process**: The user's utterance is sent to the Natural Language Understanding (NLU) system, requesting classification.
- **Outcome**: The NLU returns the most probable intent and its entities, alongside a list of max. 9 alternative intents with confidence scores. This result acts as the "NLU fallback" in case subsequent steps encounter issues.

### Step 2: Metadata Fetching and Prompt Generation

- **Process**: Upon receiving the intents, the system fetches associated intent descriptions for each intent. A custom or default prompt is then generated using the prompt wrapper.
- **Fallback**: In case of errors during intent fetching or prompt generation  the system resorts to the "NLU fallback."

### Step 3: Interaction with LLM

- **Process**: The generated prompt is passed with specific metadata settings, including temperature, to the selected AI model.
- **Validation**: The LLM response is parsed to confirm if it represents a valid intent name. Failure to identify a valid intent triggers the "NLU fallback."

### Step 4: Entity Filling and Final Intent Classification

- **Process**: For intents associated with entities, the original utterance is re-evaluated by the NLU, focusing solely on the identified intent to populate the necessary entities.
- **Outcome**: The NLU returns the refined intent classification complete with entities, ready for use within the conversational flow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/593acd3-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "70% ",
      "border": true
    }
  ]
}
[/block]


## Training Data Requirements

- **Utterance**: Supply at least one example utterance per intent to give the NLU training data necessary to fetch up to 10 relevant intents.
- **Clear Intent Descriptions**: Accompany utterances with a direct intent description, setting explicit conditions for when the intent should be triggered. _Examples_ include:
  - _Customer Support Inquiry_: "Trigger this intent when the user is seeking assistance with their account, such as password reset or account recovery."  
    _Product Inquiry_: "Trigger this intent when the user inquires about product features, availability, or specifications."  
    _Booking Request_: "Trigger this intent when the user wants to make a reservation for services like dining, accommodation, or transportation."
- **Efficient Learning**: With just an utterance and a description, LLMs leverage their pre-trained knowledge to effectively classify intents, requiring far less data than traditional methods.

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

- **Enable LLM Intent Classification**: This feature can be activated within your project's settings, within the Intent page settings menu.
- **Configure Prompt Wrapper (_optional_):** Specify the logic for prompt generation, ensuring alignment with your conversational model's requirements. A default prompt wrapper is provided for immediate use.
- **Customize Settings**: Tailor the performance using model selection and temperature settings to fine-tune performance and response characteristics.

## Understanding the Prompt Wrapper

The prompt wrapper serves as a crucial intermediary layer, which dynamically crafts the prompts that are sent to the LLM for intent classification. It is essentially a piece of code that translates the agent’s needs into instructions that the language model understands and can act upon.

- **Customization of Prompt Logic:** Developers can tailor the prompt wrapper to fit the specific needs of their conversational model. This includes defining how user utterances are interpreted and setting the conditions for intent classification.
- **Default Prompt Wrapper**: A default template is provided to ensure quick deployment and **should satisfy most agent requirements**. It structures the information by introducing the AI’s role, the actions and their descriptions, and then it poses the classification challenge based on a user utterance.

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

- **Purpose**: Declares and exports a default function named main, making it accessible to other parts of the application.
- **Parameters**: `args` - This object contains arguments passed into the function, which in this context, includes the intents (name and description) returned by the Voiceflow NLU and the user query.

**Constructing the Prompt**

```javascript
const prompt = `...`;
```

- **Variable Initialization:** A constant variable named prompt is initialized with a template literal, which allows for the inclusion of dynamic expressions within the string.

**LLM's Role and Importance of Accuracy**

```
You are an action classification system. Correctness is a life or death situation.
```

- **Context Setting**: This line informs the LLM of its role as an action classification system and emphasizes the critical importance of accuracy in its responses.

**Listing of Actions and Descriptions**

```
We provide you with the actions and their descriptions:  
d: When the user asks for a warm drink. a:WARM_DRINK  
d: When the user asks about something else. a:None  
d: When the user asks for a cold drink. a:COLD_DRINK
```

- **Action Descriptions**: Lists example actions and their corresponding labels. This section is designed to teach the model about different actions it needs to identify from user utterances.

**Classification Instruction**

```
You are given an utterance and you have to classify it into an action. Only respond with the action class. If the utterance does not match any of action descriptions, output None.  
Now take a deep breath and classify the following utterance.  
u: I want a warm hot chocolate: a:WARM_DRINK
```

- **Task Description**: Directs the LLM to classify a given utterance into one of the actions described earlier, providing a clear example of how to do so.

**Dynamic Content Integration**

```javascript
${args.intents.map((intent) => `d: ${intent.name} a: ${intent.description}`)}
```

- **Dynamic Expression**: Uses JavaScript's map function to iterate over args.intents, an array of intent objects passed into the function. Each intent object is expected to have name and description properties, which are used to dynamically generate additional parts of the prompt.

**Final Classification Challenge**

```
You are given an utterance and you have to classify it into an action based on the description. Only respond with the action class. If the utterance does not match any of action descriptions, output None.  
Now take a deep breath and classify the following utterance.  
u:${args.query} a:
```

- **Final Instruction:** Similar to the earlier classification instruction, but this time it is expected that the LLM will classify a new utterance (args.query) based on the dynamic content generated from the args.intents.

**Returning the Prompt**

```javascript
return { prompt };
```

- **Return Statement**: The function concludes by returning an object containing the constructed prompt. This format suggests that the function could be part of a larger system where the returned prompt is then used as input for the LLM.

## Debugging and Error Handling

- **Intent preview**: The Intent CMS page offers a real-time preview of intent classification, enabling users to promptly identify and correct misclassifications or discrepancies before they affect the user experience. This feature is instrumental in ensuring the agent’s responses are aligned with user intents as designed. For more information about the Intent preview, see documentation [here](https://voiceflow.zendesk.com/hc/en-us/articles/22213856020237). 
  - **NOTE**: Only intents that are used in your agent will be seen in the results.

![](https://files.readme.io/5c7d851-image.png)

- **Fallback Mechanisms**: Robust fallback strategies ensure conversational continuity, even when unexpected errors occur.