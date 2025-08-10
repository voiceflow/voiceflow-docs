---
title: Twilio
deprecated: false
hidden: true
metadata:
  robots: index
---
## Twilio

Use the Twilio integration to send SMS messages directly from your Voiceflow agent.  
With this integration, your agent can notify users, send confirmations, or follow up with important information during a conversation.

## Basic usage

![](https://files.readme.io/your-twilio-integration-image.png)

<Callout icon="🔐" theme="info">
  To use the Twilio integration, you'll need to **OAuth into Twilio** from the Voiceflow Creator. This ensures your agent can securely send messages from your Twilio account.
</Callout>

## What you can do with Twilio

The Twilio integration currently supports the following action:

| Action     | Description                                   |
| :--------- | :-------------------------------------------- |
| Send SMS   | Send a text message to a specified phone number via Twilio. |

## Use cases

Here are some common ways to use Twilio in your Voiceflow agent's workflow:

* Send a confirmation code during an onboarding process.
* Deliver appointment reminders to customers.
* Send order updates or tracking links.
* Share follow-up information after a customer service conversation.

Example:

> If a customer says, “Can you text me the order tracking link?”, the agent might use **Send SMS** to send the link to their phone number.

Ensure you provide an `LLM description` for the tool so the agent understands when to use it.  

> E.g. for `Send SMS`, you might write: `Use this when the user asks to receive information or updates via text message.`

<Callout icon="👀" theme="default">
  ### Be wary of each action's required arguments.

  The `Send SMS` action requires at least a `to` phone number and a `message body`. Decide whether these should be *defaulted, hardcoded, or collected by the agent*. Always provide LLM descriptions for each input so the agent knows exactly how to use them.
</Callout>

## Frequently asked questions

### Can I send SMS messages to any country?

> Yes, as long as your Twilio account has the appropriate permissions and phone numbers configured for that region.

### Can I personalize the SMS content?

> Absolutely. You can insert Voiceflow variables into the message body to personalize the content for each recipient.

### Does sending an SMS cost money?

> Yes. Twilio charges per message based on your plan and the recipient’s country. Check Twilio’s pricing for details.

<LinkCard type="Doc" title="Integrations" description="Learn more about what integrations are available to supercharge your agent's workflow and capabilities." href="https://docs.voiceflow.com/update/docs/integrations#/" />
