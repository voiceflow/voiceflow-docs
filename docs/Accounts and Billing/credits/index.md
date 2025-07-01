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

* `One vendor to access every AI model` Voiceflow customers get access to 10+ AI service vendors across LLMs, TTSs, and STTs without needing to signup or contract multiple AI vendors.
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

### Chat Agents

Chat Agents are cheaper than Voice Agents as they require less AI services to run, and are async.

* **User-to-Agent Chat Message**: Costs 1 Credit ($0.005) when a User sends a chat message to the Agent (including through the [Dialogue Manager API](https://docs.voiceflow.com/reference/overview#/)).
* **Agent-to-User Chat Message**: Costs 0 Credits (free) for an Agent to send chat messages to the User.
* **Agent API calls, and logic execution**: Costs 0 Credits (free) to make API calls, orchestrate logic, or perform any other logic 'behind the scenes' that does not require AI services to be called.
* **LLM Usage**: LLM tokens are charged using Credits at the same underlying token price that AI services charge Voiceflow. The Credit cost for each LLM model can be found on our [Credits Pricing Table](https://docs.voiceflow.com/docs/credits-pricing-table#/).

<br />

> 💬 Estimate Chat Agent Credit cost
>
> > ✅ AI Services used
> >
> > * **Chat Agent Hosting:** Voiceflow
> > * **LLM:** GTP4o Mini (OpenAI)
>
> > 📘 Cost for 5-turn Chat conversation
> >
> > * **Chat Agent Hosting:** Agent sends 15 messages with 3 API calls \[0 Credits]
> > * Chat Agent Hosting: User sends 5 replies \[5 Credits]
> > * **LLM:** Advanced Agent prompt with tool calls \[1 Credit]
>
> ***
>
> **Total cost:** 6 Credits ($0.03)

> 💬 Estimate Chat Agent Credit cost
>
> ***LLM Used: OpenAI GPT4o Mini***
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
> **Total Conversation Credit Usage:** 2.1 Credits ($0.0105)

<br />

### Voice Agents

Voice AI costs more than Chat AI because it requires more AI services to operate and requires real-time compute which is more expensive for Voiceflow vs Chat AI which is async.

* **Voice AI minutes**: Every minute that your Voice Agent is talking to a User costs 10 Credits ($0.05).
* **TTS (text-to-speech)**: AI speech generation is charged per character, the same as the TTS vendors. The Credit per characters price for each TTS model is listed on our [Credits Pricing Table](https://docs.voiceflow.com/docs/credits-pricing-table#/).
* **STT (speech-to-text) usage**: User speech recognition is used to turn human speech into text for Agents to process. Each STT vendor charges a different Credits cost per minute, found in [Credits Pricing Table](https://docs.voiceflow.com/docs/credits-pricing-table#/).
* **LLM Usage**: LLM tokens are charged using Credits at the same underlying token price that AI services charge Voiceflow. The Credit cost for each LLM model can be found on our [Credits Pricing Table](https://docs.voiceflow.com/docs/credits-pricing-table#/).
* **Telephony Usage:** If you are connecting your Voice Agent to a telephony provider like Twilio or Vonage, they will charge their own price separate from Voiceflow per call connected.

<br />

> 🔈 Estimate Voice Agent Credit cost
>
> > ✅ AI Services used
> >
> > * **Voice Agent Hosting:** Voiceflow
> > * **LLM:** GTP4o Mini (OpenAI)
> > * **TTS:** EllevenLabs Flash (EllevenLabs)
> > * **STT:** Deepgram Nova 3 (Deepgram)
> > * **Telephony:** None
>
> > 📘 Cost for 5-minute call (50/50 talk time User:Agent)
> >
> > * **Voice Agent Hosting:** 50 Credits (5 minutes x 10 Credits per minute)
> > * **LLM:** 1 Credit (roughly 500 input and 500 output tokens for 2140 characters, basic prompt)
> > * **TTS:** 20 Credits (2.5 mins of AI talk time, \~2,140 characters, 9 Credits per 1K characters)
> > * \*\*STT: \*\*5 Credits (5 minutes x 1 Credit per minute)
>
> ***
>
> **Total cost:** 76 Credits ($0.38, or $0.076 per minute)

Need help estimating how many credits your LLM or TTS usage will use? Check out our credit usage estimation calculator.

<LinkCard type="Tool" title="Credit usage estimator" description="Estimate how many credits your agents will consume per month and have the best value plan recommended to you." href="./estimate-your-credit-usage#credits-estimation-calculator" />

# Frequently Asked Questions about Credits

## What happens if I run out of Credits?

* You will be sent usage warning emails automatically at 50%, 75%, 90%, and 100% of Credits Usage
* Once Credits have run out, services that consume Credits in Voiceflow will stop working
* To avoid Agent outages, monitor your Credits usage and upgrade to a Credits tier that matches your desired usage level. You can downgrade to a lower Credits tier at any time.

## Can I turn on auto-upgrade for Credit tiers?

* Not today, we are working on this!

## How can I optimize my agent to use less credits?

We're on your side - we bill LLM and TTS usage **at cost**, meaning we don't make any profit from you using these features. We also pass along any bulk discounts we get from our providers onto you. This means it's in our best interest to help you optimize your agent to use the least credits possible when building with LLMs and TTS.

We've put together our tips on optimizing agents in the course below, and update whenever we hear new ideas from our community.

<LinkCard type="Course" title="Optimize your AI agent to use less credits" description="Save money while building powerful AI agents. We'll show you our tips on how to reduce how many credits you're using." href="https://www.voiceflow.com/lessons/what-are-credits" imageSrc="https://cdn.prod.website-files.com/657639ebfb91510f45654149/67f7f24a1b2cf13a2bc90086_Credits.png" />