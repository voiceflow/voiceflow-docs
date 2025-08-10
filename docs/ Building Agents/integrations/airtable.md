---
title: Airtable
excerpt: >-
  Use Airtable actions in both Agent and Tool steps for dynamic, real-time data
  interactions with your data.
deprecated: false
hidden: false
metadata:
  robots: index
---
Easily connect your Voiceflow agent with Airtable to manage and manipulate records in your bases — directly from your workflows. Use Airtable actions in both Agent and Tool steps for dynamic, real-time data interactions.

## Basic usage

<Video src="https://w17llroiln.ufs.sh/f/JH4JLc5mceYkNkm8x2DqntsPVJCcKXlTDvSfiBxWbad4Rop6" />

<br />

<Callout icon="🔐" theme="info">
  To use the Airtable integration, you'll need to **OAuth into Airtable** from the Voiceflow Creator. This gives your agent secure access to your Airtable bases and tables.
</Callout>

## What you can do with Airtable

Voiceflow's Airtable integration enables full CRUD (Create, Read, Update, Delete) operations on your Airtable records. Here are the available actions:

| Action        | Description                                                          |
| :------------ | :------------------------------------------------------------------- |
| Create record | Add a new row to a specific table in your Airtable base.             |
| Delete record | Remove a row from your table by specifying the record ID.            |
| Get record    | Fetch a single row by its unique record ID.                          |
| List records  | Retrieve multiple rows, optionally filtered by conditions or fields. |
| Update record | Modify one or more fields in an existing row using the record ID.    |

## Use cases

Here are some common ways to use Airtable in your Voiceflow agent's workflow:

* Log incoming leads or support requests as new records in your Airtable CRM.
* Pull product or order information from an Airtable inventory table.
* Update form responses or survey entries based on user inputs in a conversation.

<Callout icon="👀" theme="default">
  ### Be wary of each action's required arguments.

  Each Airtable action has unique required fields. Ensure you review them and determine whether they should be *defaulted, hardcoded, or collected by the agent*. Add an LLM description for every argument — this helps the assistant understand how to populate each field appropriately.

  It is advised that fields such as `baseId` and `tableIdOrName` are defaulted as a user may not know them.

  ![](https://files.readme.io/421a9c61fb5bc046a5b09978449321b0669938c28dc2ef007d228fc26d82fcec-CleanShot_2025-08-08_at_13.15.502x.png)
</Callout>

## Frequently asked questions

### What can I do with the Airtable integration?

> You can use Voiceflow to create, retrieve, update, or delete records from Airtable tables. This enables powerful, database-driven workflows that dynamically adjust based on user input or logic in your assistant.

### How do I specify which table or base to work with?

> Each action requires you to provide the **Base ID** and **Table name**. These can be hardcoded if your use case is fixed, or passed in dynamically through user input or context.

### How do I ensure the data fields match my Airtable schema?

> Make sure each field you send matches the exact name and format expected in Airtable. Use LLM descriptions to help your agent map user input (like "my name is John") to the correct field ("Name").

### Can I update only some fields without overwriting others?

> Yes. When using the "Update record" action, only the fields you specify will be modified — any omitted fields will remain unchanged in Airtable.

<LinkCard type="Doc" title="Integrations" description="Learn more about what integrations are available to supercharge your agent's workflow and capabilities." href="https://docs.voiceflow.com/update/docs/integrations#/" />