---
title: Memory
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
## Overview

Leveraging LLMs to perform specific functions within your Assistant can be more powerful if they understand the full context of the conversation leading up to that point in the conversation. To simplify adding that context into a Prompt, you have the option to leverage Memory on each Set AI and Response AI Step. 

If you're using the Memory option on any of your AI Steps, we will automatically include the previous 10 Turns (user inputs and system responses) in the conversation into the prompt to provide context on:

* What the user has been asking
* Specific entities or topics they have mentioned
* The responses your Assistant has provided (static or LLM-generated)
* The tone of the conversation and persona of your Assistant

This enables your Assistant to dynamically reference content from previous interactions in the conversation. For example:

```
Assistant: Welcome to Voiceflow Pizza, can I take your order?

User: I'd like a large, 3 topping pizza.

Assistant: Sure thing, which toppings would you like?

User: Pepperoni, olives and mushrooms. And make it a small.

Assistant: Got it, so thats a small pizza, with pepperoni, olives and mushrooms. Anything else?
```

This allows for much more dynamic, human interactions, when memory can be preserved across the conversation.

## Accessing Memory through a Variable

In Voiceflow, the last 10 turns of a conversation can be accessed through the variable *\{vf\_memory}*. This can be used in AI step when using the Knowledge base to provide context to the AI agent of the previous conversation.

This variable is constantly being updated. An example of how you would use it with a prompt is below.

```
You are an AI support agent. Answer the users question using the context below.

###

Context: {vf_memory}
```

## Using Memory with the Knowledge Base

The knowledge base **does not use memory by default**. You can include the memory variable in the instructions section of the Knowledge Base Step (Response AI).

> 📘 This only impacts how the AI formats the response
>
> When the knowledge base answers a question, it has 2 stages that it goes through
>
> 1. **Finding relevant information**: It uses the \{question} field to find information
> 2. **Summarizing an answer**: It uses the \{instructions} field and prompt settings to summarize an answer.
>
> Adding memory to the instructions will only impact #2. If a user asks a generic question like 'tell me more' - it will fail at Step 1 and not provide a response.
>
> If you are anticipating follow up questions from users, we suggest reformatting their question with the Set AI step (shown below). If you find customers are asking generic questions and receiving poor responses, we recommend using AI to optimize their question before sending it to the Knowledge Base .
>
> ![](https://files.readme.io/fd5d309-CleanShot_2024-06-20_at_19.37.032x.png)

<br />

## Enabling Memory on a Response AI or Set AI Step

Once you have placed your step, you can configure it in the Editor. In the editor, you will have three different options to prompt your Assistant:

* **Use Prompt only** - When the Step is hit during a user's session, the Prompt you provide will be the only data passed to the LLM to generate a response. *This option is useful when you want an LLM to perform a very specific function, or generate a very specific response, and including Memory could mess that up.*
* **Use Memory and Prompt** - When hit during a user session, the Prompt you provide will be augmented with the previous 10 turns in the conversation, and the LLM will generate a response from both pieces of data. *This option is best if you want to enable the most dynamic possible output from the LLM, because this will provide the most context possible for it to inform it's response.*
* **Use Memory only (only available on Response AI)** - This will pass only the previous 10 turns of the conversation to the LLM and allow it to response without any guidance from you. *This will enable a purely-conversational interaction between the user and your Assistant, without you providing it a specific goal or task.*

![](https://files.readme.io/d4b38ad-image.png)

## Testing your Generated Responses

You can test your prompt using the Preview button in the Editor, but this will not include any Memory. To test the function of your Set AI or Response AI Steps using a Memory option, you will need to run a conversation in the Test[ Tool](https://developer.voiceflow.com/v2.0/docs/test-tool).
