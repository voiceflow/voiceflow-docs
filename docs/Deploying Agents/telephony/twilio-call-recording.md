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

<br />

## How to enable call recording

> ⚠️
>
> You are solely responsible for complying with applicable laws related to call recording and consent in your region. Voiceflow does not access, store, or manage any call recordings. All recordings are handled directly by your Twilio account. Voiceflow is not liable for any misuse of the recording feature.

1. Go to your Voiceflow project’s settings.
2. Navigate to Behaviour > Voice.
3. Scroll to the bottom and enable Call Recording.

Once enabled, Twilio will automatically handle the recording of your calls.

<br />

<Image align="center" width="60% " src="https://files.readme.io/12a9a65c66ec3816f437f4568c29bede8dea742290e4fda07bafbe247f1ebf16-image.png" />

> ❗️ Note: Call recordings are currently only supported on Twilio, and not for the voice widget.

To listen back to your call recordings, you can go to your Twilio console, and then navigate to Monitor > Logs > call recordings.

![](https://files.readme.io/b54b57640c7f6d1e99ab1b93e71afcec3ea4727e4b87a6271722f7ae8270add7-image.png)