---
title: Inbound calls
deprecated: false
hidden: true
metadata:
  robots: index
---
Inbound calling lets users call a Twilio number and speak directly with your Voiceflow agent — no apps, just a phone call. If your Voiceflow agent is already[ linked to Twilio and published to production](/docs/telephony), you're ready to start handling inbound calls.

Here’s how to test it, and what to expect.

<br />

## Call your agent

From any phone, dial the Twilio number you connected to your Voiceflow project.

You should hear your Voiceflow agent pick up immediately and begin the conversation flow you designed. The experience will follow exactly what you’ve built inside your project — just like any user would hear it.

Congrats! Inbound calling is now live and working.

<br />

## Dev vs Prod environments

Voiceflow lets you connect your agent to either a Dev or Prod environment. Prod is ideal for live use cases, like when you're receiving real customer calls. Dev is perfectly fine for testing — inbound calling works the same in both environments.

Just make sure the environment you select in Interfaces > Telephony matches the one you publish to.

<br />

## Using multiple phone numbers (e.g. US & Canada)

If you want to support multiple regions (like having both a US and Canadian Twilio number), you can:

* Add multiple Twilio numbers to your account
* Link each number to the same Voiceflow agent
* Set up routing logic within your Voiceflow flow to personalize the experience based on region, language, or number called

As long as all numbers are tied to the same environment (Dev or Prod) and your agent is published there, inbound calls from any linked number will be routed correctly.

<br />

Outbound calls share the same concurrency pool as outbound calls. The number of simultaneous calls you can make is [determined by your plan limits](https://voiceflow.com/pricing).