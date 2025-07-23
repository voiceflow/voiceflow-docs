---
title: Transcripts
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
## What are transcripts?

Transcripts are automatically generated logs of conversations between users and your agent. They capture both user input and agent responses across voice and chat interactions.

Transcripts are valuable for:

* Debugging issues in conversation flows.
* Identifying points of confusion or user drop-off from conversations.
* Improving assistant performance using real interaction data.
* Maintaining a history of conversations for review or auditing

\[ insert video of navigating to transcripts ]

> ⚠️ Ensure transcripts are toggled on!

## Analyzing transcripts

Transcripts are tied to **individual** agents, not the overall workspace. Each transcript provides information including:

| Data attribute | Description                                                                                                                                                                                                          |
| :------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Date           | Timestamp of when the conversation started.                                                                                                                                                                          |
| Platform       | Source of the interaction (Chat widget or Telephony).                                                                                                                                                                |
| User ID        | Unique identifier for the user interacting with the agent.                                                                                                                                                           |
| Credits        | The number of credits consumed by the agent during the conversation.                                                                                                                                                 |
| From           | The user's phone number that was used during the conversation.                                                                                                                                                       |
| Evaluations    | Displays evaluation results such as test pass/fail status or validation values. By default, no evaluations are applied to transcripts, unless created and enabled through the [Evaluations](doc:evaluations) editor. |
| Duration       | Total length of the conversation (in minutes and seconds).                                                                                                                                                           |

\[ insert picture of transcript ]

## Debugging using transcripts

Agent and user conversations can be analyzed in depth for debugging through the Logs tab on each transcript. Logs display the behind-the-scenes of the Agent's interactions and what exact steps were executed within its designated workflow. They also provide additional information such as the agent's Input, Output and how many credits were consumed per action.

\[ insert logs tab picture ]

## [Evaluations]()

Evaluations are a set of custom criteria you can define to determine whether specific events occurred during a conversation—based on the transcript data.

> For example, you might want to evaluate whether:
>
> * The user expressed satisfaction or frustration
> * The agent confirmed an action(e.g. upload to database)
> * The conversation included a proper sign-off, such as the agent saying “Let me know if you need anything else”

Evaluations allow you to automate conversation review and score interactions against key success metrics, quality standards, or compliance requirements.