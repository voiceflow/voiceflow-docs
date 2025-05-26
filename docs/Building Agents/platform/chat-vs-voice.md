---
title: Chat vs Voice agents
excerpt: Choosing a Text or Voice agent in Voiceflow
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Currently, in Voiceflow you have two types of agents that you can build.

1. **Chat**: Most versatile, intended to be used natively with our built-in [Web Chat](https://developer.voiceflow.com/v2.0/docs/web-chat-overview) or to a custom interface with our [Dialog API](https://developer.voiceflow.com/v2.0/reference/overview). Contains everything you need for a visual interface like buttons, images, and more.
2. **Voice**: Is more limited. Intended to be used exclusively with our [Dialog API](https://developer.voiceflow.com/v2.0/reference/overview) to connect to a custom voice interface. This type features a few voice specific features like a [speak step with SSML](https://developer.voiceflow.com/v2.0/docs/speak) and an [audio step](https://developer.voiceflow.com/v2.0/docs/audio) to stream audio from a file. Since Voice comes from the days of Amazon Alexa, you'll have to provide your own speech to text and text to speech solutions with [Twilio IVR](https://developer.voiceflow.com/v2.0/docs/twilio-voice) for example.

<Image align="center" width="500px" src="https://files.readme.io/fcf949c-CleanShot_2024-06-10_at_13.50.222x.png" />

For most use cases, **we recommend using the Chat project,** as it has the most versatile set of features and capabilities that you can use.
