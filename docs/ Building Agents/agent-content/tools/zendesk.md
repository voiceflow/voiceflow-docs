---
title: Zendesk
excerpt: Zendesk integration into your Voiceflow agent.
deprecated: false
hidden: false
metadata:
  robots: index
---
Easily connect your Voiceflow agent with Zendesk to manage support tickets, users, and organizations — directly from your workflows. Use Zendesk actions in both Agent and Tool steps for flexible control over your support processes.

## Basic usage

![](https://files.readme.io/f0c3d825ec547dbd2b160f55c79463c658092031280b0ecca842680084aee47e-CleanShot_2025-08-06_at_14.11.592x.png)

<br />

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

<Callout icon="👀">
  ### Be wary of each action's required arguments.

  Each Zendesk action may require unique and different arguments. Ensure you verify them and decide whether they are to be defaulted to a value, provided in advance(hardcoded) or provided to the agent to be collected.

  ![](https://files.readme.io/8b407eebf2bd5e7dc062b9aaffdd647fa971f2ef796440c6f8ac28633abb38cb-CleanShot_2025-08-06_at_13.57.132x.png)
</Callout>