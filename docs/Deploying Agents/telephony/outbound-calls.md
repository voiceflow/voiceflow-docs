---
title: Outbound Calls
excerpt: Use your Voiceflow agent to make automated outbound calls
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Voiceflow supports outbound calling using Twilio, allowing your agent to initiate a call to any number via API. This is useful for automating voice actions - such as welcome calls, reminders, or follow-ups - triggered from tools like Zapier or your own scripts.

> ⚠️ Comply with your local regulations regarding automated calls
>
> In many regions, it is a violation of law to create automated outbound calls without consent. This may lead to your Twilio number or account being suspended and potentially incur fines. You are solely responsible for ensuring compliance with all relevant regulations.
>
> * [Twilio Phone Number Regulations](https://www.twilio.com/en-us/guidelines/regulatory)
> * [Twilio Voice Guidelines](https://www.twilio.com/en-us/guidelines/voice)

> 📘 Alpha Version
>
> Outbound calls are currently in an alpha version and the API endpoint, `/v1alpha1/` may be subject to change during development.

<br />

## How it works

Under **Integration** > **Telephony** after assigning a number to an agent, you can "View" the outbound call API for that number. Each assigned number will have a unique API URL, corresponding to their internal ID.

<Image align="center" src="https://files.readme.io/79fd01c1b813367b662fce296a799976c804eedac2d3706b69259c072d348106-Capture_decran_le_2024-12-19_a_18.42.44.png" />

<Image align="center" src="https://files.readme.io/b587512ab656ad543b9dade9b3b0e545960d12fffdc12d3d337273b4c2aa0563-Capture_decran_le_2024-12-19_a_18.56.58.png" />

The API is presented in a `curl` format. It must include an `Authorization` header with the [associated API Key](https://docs.voiceflow.com/docs/step-2) of the agent. This is under **Integration** > **API Keys**

### API Information

`POST https://runtime-api.voiceflow.com/v1alpha1/phone-number/<PHONE_NUMBER_ID>/outbound`

#### Headers

* `Authorization`: [`<DM API Key>`](https://docs.voiceflow.com/docs/step-2)

#### Body

```typescript
{
  "to": string,
  "variables": {} // object containing any voiceflow variables you want to assign during launch
}
```

You can use the `variables` property in the body of the request to provide additional context or metadata about the particular user the call is being made to.

The number of outbound calls you can make concurrently is [limited by your plan](https://docs.voiceflow.com/docs/setting-up-twilio-integration#sorry-no-agents-are-available-to-take-your-call-at-this-time) and is in a shared pool with inbound calls.

## Troubleshooting

### 500 Internal Server Error

It is possible your number does not have the necessary permissions to make outbound calls. There are often strict regulations depending on the region.

Try enabling the permission for the region with the link below.\
[https://www.twilio.com/console/voice/calls/geo-permissions/low-risk](https://www.twilio.com/console/voice/calls/geo-permissions/low-risk)