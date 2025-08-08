---
title: Gmail
deprecated: false
hidden: true
metadata:
  robots: index
---
Easily connect your Voiceflow agent with Gmail to send emails dynamically based on user input or agent logic. Use the Gmail action in both Agent and Tool steps for maximum flexibility in your email workflows.

## Basic usage

![](https://files.readme.io/f0c3d825ec547dbd2b160f55c79463c658092031280b0ecca842680084aee47e-CleanShot_2025-08-06_at_14.11.592x.png)

<Callout icon="🔐" theme="info">
  To use the Gmail integration, you'll need to **OAuth into Gmail** from the Voiceflow Creator. This ensures your agent can send authenticated emails securely from your connected account.
</Callout>

## What you can do with Gmail

The Gmail integration currently supports one powerful action:

| Action     | Description                                                                                  |
| :--------- | :------------------------------------------------------------------------------------------- |
| Send email | Send an email to one or more recipients with custom subject, body, and optional attachments. |

## Use cases

Here are some common ways to use Gmail in your Voiceflow agent's workflow:

* Send a confirmation or follow-up email after a conversation.
* Deliver automated receipts or summaries of support tickets.
* Email a team member or user with data collected during the interaction.

<Callout icon="👀" theme="default">
  ### Be wary of each action's required arguments.

  The **Send email** action requires several key arguments like `To`, `Subject`, and `Body`. Ensure you decide whether each field should be *defaulted, hardcoded, or collected by the agent*. Include LLM descriptions to help the assistant understand how to populate these values properly.

  ![](https://files.readme.io/8b407eebf2bd5e7dc062b9aaffdd647fa971f2ef796440c6f8ac28633abb38cb-CleanShot_2025-08-06_at_13.57.132x.png)
</Callout>

## Frequently asked questions

### Can I send emails to multiple people?

> Yes, the `To` field can accept multiple comma-separated email addresses. Make sure the agent formats this field correctly before sending by instructing it to do so in its `Instructions`.

### Can I personalize the email content?

> Absolutely. Use agent-collected variables (like name, order info, etc.) in the subject or body to generate fully personalized messages. Ensure you instruct the agent to personalize the email in its `Instructions`.

### What happens if the email fails to send?

> If the Gmail action fails (e.g., due to invalid addresses or missing fields), the agent will surface an error. You can handle this with conditional prompts or fallbacks in your flow.

### Can I include attachments?

> Not currently. The Gmail integration supports plain text and HTML bodies but does not yet support file attachments.

<LinkCard type="Doc" title="Voiceflow Integrations" description="Learn more about what integrations are available to supercharge your agent's workflow and capabilities." href="https://docs.voiceflow.com/update/docs/integrations#/" />