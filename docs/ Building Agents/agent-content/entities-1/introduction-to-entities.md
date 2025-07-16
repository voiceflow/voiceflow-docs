---
title: Introduction to Entities
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
Entities extract specific pieces of information from user input- like a date, location, or product name. They are declared and used to capture specific data during a conversation, while variables are used to store and manage it.

> **Example**\
> If a user says, "I want to book a flight to Paris next Friday," your assistant might extract:
>
> `location` → `Paris`
>
> `date `→ `next Friday`
>
> These extracted values (entities) can then be stored in variables for later use- for example, to confirm the travel booking.

***

## How Entities Work in Voiceflow

When a user interacts with your agent, the system listens for specific pieces of information—your defined entities—and uses Large Language Models (LLMs) to extract them from the user's input. Here's how the process works:

1. **Recognition**: The LLM analyzes the user's input to identify the presence of any entities you've specified.
2. **Extraction and Validation**: The system extracts the relevant data and applies any rules you've set to validate the input.
3. **Storage**: Validated entities are stored for use later in the conversation, such as personalizing responses or fulfilling requests.

This LLM-driven approach enhances accuracy and adaptability, allowing your agent to understand user inputs more effectively than traditional methods.

***

> 📘
>
> Rules, exit scenarios and automatic reprompt features are included as part of [new AI-powered entity collection](https://docs.voiceflow.com/changelog/ai-entity-collection) feature being rolled out to users.

## Entity Extraction Rules: Fine-Tuning Data Capture

**Entity Rules** allow you to specify exact criteria that the user's input must meet for the entity to be considered valid. These rules are written in natural language, making them easy to create and understand.

### Why Use Entity Rules?

* **Precision**: Define specific formats or content requirements.
* **Validation**: Ensure data integrity by accepting only valid inputs.
* **Guidance**: Help the LLM accurately interpret user responses.

### How to Set Entity Rules

**Navigate to Your Entity**: In the Entity CMS, select the entity you want to configure.

* **Add a Rule**: Write a natural language statement that describes the validation criteria.

### Examples of Good Entity Capture Rules

* **Zip Code**: "Must be exactly 5 digits long."
* **Email Address**: "Must be a valid business email, not a personal email like Gmail or Yahoo."
* **Phone Number**: "Should be a 10-digit number, possibly formatted with dashes or spaces."
* **Order Number**: "Must start with 'ORD' followed by 7 digits."

### Best Practices for Entity Rules

1. **Be Specific but User-Friendly**: Clearly define what you need without making it hard for the user to comply.
2. **Use Natural Language**: Write rules as you would explain them to a person.
3. **Avoid Overcomplication**: Don't add unnecessary complexity that could confuse the LLM or the user.

***

## Automatic Reprompts: Enhancing User Experience

**Automatic Reprompts** are dynamic follow-up messages that the system generates when a user's input doesn't meet the entity's requirements. This feature ensures that the conversation remains fluid and user-friendly.

### How Automatic Reprompts Work

* **Detection**: If the user's input is invalid or incomplete based on your entity rules, the system recognizes this.
* **Generation**: The LLM crafts a personalized message prompting the user to provide the correct information.
* **Response**: The user provides the needed input, and the conversation continues smoothly.

### Example of an Automatic Reprompt

* **Scenario**: You're capturing an email address, and the user says, "It's john at email dot com."
* **Reprompt**: "It seems there's a typo in the email address. Could you please provide a valid email in the format '[example@domain.com](mailto:example@domain.com)'?"

### Benefits of Automatic Reprompts

* **Personalization**: Messages are tailored to the specific issue, making them more helpful.
* **Efficiency**: Reduces the need for manual error handling in your design.
* **User Satisfaction**: Keeps users engaged by promptly addressing and resolving input issues.

***

## Exit Scenarios: Managing Conversation Flow

Sometimes, a user may be unable or unwilling to provide the information you're requesting. **Exit Scenarios** allow your agent to handle such situations gracefully.

### What Are Exit Scenarios?

Exit scenarios are predefined conditions under which the system stops attempting to collect a particular entity and moves on in the conversation.

### How to Set Up Exit Scenarios

* **Define Trigger Phrases**: Specify phrases or responses that indicate the user wants to skip or cannot provide the information (e.g., "I don't know," "I'd rather not say").
* **Configure the Exit Path**: Decide where the conversation should go next. This could be:
  * **Main Path**: Proceed as if the entity was captured, perhaps with a default value.
  * **Alternate Path**: Redirect to a different part of the conversation that doesn't require the entity.

### Example of an Exit Scenario

* **Entity**: `PhoneNumber`
* **Trigger Phrase**: "I don't have a phone."
* **Exit Action**: The agent replies, "No problem, we'll proceed without a phone number," and continues the conversation.

### Benefits of Using Exit Scenarios

* **Conversation Flow**: Prevents the conversation from stalling due to repeated, unwanted prompts.
* **Flexibility**: Allows your agent to handle various user behaviors smoothly.

***

## Putting It All Together: A Practical Example

Let's create a scenario to illustrate how entities, types, rules, automatic reprompts, and exit scenarios work together.

### Scenario: Capturing a Delivery Address

**Step 1: Create Entities**

* **`StreetAddress`** (Custom)
* **`City`** (Custom)
* **`ZipCode`** (Number)

**Step 2: Apply Entity Rules**

* **Rule** : "Should include the street number and name."
* **Rule**: "Must be exactly 5 digits."

**Step 3: Configure Automatic Reprompts**

* If the **`StreetAddress`** is missing or incomplete:
  * **Reprompt**: "Could you please provide your full street address, including the number and street name?"
* If the **`ZipCode`** is invalid:
  * **Reprompt**: "The zip code should be 5 digits. Could you double-check and provide it again?"

**Step 4: Set Up Exit Scenarios**

* If the user says, "I don't feel comfortable sharing my address":
  * **Exit Scenario**: Reply with "I understand. Would you like to proceed without scheduling a delivery?" and redirect the conversation accordingly.

### Conversation Flow Example

1. **Agent**: "Please provide your delivery address."
2. **User**: "It's 123 Main."
3. **Agent**: "Thanks! Could you also include the street name in your address?"
4. **User**: "Oh, sorry. It's 123 Main Street."
5. **Agent**: "Got it. And your city?"
6. **User**: "Springfield."
7. **Agent**: "Perfect. Lastly, could you provide your 5-digit zip code?"
8. **User**: "6270."
9. **Agent**: "It looks like the zip code should be 5 digits. Could you double-check and provide it again?"
10. **User**: "Oops, it's 62704."
11. **Agent**: "Thank you! Your delivery address is all set."

***

## Recommendations and Best Practices

### 1. Prioritize Entity Rules Over Entity Types

While assigning an entity type can be helpful, relying on **Entity Rules** gives you more control and precision. Use rules to specify exact formats or criteria, especially for custom entities.

### 2. Use Custom Entities for Flexibility

Custom entities allow you to define exactly what data you want to capture without being constrained by predefined types. This is particularly useful when dealing with unique identifiers or specific formats.

### 3. Write Clear and Concise Rules

Ensure your entity rules are easy to understand for both the LLM and the user. Avoid ambiguity and keep the language straightforward.

### 4. Handle Exit Scenarios Gracefully

Plan for situations where the user can't or won't provide certain information. Use exit scenarios to maintain a positive user experience by adjusting the conversation flow appropriately.