---
title: Content Manager
excerpt: Best practices when using the Voiceflow Content Management System.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Content Management System Best Practices

The Content Management System (CMS) contains all the individual pieces of content that make an agent.

Lets go over each part of the Voiceflow CMS

## Messages

The Messages CMS is a central place to see all of the hard-coded messages used in your AI Agent. Within the Messages CMS, you can see: 

- What workflows a message is used in, and how many times it is used
- Who was the last editor of the message
- When it was last updated

The Message CMS is a great collaborative tool, enabling business users (think copywriters, product owners, business analysts) to update hard-coded messages without having to go onto the canvas.

## Components

The Components CMS shows all the reusable components in an agent. Within the components CMS you can see:

- The name of the component
- A description of the component (useful for collaboration)
- What workflows the component is used in, and how many times it’s used
- Who was the last editor of the component
- When it was last updated

The components CMS is useful for getting a high level understanding of what parts of the agents are reusable, allowing you

Components in Voiceflow are reusable modules that handle specific functions or tasks. They promote consistency and efficiency by allowing you to use the same functionality across different workflows. While also allowing collaboration between team members, by being able to reuse functionality that’s already been created. 

> 💡 Pro tip
> 
> Any edits of a component will be reflected wherever the component is used.

## Variables

The Variables CMS is where you manage all the variables used in your AI Agent. Within the Variables CMS, you can see:

- The name of the variable
- A description of the variable (useful for collaboration)
- What workflows the variable is used in, and how many times it's used
- Who was the last editor of the variable
- When it was last updated

Variables in Voiceflow are containers that store data, allowing for dynamic and personalized interactions within your conversational assistant. They can be used to:

- Store user preferences
- Keep track of conversation context
- Personalize responses based on user input

The Variables CMS is particularly useful for getting an overview of all the data points your agent is tracking and how they're being used across different workflows.

## Functions

The Functions CMS displays all the custom functions created for your AI Agent. Within the Functions CMS, you can see:

- The name of the function
- A description of what the function does (important for team collaboration)
- What workflows the function is used in, and how many times it's used
- Who was the last editor of the function
- When it was last updated

Functions in Voiceflow are reusable, user-defined steps that perform specific tasks, such as transforming user input or making API calls, to enhance the capabilities of your conversational assistant. 

The Functions CMS allows you to:

- Get a high-level understanding of the custom logic in your agent
- Promote code reuse across different parts of your agent
- Facilitate collaboration by providing a central place to manage and update functions

## Natural Language CMS

The Natural Language CMS houses your Agent's Natural Language Understanding (NLU) model which allows it to classify user intention.

### Intents

The Intents CMS is where you manage all the intents defined for your AI Agent. Within the Intents CMS, you can see:

- The name of the intent
- A description of what the intent represents (crucial for AI training)
- Example utterances associated with the intent
- What workflows the intent triggers or is used in
- Who was the last editor of the intent
- When it was last updated

Intents in Voiceflow are descriptions of actions a user might intend to do, captured with example phrases and descriptions. They are used to:

- Guide conversations through natural language understanding
- Allow users to navigate between different parts of the conversation
- Improve the agent's understanding of user requests

The Intents CMS is vital for fine-tuning your agent's natural language understanding capabilities and ensuring it can accurately interpret user inputs.

### Entities

The Entities CMS shows all the entities defined in your AI Agent. Within the Entities CMS, you can see:

- The name of the entity
- A description of what the entity represents
- Examples or patterns for the entity
- What workflows or intents the entity is used in
- Who was the last editor of the entity
- When it was last updated

Entities in Voiceflow are similar to variables in that they store data, but they are used to smartly define what the variable represents. This allows for:

- Extraction of specific types of information (e.g., names, dates, locations)
- More accurate understanding of user input
- Enhanced ability to provide contextually relevant responses
- The Entities CMS is crucial for improving your agent's ability to extract and understand specific pieces of information from user inputs, leading to more accurate and contextual responses.
- By effectively utilizing these different parts of the CMS, you can create a more robust, dynamic, and intelligent AI agent. The centralized management of these elements allows for better collaboration, easier maintenance, and a more comprehensive overview of your agent's capabilities.

## Organizational Features

Several organizational features help you structure and manage your Agent efficiently within the CMS. These features are designed to improve collaboration, maintainability, and scalability of your projects.

### Folders

Folders serve as the top-level organizational units in your Voiceflow Agent. They act as containers for related workflows and components, allowing you to group functionalities logically. Folders can be used to organize:

- Workflows
- Components
- Intents
- Entities
- Variables

### Descriptions: Context and Clarity

Most elements in the CMS (intents, entities, variables) have the ability to add descriptions. Use these to:

- Provide context for team members
- Clarify the purpose and usage of each element
- Improve maintainability of your agent

> 💡 Pro tip
> 
> If using the LLM Intent Classification feature, then you must have a description of your Intent for the classification to work.