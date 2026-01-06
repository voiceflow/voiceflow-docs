---
title: Session timeouts
deprecated: false
hidden: false
metadata:
  robots: index
---
Each conversation that a user has with a Voiceflow agent happens within a **chat session**. This chat session is tied to a `user_id` and contains everything related to a single conversation's state, such as its message history, [variables](doc:variables), and other data visible through the [Dialogue Manager API](ref:stateinteract-1). This means that as the user continues to interact with your agent using the same `user_id`, they will remain in the same chat session—allowing the agent to build on existing message history, variables, and context rather than starting a new conversation.

<br />

By default, chat sessions will only end when:

* **The user chooses to end the session** - for example, they hang up on a voice call, or click the close button on the web chat widget.
* **The project reaches a point where there is no continuing** - such as an [End step](doc:todo-end-step) or an [exit condition](https://docs.voiceflow.com/docs/agents#exit-conditions) that isn't linked to any further steps.
* **A technical issue forces the conversation to end** - such as the user's connection to a voice call dropping.

<br />

## Frequently asked questions

**What is the `user_id` variable?**

The `user_id` variable c When calling into an agent via Voiceflow's [phone](doc:telephony) integration, 
