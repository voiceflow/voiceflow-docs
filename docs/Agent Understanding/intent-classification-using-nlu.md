---
title: Intent Classification using Voiceflow NLU
excerpt: >-
  Intent classification using Voiceflow's Natural Language Understanding (NLU)
  model
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

## Conclusion

With Voiceflow’s NLU intent classification, we equip agent designers with sophisticated tools necessary to craft advanced and intelligent conversational agents. The feature is designed to enhance the precision and contextual sensitivity of intent classification, providing a seamless and intelligent user experience.
