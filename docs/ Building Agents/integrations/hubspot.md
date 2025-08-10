---
title: Hubspot
excerpt: >-
  Use the HubSpot actions in both Agent and Tool steps to create powerful sales,
  support, and marketing workflows.
deprecated: false
hidden: true
metadata:
  robots: index
---
# HubSpot

Use HubSpot actions in both Agent and Tool steps for dynamic CRM management and real-time data access.\
Easily connect your Voiceflow agent with HubSpot to store, retrieve, and update contact, deal, and company data directly from your conversations.

## Basic usage

![](https://files.readme.io/example-hubspot-screenshot.png)

<Callout icon="🔐" theme="info">
  To use the HubSpot integration, you'll need to **OAuth into HubSpot** from the Voiceflow Creator.\
  This ensures your agent can read and write CRM data securely from your connected HubSpot account.
</Callout>

## What you can do with HubSpot

The HubSpot integration supports the following actions:

| Action         | Description                                              |
| :------------- | :------------------------------------------------------- |
| Create contact | Add a new contact to your HubSpot CRM.                   |
| Get contact    | Retrieve detailed information about an existing contact. |
| Update contact | Modify details of an existing contact.                   |
| Create deal    | Add a new deal to your sales pipeline.                   |
| Get deal       | Retrieve details of an existing deal.                    |
| Update deal    | Update the stage or details of an existing deal.         |
| Create company | Add a new company record to HubSpot.                     |
| Get company    | Retrieve company information from HubSpot.               |
| Update company | Modify existing company details.                         |

## Use cases

Here are some common ways to use HubSpot in your Voiceflow agent's workflow:

* Automatically create contacts from new leads captured in conversation.
* Pull deal status for a sales representative in real-time.
* Update a company profile with the latest interaction details.
* Create follow-up deals when a conversation indicates a potential upsell.

> **Example:** For `Get contact`, you might provide an LLM description such as `Retrieve details of a customer using their email address from the conversation`.

<Callout icon="👀" theme="default">
  ### Be wary of each action's required arguments.

  Each action may require unique parameters such as `contactId`, `dealId`, or `companyId`.\
  Decide whether these should be *defaulted, hardcoded, or collected by the agent*.
  Always provide LLM descriptions for each input variable so the agent knows exactly how to use them.

  ![](https://files.readme.io/example-hubspot-args.png)
</Callout>

## Frequently asked questions

### Can I update multiple properties at once?

> Yes. When using **Update contact**, **Update deal**, or **Update company**, you can pass multiple properties in a single request. Ensure you clarify and specify this in the Agent's `Instructions`.

### Can I search for a contact by email?

> Yes. The **Get contact** action supports querying contacts by email address.

### Can I link a deal to a specific company?

> Yes. When creating or updating a deal, you can provide the `companyId` to link the deal to an existing company.

### Can I bulk import data into HubSpot through Voiceflow?

> No. Voiceflow's HubSpot integration is designed for real-time, conversational updates rather than large-scale imports.

<LinkCard type="Doc" title="Integrations" description="Learn more about what integrations are available to supercharge your agent's workflow and capabilities." href="https://docs.voiceflow.com/update/docs/integrations#/" />