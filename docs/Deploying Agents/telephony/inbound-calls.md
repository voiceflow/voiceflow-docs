---
title: Inbound calls
excerpt: >-
  This guide walks you through how to connect a Twilio phone number to a
  Voiceflow agent for inbound calling.
deprecated: false
hidden: true
metadata:
  robots: index
---
## Concurrency limits

Outbound calls share the same concurrency pool as outbound calls. The number of simultaneous calls you can make is [determined by your plan limits](https://voiceflow.com/pricing)

<br />

## 1. Create a Twilio Account and get credentials

1. SIgnup at [Twilio](twilio.com)
2. Claim a phone number with the free trial
3. Note your:

* Account SID
* Auth Token
* Phone Number SID

<br />

## 2. Configure Telephony in Voiceflow