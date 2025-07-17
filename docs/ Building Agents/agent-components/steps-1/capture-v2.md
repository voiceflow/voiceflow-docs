---
title: Capture step
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
## Introduction

The Capture Step lets your assistant collect user input- either as a full response or by extracting specific entities. It gives you control over how input is handled, validated, and responded to.

\[ video of capture step from canvas ]

***

## Capturing the Entire User Reply

When you want to capture exactly what the user says and store it for later use, you can configure the Capture Step to save the entire user reply to a variable.

### Configuring to capture Entire User Reply

1. **Select Capture Mode**: In the Capture Step editor, you'll see a toggle to choose between **Entities** and **Entire User Reply**. Select **Entire User Reply**.

   <Image align="center" src="https://files.readme.io/a38edb0cb24592a10afbaf3ad3e1c9e06205b8ab7b6cb201f33b6181c1e7ef71-CleanShot_2024-10-02_at_14.50.41.png" />
2. **Set the Variable**: Specify the variable where you want to store the user's reply. This variable can be used later in your conversation flow to personalize responses or process the input.

### Options and Toggles

The Capture Step offers additional options to control the user's experience:

#### 1. No Reply

> **Purpose**: Handles situations where the user doesn't respond within a certain timeframe.
>
> **Behaviour**:
>
> * **Set Timeout Duration**: Define the time (in seconds) the system should wait for a response before considering it a no-reply.
> * **Customize Reprompt Message**: Provide a message that will be sent to the user if they don't reply in time (e.g., "Are you still there?").

<br />

#### 2. Listen for Other Triggers

> **Purpose**: Allows the agent to recognize and respond to intents that are outside the scope of the current Capture Step.
>
> **Behavior**:
>
> * **ON**: The agent listens for other intents while waiting for the user's reply. If the user says something that matches another intent, the agent will trigger that intent.
> * **OFF**: The agent focuses solely on capturing the user's input in this step. It won't trigger other intents until after the capture is complete.

***

<br />

<Image align="center" src="https://files.readme.io/a978c1d1d21038e83d87716de2fc3cd492500bae021b882725c24abc663b6239-CleanShot_2024-10-02_at_14.48.32.png" />

* **Validate User Input**: Specify conditions that the user's input must meet for the entities to be considered successfully captured.
* **Guide the AI**: Provide instructions to the LLM to ensure accurate extraction of entities.

#### How to Add Rules

1. **Navigate to Rules Section**: In the Capture Step editor, find the **Rules** section.
2. **Click the "+" Button**: Add a new rule.
3. **Define Your Rule**:
   * Write a natural language statement that describes the validation criteria for the entity collection.
   * **Example**: "The email address must be valid and cannot be from a free email provider like Gmail or Yahoo."

#### Multiple Rules

* You can add multiple rules to cover all necessary validation for your entities.
* The LLM will consider all rules when extracting and validating entities from the user's input.

### 2. Exit Scenarios

#### Purpose

<Image align="center" src="https://files.readme.io/bf143a9dcae19402a084232eebf49fc601f7181bb79a9cce61fcf3346cb92bc9-CleanShot_2024-10-02_at_14.51.16.png" />

* **Manage Conversation Flow**: Define conditions under which the agent should stop trying to capture the entities and proceed differently.
* **Enhance User Experience**: Prevent frustration by not repeatedly asking for information the user cannot or does not want to provide.

#### How to Add Exit Scenarios

1. **Navigate to Exit Scenarios Section**: In the Capture Step editor, find the **Exit Scenarios** section.
2. **Click the "+" Button**: Add a new exit scenario.
3. **Define Your Exit Scenario**:
   * Specify phrases or conditions that indicate the user cannot provide the entities.
   * **Example**: "If the user says 'I don't have an email address' or 'I'd prefer not to share that.'"

#### Multiple Exit Scenarios

* You can add multiple exit scenarios to handle different user responses.

