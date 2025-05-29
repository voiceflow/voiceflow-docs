---
title: Call recording
excerpt: Monitor your agent's calls and measure quality.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Voiceflow supports call recording for Twilio-powered voice experiences, including both inbound and outbound calls. This feature allows you to automatically record conversations handled through your Voiceflow agent when connected via Twilio, enabling quality assurance and compliance check workflows.

## Enabling and disabling call recording

> ⚠️
>
> You are solely responsible for complying with applicable laws related to call recording and consent in your region. Voiceflow does not access, store, or manage any call recordings. All recordings are handled directly by your Twilio account. Voiceflow is not liable for any misuse of the recording feature.

<br />

Call recording can be enabled by opening the settings tab of your agent, opening **Behaviour** settings, then selecting **Voice**. The **save call recordings** toggle can be found bottom of this page.

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSq73XJyBe98Elmq4kxJ1Vv0CSoXDObGzif7WU" />

<br />

## Listening to call recordings

Calls can be listened to from your [Twilio console](https://console.twilio.com/). Login to your Twilio account, then navigate to **Monitor > Logs > Call recordings** to listen to recordings.

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSKowMrczNIhSvxwGVX58OPtY0fWsCKNQblBjr" />

<br />

## Limitations

Please note that only calls routed through a phone number are able to be recorded. Voice calls over the web (for example, through the [web chat widget](doc:chat-widget) cannot be recorded at this time.