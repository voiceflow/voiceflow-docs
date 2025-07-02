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
Credits are the currency in Voiceflow to pay for AI usage and project hosting. Voiceflow charges credits for:

* **Agent hosting** - charged by messages sent by the user and minutes the agent spends on phone calls.
* **AI service usage** - this includes LLM tokens, text-to-speech generation, and speech-to-text usage.

Each Voiceflow credit costs $0.005 USD on non-Enterprise plans and can be used for either Agent hosting or AI services. Voiceflow only makes money on Agent hosting - AI service costs are passed through at cost, with no markup.

## What actions consume credits?

Credits are charged differently for chat and voice agents because they run in different ways: chat agents are asynchronous and cheaper, while voice agents operate in real time and cost more.

### Chat Agents

| Action                                                                                                                       | Credit Cost                                                                                                         |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| **User sends a chat message** (including through the [Dialogue Manager API](https://docs.voiceflow.com/reference/overview#/) | 1 credit ($0.005)                                                                                                   |
| **Agent sends a chat message**                                                                                               | 0 credits (free)                                                                                                    |
| **API calls, function calls, logic steps, and other similar actions**                                                        | 0 credits (free)                                                                                                    |
| **LLM usage**                                                                                                                | Based on tokens used, billed at cost (see [pricing table](https://docs.voiceflow.com/docs/credits-pricing-table#/)) |

<br />

**Here's how this works in practice for a five turn conversation:**

<Accordion title="Example Conversation" icon="fa-comments">
  **Agent:** Hi! How can I help? *\[0.0001 Credits for LLM usage]*

  **User:** I need to book a demo *\[1 Credit]*

  **Agent:** Got it, I can help you with that. One moment please... *\[0.0001 Credits for LLM usage]*

  **Agent:** \<Executes an API call to pull up user info> *\[0 Credits]*

  **Agent:** \<Runs an LLM prompt to format API response> *\[0.01 Credits]*

  **Agent:** I have pulled up your account information *\[0.0002 Credits for LLM usage]*

  **User:** Thanks! *\[1 Credit]*
</Accordion>

* User sends 5 messages → 5 credits
* Agent sends 15 messages + 3 API calls → 0 credits
* LLM usage - GPT-4o Mini → \~1 credit

Total: 6 credits ($0.03)

<br />

### Voice Agents

Voice agents are billed per minute, plus text-to-speech, speech-to-text, and LLM usage. Telephony rates (such as renting a phone number and connection fees) are charged directly by our supported providers: [Twilio](https://twilio.com) and [Vonage](https://vonage.com).

| Action                         | Credit Cost                                                                                     |
| ------------------------------ | ----------------------------------------------------------------------------------------------- |
| **Agent call time**            | 10 credits per minute ($0.05/min)                                                               |
| **Text-to-Speech (TTS)**       | Billed per character ([vendor rates](https://docs.voiceflow.com/docs/credits-pricing-table#/))  |
| **Speech-to-Text (STT)**       | Billed per minute ([vendor rates](https://docs.voiceflow.com/docs/credits-pricing-table#/))     |
| **LLM usage**                  | Based on tokens used, [billed at cost](https://docs.voiceflow.com/docs/credits-pricing-table#/) |
| **Telephony provider charges** | Billed separately by provider (Twilio or Vonage)                                                |

<br />

**Here's an example of how this works in practice for a five minute conversation:**

* Agent talk time (5 min x 10 credits per minute) → 50 credits
* LLM usage - GPT-4o Mini → \~1 credit
* Text-to-Speech - ElevenLabs Flash (2.5 min, \~2,140 chars, 9 credits per 1,000 characters) → 20 credits
* Speech-to-Text - Deepgram Nova 3 - (5 min x 1 credit per minute) → 5 credits

Total: 76 credits ($0.38, or $0.076 per minute)

<br />

<br />

Need help estimating how many credits your LLM or TTS usage will use? Check out our credit usage estimation calculator.

<LinkCard type="Tool" title="Credit usage estimator" description="Estimate how many credits your agents will consume per month and have the best value plan recommended to you." href="./estimate-your-credit-usage#credits-estimation-calculator" />

<br />

## Why Voiceflow uses credits

We use a credit system to simplify how you pay for Agent hosting and AI services (like LLMs, TTS, and STT), without locking you into specific vendors or surprise bills.

For you, this means that:

* **No separate AI vendor accounts are required**: use models from OpenAI, Anthropic, Google, Meta, and more — all through one Voiceflow account.
* **You can switch AI vendors anytime**: as prices or quality shift, you can change providers without rewriting your agent or renegotiating contracts.
* **Pay-as-you-go with transparent costs**: every action has a clear credit cost, and most non-AI logic (like API calls or logic steps) is free.
* **You have access to volume discounts**: Voiceflow negotiates bulk rates with AI providers and passes those savings directly to you.

> ℹ️
>
> **Example:** If ElevenLabs lowers TTS rates or Anthropic releases a cheaper model, you’ll get those savings automatically — no manual work or vendor management required.

## How Voiceflow makes money

Voiceflow makes money through the combination of Paid Plans, and Credits.

1. **Paid Plans:** Paid plans determine the features you have access to when building Agents. Building and Agent capabilities will differ across the Starter (free), Pro, Business, and Enterprise plans.
2. **Credit Tiers:** Credit tiers determine the number of Credits your Voiceflow Workspace is granted every month, or year. Each Paid plan has a default number of Credits granted each month/year (ie Pro is 10K Credits). Each Paid plan can be upgraded to a higher Credits tier for more usage. [You can learn more on our pricing page.](https://www.voiceflow.com/pricing)

> 🧠 Unlock a 10% discount and a year's worth of Credits
>
> When you upgrade to an Annual Credits tier, you get the entire year's worth of Credits upfront.
>
> For example, the Pro plan grants 10K Credits per month, but if you upgrade to an Annual plan you get a 10% discount and all 120K yearly Credits upfront.

## Frequently Asked Questions about Credits

### What happens if I run out of Credits?

* You will be sent usage warning emails automatically at 50%, 75%, 90%, and 100% of Credits Usage
* Once Credits have run out, services that consume Credits in Voiceflow will stop working
* To avoid Agent outages, monitor your Credits usage and upgrade to a Credits tier that matches your desired usage level. You can downgrade to a lower Credits tier at any time.

### Can I turn on auto-upgrade for Credit tiers?

* Not today, we are working on this!

### How can I optimize my agent to use less credits?

We're on your side - we bill LLM and TTS usage **at cost**, meaning we don't make any profit from you using these features. We also pass along any bulk discounts we get from our providers onto you. This means it's in our best interest to help you optimize your agent to use the least credits possible when building with LLMs and TTS.

We've put together our tips on optimizing agents in the course below, and update whenever we hear new ideas from our community.

<LinkCard type="Course" title="Optimize your AI agent to use less credits" description="Save money while building powerful AI agents. We'll show you our tips on how to reduce how many credits you're using." href="https://www.voiceflow.com/lessons/what-are-credits" imageSrc="https://cdn.prod.website-files.com/657639ebfb91510f45654149/67f7f24a1b2cf13a2bc90086_Credits.png" />