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

Credits are a currency used across Voiceflow and are how you're billed for your agent's usage. Certain actions performed by one of your agents will consume credits. Your credit balance is managed at workspace level, meaning that a single credit balance is shared by all agents in a workspace.

Each plan includes a certain amount of credits. [You can learn more on our pricing page.](https://www.voiceflow.com/pricing)

## What actions consume credits?

Most actions performed by an AI agent on the Voiceflow platform will consume credits. The specific amounts vary depending on the type of action:  

* **Messages:** each message sent by an AI agent will consume 1 credit.
* **Call minutes**: every minute your AI agent spends on a call (inbound or outbound) will consume 10 credits.
* **LLM (Large Language Model) Usage**: LLMs are used for various features, including the [Prompt step](doc:prompt-step), [Agent step](doc:agents), [prompt-based logic](https://docs.voiceflow.com/docs/logic#/), and [intent detection](https://docs.voiceflow.com/docs/intents#/). Credits are billed **at-cost** for LLM usage - more powerful models like GPT-4 Turbo will consume more credits per use than more lightweight models such as GPT-4o mini. [Use this calculator to estimate your LLM costs.](https://docs.google.com/spreadsheets/d/1VumQjS1Xx86Cp1jewVKy0T2m3H8j0W7sctvAp4aGIz8/edit?usp=chrome_ntp\&ouid=111138026718917478511)
* **TTS (Text-to-Speech) Usage** TTS generation for voice agents is charged per character and is an additional cost to call minutes. [Use this calculator to estimate your TTS costs.](https://docs.google.com/spreadsheets/d/1VumQjS1Xx86Cp1jewVKy0T2m3H8j0W7sctvAp4aGIz8/edit?usp=chrome_ntp\&ouid=111138026718917478511)

<br />

## What actions don't consume credits?

While usage of your agent will incur credit charges, many actions do not cost credits. These include:

* Messages sent from inside Voiceflow Creator while building an agent do not consume credits. However, any LLM or TTS usage incurred while generating these messages **will** incur credit charges.
* Querying or adding data to the Knowledge Base will never consume credits.
* Connecting to integrations through tools or functions or using the API step does not consume credits. However, any messages sent as a result of these actions will incur credit charges.
* Deploying and backing up your agent, adding editors to your workspace, and any other action that isn't direct usage of your agent will not consume credits.