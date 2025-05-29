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
> Outbound calls are currently in alpha and the API endpoint, `/v1alpha1/` may be subject to change during development.

<br />

## How it works

To trigger an outbound call, your app must make a `POST` request to a Voiceflow API endpoint associated with your agent. You can find this endpoint by navigating to **Interfaces > Telephony > View Outbound API**. Each agent has a unique API URL based on its internal ID.

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NS6cFRoyG9t5VYWaO0GfNrPI1S4ncjDlbBKXs7" />

<br />

The API is presented in a `curl` format. It must include an `Authorization` header with the [associated API Key](https://docs.voiceflow.com/docs/step-2) of the agent. This is under **Integration** > **API Keys**

<br />

## API reference

### Endpoint

`POST https://runtime-api.voiceflow.com/v1alpha1/phone-number/<PHONE_NUMBER_ID>/outbound`

<br />

### Headers

| Header          | Value                                                                                |
| --------------- | ------------------------------------------------------------------------------------ |
| `Authorization` | `Bearer <your DM API Key>` ([How to get it](https://docs.voiceflow.com/docs/step-2)) |

<br />

### Body

```json
{
  "to": "+15551234567",
  "variables": {
    "user_name": "Jane",
    "account_type": "Premium"
  }
}
```

* `to`: The phone number to call (E.164 format).
* `variables`: Optional. A JSON object with any Voiceflow variables to inject at launch.

<br />

<br />

The number of outbound calls you can make concurrently is [limited by your plan](https://docs.voiceflow.com/docs/setting-up-twilio-integration#sorry-no-agents-are-available-to-take-your-call-at-this-time) and is in a shared pool with inbound calls.

## Troubleshooting

### 500 Internal Server Error

It is possible your number does not have the necessary permissions to make outbound calls. There are often strict regulations depending on the region.

Try enabling the permission for the region with the link below.\
[https://www.twilio.com/console/voice/calls/geo-permissions/low-risk](https://www.twilio.com/console/voice/calls/geo-permissions/low-risk)