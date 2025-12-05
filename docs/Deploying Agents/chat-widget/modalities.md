---
title: Modalities
excerpt: Embed text or voice conversational agents on the web.
deprecated: false
hidden: false
metadata:
  robots: index
---
Depending on your use-case, you might want to build text or voice-based conversational agents and embed them onto your website. For example:

* A **law firm** may wish to have a text-only agent to ensure that all details collected are exactly what the user inputted, and not subject to text-to-speech transcriptions.
* An **online fashion store** might use the text modality with certain voice features enabled, allowing users to have voice conversations with an agent while also allowing for [cards](doc:cards-tool) promoting products to be shown during the conversation.
* A **car rental company** might embed a voice-only widget into their app, allowing customers from outside their home country to call customer support while driving without incurring international call charges.

Voiceflow's chat widget supports all of these options.

<br />

## Setting your modality

To set your web chat widget's modality, open the widget settings by pressing the **Interfaces** button on your canvas' sidebar then clicking **Interfaces**.

<Image align="center" border={false} src="https://files.readme.io/4642be086623ea0872af9fe87480df0446906474e77b8504183964f5adcd520b-Frame_48095762.png" />

<br />

## Chat modality

The chat modality is the default version of the web chat widget. When enabled, users can type messages your agent, and will see the agent's responses as text. Most people building for the web use the chat modality.

When building with the chat modality, you can also optionally enable voice-focused features. These are:

* **Dictation** - allows your agent's users to input text using speech-to-text.
* **Voice output** - allows your agent's users to hear your agent's responses using the text-to-speech model set in your project's settings.
* **Voice mode** - when enabled, this setting allows conversations to take place hands-free. Once the user presses the blue "voice" button in the message input (shown below), they will be able to talk to the agent for the rest of the conversation without pressing it again, similar to a phone call. If this option is disabled, the user must press the microphone button each time before saying their message.

<br />

<Callout icon="ℹ️" theme="info">
  Voice related features, such as speech-to-text and text-to-speech consume credits. [Learn more about credits](doc:credits).
</Callout>

<Image align="center" border={false} src="https://files.readme.io/a562d6bf8c6fc102f853d53b543789a16d01d5565aa13bf71add1af638cbba5d-Frame_48095764.png" />

<br />

## Voice modality

When the voice modality is enabled, the conversation will act similarly to a phone call. This means that the conversation's message history will not be shown to the user, and the user will not need to press a button to send their message. However, the written message history will be saved in the conversation's transcript.

When voice mode is enabled, the user can also interrupt the agent by speaking at the same time as it.

<Image align="center" border={false} src="https://files.readme.io/4f5f822e92e831ac79a9b70842e7f8a69b4ec37a7019feafc7fd6e5800d4700a-Frame_48095763.png" />

<br />
