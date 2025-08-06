---
title: Tool step
excerpt: Add Integrations, Functions and API requests to your agent's workflow.
deprecated: false
hidden: false
metadata:
  robots: index
---
The Tool Step allows you to run any tool — like sending an email, querying a Google Sheet, or updating a CRM — anywhere in your workflow, not just within an agent step. This gives you more control and flexibility over when and how you trigger third-party integrations. You’ll find the Tool Step in the ‘**Dev**’ section of the tool bar.

## Basic Usage

<Image align="center" className="border" border={true} src="https://files.readme.io/23665b7f9c7ed9126a038c2c7ed071dccc29a3ece10ba03fd607d3b49f58efff-image.png" />

## Use cases

You can use Tool Steps to:

* Send confirmation emails after an appointment is booked
* Trigger external workflows using Make.com
* Log conversation outcomes in Hubspot
* Create or update tickets in Zendesk
* Fetch product data from Google Sheets
* Send SMS via Twilio
* Update customer records in Airtable or your CRM

And much more...

<Callout icon="📘" theme="info">
  All the functions, integrations and APIs available in the **Tool step** can also be toggled and selected for use in the **Agent step**.
</Callout>

## Example use case: *Gmail*

In the example shown, the Tool Step sends a confirmation email using Gmail. The following variables were configured:

> * To
> * Body
> * Bcc

Optional fields such as cc and bcc can also be added.

<Video src="https://w17llroiln.ufs.sh/f/JH4JLc5mceYkxy8f4ehHB63EAecr4ldMRpWtKsU5fLaQgvGk" />