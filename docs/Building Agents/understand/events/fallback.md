---
title: Fallback
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
Handling unexpected user inputs is essential for creating a smooth conversational experience. This guide will help you understand how the **Fallback** event works and how to implement it effectively in your agents.

### Understanding the Hierarchy of Intent Matching

Voiceflow follows a specific order of operations to match a user’s utterance to an intent. Knowing this hierarchy helps you design more effective conversations.

### Order of Operations: How Voiceflow Matches User Input

1. **Local Triggers on the Current Step**

* **Intents on the Current Step**: Voiceflow first checks if the user’s input matches any intents directly attached to the current step.

2. **Triggers in the Current Workflow**

* **Intents in the Current Flow**: If there’s no match on the current step, Voiceflow looks for matching intents within the current workflow or flow.

3. **Global Triggers**

* **Global Intents**: Next, Voiceflow checks for any global intents that match the user’s input. These intents are available across all workflows in your agent.

4. **Local No Match Handling**

* **No Match Handler on the Current Step**: If no intents match, Voiceflow checks if there’s a local no match response defined on the current step. This allows you to handle misunderstandings specific to that point in the conversation.

5. **Fallback Event**

* **Triggering the Fallback Workflow**: If none of the above conditions are met, and the local no match has been exhausted or isn’t defined, Voiceflow triggers the built-in **Fallback event**. This event initiates its own workflow, allowing you to handle unrecognized inputs globally.

**The Fallback Event Explained**

The **Fallback Event** is designed to give you greater control over how your agent handles unrecognized user inputs.

**How the Fallback Event Works**

* **Automatic Triggering**: The fallback event is automatically triggered when the user’s input doesn’t match any local triggers, workflow triggers, global triggers, or local no match handlers.
* **Initiating a Fallback Workflow**: When triggered, the fallback event starts a separate workflow that you can design to guide the user back into the conversation.

**Benefits of the Fallback Event**

* **Customizable Responses**: Create tailored responses that align with your agent’s personality and the context of the conversation.
* **Improved User Experience**: Helps maintain a smooth dialogue by gracefully handling misunderstandings.
* **Flexible Conversation Design**: Allows you to decide how the agent should respond, whether by providing help, re-prompting, or offering alternative options.

### Implementing the Fallback Event in Your Agent

**1. Design Your Fallback Workflow**

* **Create a Fallback Flow**: In your Voiceflow project, design a flow specifically for handling fallback situations.
* **Craft Appropriate Responses**: Include messages that acknowledge the misunderstanding and provide guidance.
* Example: “I’m sorry, I didn’t quite catch that. Could you please rephrase?”
* **Offer Options**: Provide the user with clear options to continue.
* Example: “You can say ‘Help’ for assistance or ‘Main Menu’ to go back.”

**2. Set Up the Fallback Event Trigger**

* **Associate the Fallback Event with Your Workflow**:
* Add a **Trigger step** to your fallback workflow.
* Set the trigger type to **Event**.
* Select the **Fallback Event** from the list.

![](https://files.readme.io/b4f8f0aedebe40d82dbf7fe982208607744c8baac0a350f9acb382b14ae0816d-CleanShot_2024-11-06_at_09.55.002x.png)

**3. Test Your Agent**

* **Simulate Unrecognized Inputs**: During testing, input phrases that aren’t covered by any intents.
* **Observe the Fallback Behavior**: Ensure that the agent follows your fallback workflow.
* **Refine as Needed**: Adjust your fallback responses based on testing to improve clarity and effectiveness.

### Example: How Voiceflow Processes User Input

Let’s walk through an example to illustrate the hierarchy:

1. **User Says**: “I want to fly to the moon.”

2. **Local Triggers on the Current Step**

* **Check**: Are there any intents attached to the current step that match?
* **Result**: No match found.

3. **Triggers in the Current Workflow**

* **Check**: Are there any intents in the current flow that match?
* **Result**: No match found.

4. **Global Triggers**

* **Check**: Does the input match any global intents?
* **Result**: No match found.

5. **Local No Match Handling**

* **Check**: Is there a local no match handler on the current step?
* **Result**: Yes, a response is defined.
* **Action**: Agent provides the local no match response.
* **Note**: If the user continues to provide unrecognized inputs and the local no match has been exhausted, the agent proceeds to the fallback event.

6. **Fallback Event**

* **Trigger**: The fallback event is activated.
* **Action**: Agent follows the fallback workflow you’ve designed.

**Tips for Designing Effective Fallback Responses**

* **Provide Clear Guidance**: Let the user know how they can proceed.
* Example: “You can ask me about our products or say ‘Help’ for more options.”
* **Consider Escalation**: If appropriate, offer to connect the user with a human agent after multiple fallback events.
