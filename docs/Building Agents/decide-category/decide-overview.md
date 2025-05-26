---
title: Overview
excerpt: >-
  Deciding is using logic, variables, and other information to flesh out
  diffferent capabilities of your AI agent, and collect external infromation.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Deciding is where your AI Agent begins to integrate business rules and logic unique to your organization. This customizability and expandability is where Voiceflow really shines!

Once your agent can understand what the user wants, you can use the following to _decide_ where the user should go.

1. **[Variables](https://developer.voiceflow.com/v2.0/docs/variables-set)**: Information about the user and what the user wants can be stored in Variables or Entities. Variables are filled by an external source like an [API call](https://developer.voiceflow.com/v2.0/docs/api-step) or a [Set](https://developer.voiceflow.com/v2.0/docs/variables-set#set) step. Entities are filled from user input. You can also take advantage and manipulate an agent's [Memory](https://developer.voiceflow.com/v2.0/docs/memory) for more relevant answers.
2. **[Logic](https://developer.voiceflow.com/v2.0/docs/logic)**: Using logic allows you to dictate where the conversation should go based on variables or entities. You can use logic to provide different types of users different capabilities within your AI agent. Through logic and all your steps, you can also run [Actions](https://developer.voiceflow.com/v2.0/docs/actions).
3. **[Triggers](https://developer.voiceflow.com/v2.0/docs/trigger)**: Triggers are used to 'jump' to a specific part of your AI agent. Triggers are activated by attaching an intent to them. You can also use an 'action' to route a user to a trigger.
4. **Custom code**: Using [JavaScript](https://developer.voiceflow.com/v2.0/docs/javascript-step) and [Custom Functions](https://developer.voiceflow.com/v2.0/docs/custom-functions) are other ways to call external APIs and run logic on your agent to parse inputs.

By optimizing the decide phase, businesses can ensure their AI agents are not only responsive but also strategically aligned with business goals, enhancing user experience and operational efficiency, and are able to integrate all the extra relevant information they have.

## Common Applications

Typically, we use Voiceflow in the following way.

1. Passing in information to Voiceflow about the customer when the conversation starts. This often contains information like the user's ID or other unique identifiers. This can be done through the _Launch Request_ that is used to start the conversation with the AI Agent.
2. The API step or a Function may be used in the flow to fetch information related to the user, such as their purchase history, plan type, shipping information, and more.
3. Logic is used based on these to route the user down specific paths or give them access to answers provided by specific models or that contain specific information.
   1. _Example: If a user is on an 'enterprise' plan, we provide them different menu options and access to different functions within our AI agent. Like submitting a premium support ticket._