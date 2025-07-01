---
title: Credits
excerpt: >-
  Credits are Voiceflow's currency used to bill for Agent hosting and AI
  services.
deprecated: false
hidden: false
metadata:
  robots: index
---
## Intro to Voiceflow Credits

Credits are the currency in Voiceflow to pay for AI usage and Agent hosting. One Voiceflow Credit costs $0.005 for non-Enterprise plans, and can be used to purchase Agent hosting or AI service usage.

Voiceflow charges Credits:

* **Agent hosting** (ie User sent Chat AI messages, or Agent Voice AI minutes)
* **AI service usage** (ie LLM tokens, TTS minutes etc)

Voiceflow only takes margin (makes money) on Agent hosting. Credits spent on AI services are charged at the price  Voiceflow pays for the AI service on behalf of the Voiceflow customer.

## Benefits of Voiceflow Credits

* **One vendor to access every AI model** Voiceflow customers get access to 10+ AI service vendors across LLMs, TTSs, and STTs without needing to signup or contract multiple AI vendors.
  * For example, Voiceflow customers get access to Anthropic, Google, OpenAI, Meta, Groq models all within one platform without needing to contract multiple vendors.
  * For some AI vendors, Voiceflow has purchased an Enterprise license allowing unlimited usage of the underlying AI vendor without Voiceflow customers needing to purchase an Enterprise license themselves.
* **AI model flexibility:** Voiceflow customers can spend Credits on any AI service vendor, and easily switch between vendors as prices change or new models come out without worry of AI vendor lock-in.
* **Access to bulk discounting:** As Voiceflow's customer base spends more on AI services, Voiceflow negotiates bulk purchase discounts on AI services and passes these savings to customers.
  * Over time, this will make AI services purchased through Voiceflow cheaper for Voiceflow customers than purchasing directly through the underlying AI vendor.

## How Voiceflow makes money

Voiceflow makes money through the combination of Paid Plans, and Credits.

1. **Paid Plans:** Paid plans determine the features you have access to when building Agents. Building and Agent capabilities will differ across the Starter (free), Pro, Business, and Enterprise plans.
2. **Credit Tiers:** Credit tiers determine the number of Credits your Voiceflow Workspace is granted every month, or year. Each Paid plan has a default number of Credits granted each month/year (ie Pro is 10K Credits). Each Paid plan can be upgraded to a higher Credits tier for more usage. [You can learn more on our pricing page.](https://www.voiceflow.com/pricing)

> 🧠 Unlock a 10% discount and a year's worth of Credits
>
> When you upgrade to an Annual Credits tier, you get the entire year's worth of Credits upfront.
>
> For example, the Pro plan grants 10K Credits per month, but if you upgrade to an Annual plan you get a 10% discount and all 120K yearly Credits upfront.

## Actions that consume Credits

Voice and Chat Agents charge in different ways because Voice Agents are real-time, so they charge in minutes, and Chat Agents are async, so they charge per User message.

**Chat Agents Credit Cost**

Chat Agents are cheaper than Voice Agents as they require less AI services to run, and are async.

* **User-to-Agent Chat Message**: Costs 1 Credit ($0.005) when a User sends a chat message to the Agent (including through the [Dialogue Manager API](https://docs.voiceflow.com/reference/overview#/)).
* **Agent-to-User Chat Message**: Costs 0 Credits (free) for an Agent to send a chat message to the User.
* **Agent API calls, and logic execution**: Costs 0 Credits (free) to make API calls, orchestrate logic, or perform any other logic 'behind the scenes' that does not require AI services to be called.
* **LLM Usage**: LLM tokens are charged using Credits at the same underlying token price that AI services charge Voiceflow. The cost in Credits for each LLM model can be found on our pricing table.
* <br />
* Voiceflow are charged at the same underlying cost of the LLM provider. If an Agent-to-User Chat message requires LLM usage (like an Agent step or Prompt step), it will cost the number of tokens required to generate that message.

<br />

> 🧪 Example Chat AI Credit cost (using GPT4o-mini)
>
> *\*\*Agent:* \*\*Hi! How can I help? \[0.0001 Credits for LLM usage]
>
> \*\**User:* \*\*I need to book a demo \[1 Credit]
>
> \_\*\*Agent: \*\*\_Got it, I can help you with that. One moment please... \[0.0001 Credits for LLM usage]
>
> *\*\*Agent: \*\**\< Executes an API call to pull up user info > \[0 Credits]
>
> ***Agent:*** \< Runs an LLM prompt to format API response > \[0.01 Credits]
>
> ***Agent:*** I have pulled up your account information \[0.0002 Credits for LLM usage]
>
> \_\*\*User: \*\*\_Thanks! \[1 Credit]
>
> ***
>
> Total Credits Usage: 2.1 Credits ($0.0105)

<br />

**Voice Agents Credit Cost**

Voice AI Agents have 3 required component costs to every minute of usage: Agent Hosting, Text-to-Speech, Speech-to-Text. There are 2 optional components for usage, including LLM models, and telephony.

* **Voice AI minutes**: Every minute that your Voice Agent is talking to a User costs 10 Credits ($0.05).
* **TTS (text-to-speech) usage**: TTS generation for voice agents is charged per character and is an additional cost to call minutes.
* **STT (speech-to-text) usage**: voice interfaces, such as [web chat widget](doc:chat-widget) and our [phone integration](doc:telephony) will consume credits as the user speaks.
* **LLM (large language model) usage**: Any service in Voiceflow which requires LLM tokens consumes Credits at-cost, meaning Voiceflow does not make any money on these LLM tokens and simply charges the exact amount that Voiceflow will pay to the underlying model provider. The cost in Credits per model per token amount can be found in our Credits Pricing table.

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