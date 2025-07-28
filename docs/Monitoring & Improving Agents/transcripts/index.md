---
title: Transcripts
excerpt: Record and analyze conversations between agents and users.
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

> ⚠️ Ensure audio recordings are toggled on!
>
> Call recordings need to be enabled in **transcript settings** to retrieve audio files for a conversation's transcript. Click on the ⚙️ icon to view settings.
>
> <Image align="center" className="border" border={true} src="https://files.readme.io/961b89bcfedfc25e753ba2f3fd94184b788cf78057a211fbb883b60799f33708-CleanShot_2025-07-24_at_12.33.322x.png" />

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

<Image align="center" className="border" border={true} src="https://files.readme.io/da14e70da51d4055f0ce2f9322d5d374be7b4a215f81b128558284187cd51d6d-image.png" />

<br />

## Debugging using transcripts

Agent and user conversations can be analyzed in depth for debugging through the Logs tab on each transcript. Logs display the behind-the-scenes of the Agent's interactions and what exact steps were executed within its designated workflow. They also provide additional information such as the agent's Input, Output and how many credits were consumed per action.

![](https://files.readme.io/86f63fa46cfd6f1512ce1705d034f32ee1029d9f400049e42d11cddb4d2ca985-image.png)

<br />

## [Evaluations]()

Evaluations are a set of custom criteria you can define to determine whether specific events occurred during a conversation—based on the transcript data.

> For example, you might want to evaluate whether:
>
> * The user expressed satisfaction or frustration
> * The agent confirmed an action(e.g. upload to database)
> * The conversation included a proper sign-off, such as the agent saying “Let me know if you need anything else”

Evaluations allow you to automate conversation review and score interactions against key success metrics, quality standards, or compliance requirements.