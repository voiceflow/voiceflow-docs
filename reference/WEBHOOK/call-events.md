---
title: Call Events
excerpt: Send events from your project's calls to your webhook
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Webhooks allow you to receive real-time event notifications when calls start and end in Voiceflow, enabling seamless integration with your systems. This helps automate workflows, log call data, and trigger actions based on call events for both Twilio and web voice interactions.

Add your webhook URL under **Settings > Behavior > Voice > Call events webhook**.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0013315f5f5cb155195c11b88fc21853f75cc8c66d266c8e53eafbbcc3096244-Capture_decran_le_2025-04-02_a_09.07.34.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "70% "
    }
  ]
}
[/block]


# Events

Voiceflow will send POST requests to your webhook URL on the following events.

## `runtime.call.start`

This event is sent when the following call types are made:

- Twilio inbound / outbound / prototype-outbound call
- web widget voice call is made (including during testing on `creator.voiceflow.com`)

```typescript
{
  "type": "runtime.call.start",
  "data": {
    "userID": string,
    "projectID": string,
    "environmentID": string,
    "startTime": number, // unix timestamp MS
    "platform": "twilio" | "web-voice",
    "metadata": object // depends on "platform"
  }
  "time": number // unix timestamp MS, event time
  "resource": string // project-{projectID}
}
```

Example `runtime.call.start` event:

```json
{
  "type": "runtime.call.start",
  "data": {
    "userID": "+19876543210",
    "environmentID": "development",
    "projectID": "6772da2e485189279fa5b9da",
    "startTime": 1743563467788,
    "platform": "twilio",
    "metadata": {
      "callSid": "CA01ed76f14fee29c50f5de59400474006",
      "callType": "inbound",
      "userNumber": "+19876543210",
      "agentNumber": "+17782006110"
    }
  },
  "time": 1743563467874,
  "resource": "project-6772da2e485189279fa5b9da",
}
```

## `runtime.call.end`

This event is sent when a call is completed.

```typescript
{
  "type": "runtime.call.end",
  "data": {
    "userID": string,
    "projectID": string,
    "environmentID": string,
    "startTime": number, // unix timestamp MS
    "endTime": number, // unix timestamp MS
    "endReason"?: string | undefined, // why the call ended, arbitrary string, common reasons include "hangup" "end trace" "twiml" "answering machine"
    "platform": "twilio" | "web-voice",
    "metadata": object // depends on "platform"
  }
  "time": number // unix timestamp MS
  "resource": string // project-{projectID}
}
```

Example `runtime.call.end` event:

```json
{
  "type": "runtime.call.end",
  "data": {
    "userID": "+19876543210",
    "environmentID": "development",
    "projectID": "6772da2e485189279fa5b9da",
    "startTime": 1743563467788,
    "endTime": 1743563467834,
    "endReason": "hangup",
    "platform": "twilio",
    "metadata": {
      "callSid": "CA01ed76f14fee29c50f5de59400474006",
      "callType": "inbound",
      "userNumber": "+19876543210",
      "agentNumber": "+17782006110"
    },
    
  },
  "time": 1743563467874,
  "resource": "project-6772da2e485189279fa5b9da",
}
```

# Platform Metadata

Depending on `data.platform`, the metadata for the call will change.

### Twilio

```typescript
"platform": "twilio",
"metadata": {
  "callSid": string // twilio call sid, can be used to check twilio logs
  "callType": "inbound" | "outbound" | "prototype-outbound",
  "userNumber": string // phone number of the user
  "agentNumber": string // phone number of the agent / bot
}
```

The _to_ and _from_ number depends on the type of call.

For example, for an `"inbound"` call, from is the `userNumber` and to is the `agentNumber`, while it is the inverse for `"outbound"`.

### web-voice

No additional metadata currently. In the future, this may include browser and geographic information.

```typescript
"platform": "web-voice",
"metadata": { 
  // empty
}
```

# Best Practices

- Check `type` when evaluating response. There may be additional types of events in the future with a different shaped request body, as well as new properties and metadata.
- Check `data.platform` before evaluating `data.metadata`, for example it's possible that `data.metadata.callSid` doesn't exist because it's a `"web-voice"` call.
- You can check `data.projectID` if you want to share the same endpoint between different projects.