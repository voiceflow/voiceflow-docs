---
title: Zendesk
excerpt: Zendesk integration into your Voiceflow agent.
deprecated: false
hidden: true
metadata:
  robots: index
---
Easily connect your Voiceflow agent with Zendesk to manage support tickets, users, and organizations — directly from your workflows. Use Zendesk actions in both Agent and Tool steps for flexible control over your support processes.

## Basic usage

<br />

<Video src="https://w17llroiln.ufs.sh/f/JH4JLc5mceYkSjPbKcmMCapOVQL9rmTnx1hYXiR0P3ZbNgMd" />

## What you can do with Zendesk

Voiceflow's Zendesk integration supports a full range of ticket and user management operations. Here are the available actions:

| Action              | Description                                                               |
| :------------------ | :------------------------------------------------------------------------ |
| Add ticket comment  | Append a public or private comment to an existing support ticket.         |
| Create ticket       | Generate a new ticket with custom subject, description, tags, and more.   |
| Find group          | Look up support groups by ID or name.                                     |
| Find latest comment | Retrieve the most recent comment on a specific ticket.                    |
| Find ticket(s)      | Search for one or more tickets by custom criteria (user ID, status, etc). |
| Find user           | Search for users based on email, name, or other identifiers.              |
| Update organization | Edit an existing organization’s details (e.g. domain, name, notes).       |
| Update ticket       | Modify an existing ticket’s priority, status, tags, and more.             |

## Use cases

Here's some common use cases on when you might use Zendesk in your agent's workflow:

* Auto-log support issues raised in chat or voice conversations.
* Pull the latest comment from an ongoing ticket to give users real-time updates.
* Update a ticket’s status based on a user’s spoken intent (e.g., “I want to cancel”).

<Callout icon="👀" theme="default">
  ### Be wary of each action's required arguments.

  Each Zendesk action requires specific arguments. Be sure to review each one and decide whether it should be _defaulted, hardcoded, or collected by the agent_. Add an LLM description for every argument to help the assistant understand its purpose and how to populate it.

  ![](https://files.readme.io/8b407eebf2bd5e7dc062b9aaffdd647fa971f2ef796440c6f8ac28633abb38cb-CleanShot_2025-08-06_at_13.57.132x.png)
</Callout>

<br />

## Syncing Zendesk Help with your Knowledge Base

Beyond ticket and user management, you can also connect your **Zendesk Help Center** to Voiceflow’s Knowledge Base. This allows your agent to surface trusted company resources — such as product guides, policies, or FAQs — alongside live ticketing actions.

By syncing Zendesk Help, your agent has access not just to Zendesk functionality (creating/updating tickets), but also Zendesk knowledge, enabling more contextual, accurate, and helpful responses for your users.


## Frequently asked questions

### What can I do with the Zendesk integration?

> You can trigger Zendesk actions such as creating tickets, finding users, adding comments, or updating tickets directly from your workflow. This allows you to build support workflows that automatically interact with your Zendesk account based on user input or logic flows.

### How do I provide the required inputs for a Zendesk action?

> Each Zendesk action requires specific arguments (e.g., ticket ID, user email, comment body). You can either:
>
> * Pre-fill these values in the tool or agent step,
> * Collect them from the user using the agent
> * Set default values for fallback cases.
>
> Always include a clear LLM description for each argument to help the agent understand how to retrieve the right data.

### What happens if a ticket or user isn’t found?

> If the Zendesk action fails to find the requested resource (like a ticket or user), the agent will inform the user they were unable to perform the action. You can add conditional logic in the agent's prompt to handle these cases gracefully, such as prompting the user to re-enter information or skipping to an _exit condition_.

### Can I update an existing ticket based on user replies?

> Yes. Use the "Update ticket" or "Add ticket comment" actions and pass in the correct ticket ID (either stored earlier in the flow or retrieved using “Find ticket”). This enables dynamic support workflows in Voiceflow that react to user responses in real time.

﻿

<LinkCard type="Doc" title="Voiceflow Integrations" description="Learn more about what integrations are available to supercharge your agent's workflow and capabilities." href="https://docs.voiceflow.com/update/docs/integrations#/" />
