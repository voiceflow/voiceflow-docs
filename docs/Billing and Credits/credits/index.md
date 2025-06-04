---
title: Credits
excerpt: >-
  Credits are Voiceflow's currency used to bill for agent usage. Each plan
  includes credits.
deprecated: false
hidden: false
metadata:
  robots: index
---
## What are credits?

Credits are a currency used across Voiceflow and are how you're billed for your agent's usage. Certain actions performed by your agents will consume credits. Your credit balance is managed at workspace level, meaning that a single credit balance is shared by all agents in a workspace.

Each plan includes a certain amount of credits. [You can learn more on our pricing page.](https://www.voiceflow.com/pricing)

<br />

## What actions consume credits?

Most actions performed by an AI agent on the Voiceflow platform will consume credits. The specific amounts vary depending on the type of action:  

* **Messages:** each message sent by an AI agent will consume 1 credit.
* **Call minutes**: every minute your AI agent spends on a call (inbound or outbound) will consume 10 credits.
* **LLM (Large Language Model) Usage**: LLMs are used for various features, including the [Prompt step](doc:prompt-step), [Agent step](doc:agents), [prompt-based logic](https://docs.voiceflow.com/docs/logic#/), and [intent detection](https://docs.voiceflow.com/docs/intents#/). Credits are billed **at-cost** for LLM usage - more powerful models like GPT-4 Turbo will consume more credits per use than more lightweight models such as GPT-4o mini.
* **TTS (Text-to-Speech) Usage** TTS generation for voice agents is charged per character and is an additional cost to call minutes.
* **STT (Speech-to-Text) Usage:** voice interfaces, such as [web chat widget](doc:chat-widget) and our [phone integration](doc:telephony) will consume credits as the user speaks.

Need help estimating how many credits your LLM or TTS usage will use? Check out our credit usage estimation calculator.

<LinkCard type="Tool" title="Credit usage estimator" description="Estimate how many credits your agents will consume per month and have the best value plan recommended to you." href="./estimate-your-credit-usage#credits-estimation-calculator" />

<br />

## What actions don't consume credits?

While usage of your agent will incur credit charges, many actions do not cost credits. These include:

* Messages sent from inside Voiceflow Creator while building an agent do not consume credits. However, any LLM or TTS usage incurred while generating these messages **will** incur credit charges.
* Querying or adding data to the Knowledge Base will never consume credits.
* Connecting to integrations through tools or functions or using the API step does not consume credits. However, any messages sent as a result of these actions will incur credit charges.
* Proactive messages sent using the [proactive messages feature](doc:proactive-messages) aren't considered messages and don't incur credit charges.
* Deploying and backing up your agent, adding editors to your workspace, and any other action that isn't direct usage of your agent will not consume credits.

<br />

## What happens if I run out of credits?

If your workspace's credit balance is depleted, AI agents associated with that workspace will stop sending and replying to messages in production. To reactivate your agents, [upgrade your Voiceflow plan to one that includes more credits.](doc:managing-your-voiceflow-plan)

<br />

## How can I optimize my agent to use less credits?

We're on your side - we bill LLM and TTS usage **at cost**, meaning we don't make any profit from you using these features. We also pass along any bulk discounts we get from our providers onto you. This means it's in our best interest to help you optimize your agent to use the least credits possible when building with LLMs and TTS.

We've put together our tips on optimizing agents in the course below, and update whenever we hear new ideas from our community.

<LinkCard type="Course" title="Optimize your AI agent to use less credits" description="Save money while building powerful AI agents. We'll show you our tips on how to reduce how many credits you're using." href="https://www.voiceflow.com/lessons/what-are-credits" imageSrc="https://cdn.prod.website-files.com/657639ebfb91510f45654149/67f7f24a1b2cf13a2bc90086_Credits.png" />