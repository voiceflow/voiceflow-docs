---
title: Session timeouts
excerpt: Manage when a conversation ends and evaluations are generated.
deprecated: false
hidden: false
metadata:
  robots: index
---
Each conversation that a user has with a Voiceflow agent happens within a **chat session**. This chat session is tied to a `user_id` and contains everything related to a single conversation's state, such as its message history and other data visible through the [Dialogue Manager API](ref:stateinteract-1). This means that as the user continues to interact with your agent using the same `user_id`, they will remain in the same chat session, meaning they'll continue where they left off in the conversation.

<br />

## Ending a chat session

By default, chat sessions will only end when:

* **The user chooses to end the session** - for example, they hang up on a voice call.
* **The project reaches a point where there is no continuing** - such as an [End step](doc:todo-end-step) or an [exit condition](https://docs.voiceflow.com/docs/agents#exit-conditions) that isn't linked to any further steps.
* **A technical issue forces the conversation to end** - such as the user's connection to a voice call dropping.
* **When using the web chat widget, the [chat persistence settings](doc:chat-persistence) result in the conversation expiring** - for example, the `sessionStorage` option is enabled and the user closes all of their browser's tabs.

This means that in some cases, a chat session can last for a significant amount of time. For example, if a conversation takes place via Voiceflow's [Dialogue Manager API](ref:stateinteract-1) or [Zapier integration](doc:zapier) and is connected to an email tool, a chat session could last weeks on a back-and-forth email thread.

<br />

## Enabling session inactivity timeouts

<Callout icon="❗️">
  Session timeouts are currently only fully supported when using Voiceflow's [Web chat widget](doc:chat-widget) an [Phone](doc:telephony) [Dialogue Manager API]( integration. Conversations taking place through Voiceflow's ref:stateinteract-1) may experience unexpected behaviour if the timeout option is enabled.
</Callout>

For some use-cases, you may wish to automatically end all chat sessions after a period of inactivity. This can be useful if you're using an external tool to analyze previous conversations via [Voiceflow's transcript API](ref:transcriptpubliccontroller_findonewithlogs) and want to build guardrails around processing incomplete conversations.

To enable the inactivity timeout, open your agent's settings, then select **Behaviour** > **General**. Then, toggle on the **Timeout** option. You'll be able to configure your **idle timeout** setting to any value between 60 seconds and 43200 seconds (12 hours).

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSRtWX4tFNQ3iypoMFaJZwq9en7SuAdfDmCvL1" />

## Frequently asked questions

### What is the `user_id` variable?

The `user_id` variable is a unique value that identifies a specific chat session.

* When calling into an agent via Voiceflow's [phone](doc:telephony) integration, `user_id` will automatically be set to the user's phone number.
* When using the [web chat widget](doc:chat-widget), it will be automatically set, but can be overridden to a custom value in the widget's embed code.
* When working with the [Dialogue Manager API](ref:stateinteract-1), you must manually set the `user_id`.

If a user continues interacting with your agent using the same `user_id`, they'll continue with the same conversation, provided the chat session has not ended.

<br />

### What happens if a chat session tied to a specific `user_id` ends, but then I send a message or event using the same `user_id`?

If a chat session tied to a `user_id` ends, but then the same `user_id` is used to send a new message or event, the conversation will reset to the beginning. No chat history will persist in the new conversation, and a new transcript will be generated. Variables tied to a `user_id` will persist between chat sessions.

For example, imagine a user with the`user_id` of `Connor`  is mid-way through a conversation your agent on his laptop. Your agent has the idle timeout option enabled and set to 3600 seconds (one hour). If Connor decides to go on a four hour hike mid-conversation, when he returns, his conversation will have ended. If he sends another message with the same `user_id` (`Connor`), he'll start the conversation from the beginning your agent's workflow.

<br />

### What happens to a transcript when a chat session ends?

Each [transcript](doc:transcripts) is tied to a chat session, meaning all messages within a single chat session will be shown in a single transcript (and only those messages).

When a chat session ends, the transcript will no longer be marked as **in progress** when viewed on Voiceflow. When using [Voiceflow's API to pull a transcript](ref:transcriptpubliccontroller_findonewithlogs), the `endedAt` value will be set to the time that the chat session ended.

Once a transcript is no longer marked as in progress and has a `endedAt` value set, it is guaranteed to no longer update. Any further messages sent by the user will begin the conversation from the default state in a new chat session and transcript.

<br />

### How do my chat sessions affect my evaluations?

To ensure useful analytics are available, [Evaluations](doc:evaluations) are only run when a chat session is finished. If you're a heavy user of evaluations, you may wish to [enable the idle timeout setting](https://docs.voiceflow.com/docs/session-timeouts#enabling-session-inactivity-timeouts) to ensure the timely generation of evaluation results.