### Exit Scenario Path Toggle

#### Purpose

* **Customize Conversation Paths**: Decide whether to direct the user down a separate path if an exit scenario is triggered.

#### How to Use

* Exit Scenario Path Toggle:
  * **ON**:
    * An additional exit port appears on the Capture Step.
    * When an exit scenario is triggered, the conversation flows through this separate path.
    * **Use Case**: Direct the user to an alternative flow, such as offering different options or providing additional assistance.
  * **OFF**:
    * No additional exit port is created.
    * When an exit scenario is triggered, the conversation continues through the main capture port.
    * **Use Case**: Proceed with the conversation as if the entities were captured, possibly with default values or by skipping certain steps.

***

## Summary of the Capture Step Configuration

1. **Select Capture Mode**:
   * **Entire User Reply**: Capture and store the full user input.
   * **Entities**: Extract specific entities from the user's input.

2. **Configure Options**:
   * **No Reply**: Handle situations where the user doesn't respond.
   * **Listen for Other Triggers**: Allow or prevent the agent from recognizing other intents during this step.

3. **For Entity Capture**:
   * **Add Entities**: Choose or create the entities you want to capture.
   * **Automatically Reprompt**: Enable the system to generate dynamic reprompts for incomplete or invalid inputs.
   * **Define Rules**: Set validation criteria for the collection of entities.
   * **Set Exit Scenarios**: Determine conditions under which to stop capturing entities and how to proceed.
   * **Exit Scenario Path**: Decide whether to use a separate path when an exit scenario is triggered.

***

## Practical Example: Capturing User Contact Information

Let's walk through an example to illustrate how to use the Capture Step effectively.

### Scenario

You want to collect the user's **first name**, **last name**, and **email address**.

### Steps

1. **Add a Capture Step to Your Canvas**.

2. **Configure to Capture Entities**:
   * **Select Entities**:
     * `FirstName` (Custom)
     * `LastName` (Custom)
     * `EmailAddress` (Custom)

3. **Set Options**:
   * **No Reply**: Enable with a timeout of 30 seconds and a reprompt like "Please let me know if you're still there."
   * **Listen for Other Triggers**: Disable to focus on capturing the required information.

4. **Enable Automatically Reprompt**:
   * **Model Settings**:
     * **Temperature**: 0.7 for a balance between creativity and predictability.
     * **Max Tokens**: 50 to limit the length of reprompts.
     * **System Prompt**: "Politely ask the user for any missing information."

5. **Define Rules**:
   * **Rule**: "Ensure both first name and last name are provided, and the email address must be valid and not from a disposable domain."

6. **Set Exit Scenarios**:
   * **Exit Scenario**: "If the user says 'I don't want to provide my email,' 'I prefer not to share personal information.'"
   * **Exit Scenario Path Toggle**: Enable to create a separate path.
     * **Connect the Exit Port**: Direct to a step that says, "No problem, we can proceed without your email."

### Conversation Flow Example

1. **Agent**: "Could you please provide your first name, last name, and email address?"
2. **User**: "I'm John."
3. **Agent**: "Thanks, John. May I have your last name as well?"
4. **User**: "Doe."
5. **Agent**: "Great, and could you provide your email address?"
6. **User**: "I'd rather not share that."
7. **Agent**: "No problem, we can proceed without your email."
8. **\[Conversation continues along the exit scenario path.]**

***

## Best Practices

* **Be Clear with Prompts**: Ensure that your initial prompt clearly states what information you're requesting.
* **Write Effective Rules**: Use natural language to define rules that cover all entities in the collection.
* **Consider User Privacy**: Always provide options for users to opt out of providing certain information.
* **Test Your Configuration**: Use Voiceflow's testing tools to simulate conversations and ensure that your Capture Step behaves as expected.
* **Monitor and Iterate**: Collect user data (in compliance with privacy laws) to understand how users interact with your agent and adjust your design accordingly.