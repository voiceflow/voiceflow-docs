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

### Options and toggles

The Capture Step offers additional options to control the user's experience:

#### 1. `No Reply`

> **Purpose**: Handles situations where the user doesn't respond within a certain timeframe.
>
> **Behaviour**:
>
> * **Set Timeout Duration**: Define the time (in seconds) the system should wait for a response before considering it a no-reply.
> * **Customize Reprompt Message**: Provide a message that will be sent to the user if they don't reply in time (e.g., "Are you still there?").

<br />

#### 2. `Listen for Other Triggers`

> **Purpose**: Allows the agent to recognize and respond to intents that are outside the scope of the current Capture Step.
>
> **Behavior**:
>
> * **ON**: The agent listens for other intents while waiting for the user's reply. If the user says something that matches another intent, the agent will trigger that intent.
> * **OFF**: The agent focuses solely on capturing the user's input in this step. It won't trigger other intents until after the capture is complete.

***

## Entity extraction rules

Entity rules let you define what valid input should look like—such as a 5-digit number for a ZIP code—so your assistant can validate responses and help the LLM extract the right information. These rules are written in natural language, making them easy to create and understand.

<Image align="center" src="https://files.readme.io/a978c1d1d21038e83d87716de2fc3cd492500bae021b882725c24abc663b6239-CleanShot_2024-10-02_at_14.48.32.png" />

Here's some sample entities with rules:

> **Zip Code**: "Must be exactly 5 digits long."
>
> **Email Address**: "Must be a valid business email, not a personal email like Gmail or Yahoo."
>
> **Phone Number**: "Should be a 10-digit number, possibly formatted with dashes or spaces."

Clearly define what you need without making it hard for the user to comply. Write rules the same way, you would explain to a person.

***

## Automatic reprompts

Automatic reprompts are dynamic follow-up messages that the system generates when a user's input doesn't meet the entity's requirements. This feature ensures that the conversation remains fluid whilst still extracting information to fulfill an entity.

### How automatic reprompts work

1. **Detection**: If the user's input is invalid or incomplete based on your entity rules, the system recognizes this.
2. **Generation**: The LLM crafts a personalized message prompting the user to provide the correct information.
3. **Response**: The user provides the needed input, and the conversation continues smoothly, as originally planned in your workflow.

Here's an example of an automatic reprompt:

> **Scenario**: You're capturing an `email address`, and the user says, "It's john dot email at com."
>
> **Reprompt**: "It seems there's a typo in the email address. Could you please provide a valid email in the format '[example@domain.com](mailto:example@domain.com)'?"

***

## Exit scenarios

Sometimes, a user may be unable or unwilling to provide the information you're requesting. Exit scenarios allow your agent to handle such situations gracefully.

### What are exit scenarios?

Exit scenarios are predefined conditions under which the system stops attempting to collect a particular entity and moves on in the conversation.

### How to set up exit scenarios

* **Define trigger phrases**: Specify phrases or responses that indicate the user wants to skip or cannot provide the information (e.g., "I don't know," "I'd rather not say").
* **Configure the exit path**: Decide where the conversation should go next. This could be:

  * **Main path**: Proceed as if the entity was captured, perhaps with a default value.
  * **Alternate path**: Redirect to a different part of the conversation that doesn't require the entity.

  <Image align="center" className="border" border={true} src="https://files.readme.io/bf143a9dcae19402a084232eebf49fc601f7181bb79a9cce61fcf3346cb92bc9-CleanShot_2024-10-02_at_14.51.16.png" />

  Here's a possible scenario where an exit scenario is executed:

> **Entity**: `PhoneNumber`
>
> **Trigger Phrase**: "I don't have a phone."
>
> **Exit Action**: The agent replies, "No problem, we'll proceed without a phone number," and continues the conversation.