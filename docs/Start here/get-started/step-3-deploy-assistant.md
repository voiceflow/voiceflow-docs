---
title: 'Step 3: Deploy Assistant'
excerpt: >-
  You can use our quick launch deployments to launch in <1 minute or our code
  samples for a more flexible integration
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
There are two ways to launch an assistant

1. **Quick Launch**: Use our built-in integrations to launch to a website, SMS, WhatsApp, or Microsoft Teams. These are fast but limited in customization.
2. **Custom Launch**: Use our code samples to launch an assistant for channels like slack, discord, IVR, Telegram, and more. These allow you to create your own customizations with code.

## **Quick Launch**

On an AI project, click the integrations tab for the various quick launch instructions and settings. Details instructions on each channel are included below. We only support chat based channels on quick launch currently.

- [Webchat](https://developer.voiceflow.com/docs/chat-widget)
- [Whatsapp](https://developer.voiceflow.com/docs/whatsapp)
- [Twilio SMS](https://developer.voiceflow.com/docs/twilio-sms)
- [Microsoft Teams](https://developer.voiceflow.com/docs/microsoft-teams)

![](https://files.readme.io/fbfa13a-CleanShot_2023-07-14_at_15.52.26.png)



## **Custom Launch**

Our code samples can be found in the **custom launch section** of the docs or on github [here](https://github.com/voiceflow/demos-n-examples). These are starting points that help you understand how to connect with various voice and chat channels.

All of our code samples leverage our Dialog API. This API send input to your Voiceflow project and returns a response based on the design.

It also manages the state of the users conversation, letting them leave the conversation then pick it up later from the same spot.

There are 3 key requests you will use

1. [Interact Launch Request](https://developer.voiceflow.com/reference/stateinteract-1): This starts the conversation from the start block.
2. [Interact Text Request](https://developer.voiceflow.com/reference/stateinteract-1): This sends text input to Voiceflow and returns a response. Use this after the Launch request.
3. [Delete State](https://developer.voiceflow.com/reference/deletestate-1): This force ends the conversation and resets the state.

You can do other functions like set variables in Voiceflow with the [Update Variable](https://developer.voiceflow.com/reference/updatestatevariables-1) endpoint. This is useful for things like authentication and passing user information.