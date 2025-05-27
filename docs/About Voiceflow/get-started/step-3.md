---
title: 'Step 3: Deploy your agent'
excerpt: >-
  You can use our quick launch Web Chat code snippet to launch a simple agent in
  <1 minute, or our react-chat project or APIs for a more flexible integration.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
There are two main ways to launch a Voiceflow <Glossary>agent</Glossary>:

1. **Quick Launch**: Use our Web Chat JavaScript installation code snippet to embed the Web Chat widget on your website.
2. **Custom Launch**: Use our open-source projects and APIs to create your own customizations with code.

## **Quick Launch**

On an AI agent, click the integrations tab for the Web Chat quick launch instructions and settings. We only support chat based channels on quick launch currently.

* [Web Chat settings and API options](https://developer.voiceflow.com/docs/chat-widget)

![](https://files.readme.io/280cb53-CleanShot_2024-06-19_at_16.33.212x.png)

## **Custom Launch**

Use our open-source Web Chat project to further customize the chat widget experience or the [Dialog Manager API](https://developer.voiceflow.com/reference/overview) to integrate your Voiceflow <Glossary>agent</Glossary> with an interface of your choice. (Note: a custom launch solution requires the ability to host and maintain code on your own infrastructure.)

### Customize the Web Chat experience

You can leverage our open-source Web Chat project (called “react-chat”) to customize your own version of the Web Chat widget. See our [Customizing Web Chat guide](https://developer.voiceflow.com/docs/advanced-webchat) to learn more.

### Integrate with a channel or custom interface

You can integrate your Voiceflow agent into your channels and custom interfaces by leveraging our [Dialog Manager API](https://developer.voiceflow.com/reference/overview):

* See  the Integrations section for starter integration code samples for [text-based interfaces](https://developer.voiceflow.com/docs/text-based-interfaces) like WhatsApp and Discord and [voice-based interfaces](https://developer.voiceflow.com/docs/voice-based-interfaces) like Twilio IVR. Our code samples can also be found on GitHub [here](https://github.com/voiceflow/demos-n-examples).
  * These code samples are starting points that can help you understand how to connect the Dialog Manager API with various channels; they are not meant to be deployed as-is into your production environment.
* The [Dialog Manager API](https://developer.voiceflow.com/reference/overview) can be used to send input to your Voiceflow <Glossary>agent</Glossary> and fetch a response based on your design. This API can also manage the state of your user's conversation, letting them leave the conversation, then pick it up later from the same spot.
* There are 3 key [Dialog Manager API](https://developer.voiceflow.com/reference/overview) requests that you will use
  * [Interact Launch Request](https://developer.voiceflow.com/reference/stateinteract-1): This starts the conversation from the start block.
  * [Interact Text Request](https://developer.voiceflow.com/reference/stateinteract-1): This sends text input to Voiceflow and returns a response. Use this after the Launch request.
  * [Delete State](https://developer.voiceflow.com/reference/deletestate-1): This force ends the conversation and resets the state.
* You can do other functions like set variables in Voiceflow with the [Update Variable](https://developer.voiceflow.com/reference/updatestatevariables-1) endpoint. This is useful for things like authentication and passing user information.
