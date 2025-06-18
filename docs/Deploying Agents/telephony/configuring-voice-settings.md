---
title: Configuring voice settings
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Overview

The Voice settings allow you to fine-tune the behaviour of your voice agents during voice calls. By adjusting parameters like silence timeouts, audio cues, and ASR/TTS settings, you can make conversations more organic and enhance the caller experience. This guide will walk you through the available options and how to configure them for your voice agent.

<Image align="center" width="80% " src="https://files.readme.io/47c70a1be0d3c9139622f708681f8ad91a62e665c23271cb133b18115f2493c1-Capture_decran_le_2025-06-18_a_11.59.52.png" />

## Getting Started

To access the Voice behavior settings for your agent:

1. Navigate to your project.
2. Navigate to the *Settings* > *Behaviour* tab.
3. Select the *Voice* tab.

You'll see several settings that control different aspects of the voice interaction.

## Key Concepts

* **Voice Output**: Also referred to as Text-to-Speech (TTS). Determines the voice and speech patterns of the agent speaking back to the user.
* **Voice Input**: Also referred to as Speech-to-Text (STT). Determines how we capture user speech for the agent to understand.
* **Audio Cue**: A short sound effect played to the caller to signal that the agent has received their input and is processing it.
* **Background Audio:**: Simulated background audio that helps give more realism to the call

## Voice Input

### Deepgram

As a user speaks, the **Speech-to-Text (STT)** engine continuously transcribes the audio into words, by breaking the streamed audio into "chunks".

For example, while I say "I want 2 turtles", this is what is happening in the background as I speak:

> I want...
>
> I want to...
>
> I want to turtles...
>
> I want 2 turtles. *(finalized chunk)*

If the user takes a significant pause, it will also create a *chunk*, even if the sentence looks incomplete.\
In the following example, two separate chunks are created.

> Hi...
>
> Hi, my name is... *(pause)*
>
> Hi, my name is *(finalized chunk)*
>
> ...
>
> Joe *(finalized chunk)*

#### Endpointing

**Endpointing** uses silence to detect when to finalize a *chunk*. A shorter period means faster latency. For example if I say:

> That's awesome!

We will wait the **Endpointing** period before deciding to finalize the chunk. If your **Endpointing** is 1 second, that adds up to 1 second of latency to resolving any response.

In environments with loud background noises, **Endpointing** doesn't work well because there isn’t actually a period of silence. That means we will often fall back on other methods to finalize a transcript (like timeouts), this can cause additional latency. You can learn more [here](https://developers.deepgram.com/docs/endpointing).

#### Punctuation/No Punctuation Timeout

**After** a finalized *chunk* is produced, we sometimes want to give the user a chance to continue speaking to form a complete utterance for your agent to process.

Users can often speak in run-on sentences, take long pauses, or try to make corrections.

> 1. Hey my name is
> 2. Joe.
> 3. And I live in
> 4. New York,
> 5. Manhattan actually.

Lines 2, 5 trigger **Punctuation Timeout**\
Lines 1, 3, 4 trigger **No Punctuation Timeout**

If the most recent chunk ends in punctuation (!.?¡¿…), it will wait **Punctuation Timeout** seconds for the user to say something else before assuming the user is finished speaking, and processing the turn. This is usually when a user says a complete sentence.

If the most recent chunk does not end in punctuation, it will wait for **No Punctuation Timeout** seconds. This is often when the user takes a pause during the middle of a sentence (if they're thinking for example, or pulling up some details).

The STT engine is generally pretty good at determining punctuation based on intonation and other cues, so should be taken as the primary cue for if the user is done speaking.

**No Punctuation Timeout** should always be significantly higher than **Punctuation Timeout** seconds.

#### Recommendations

Voiceflow provides default settings under the "Simplified" tab, with three options for "Speed" (optimized for quickly replying to users), "Balanced", and "Accuracy" (optimized for high conversational accuracy, at the cost of agent speed).

If you wish to customize further, you can switch to the "Advanced" tab:

* **Punctuation Timeout** and **No Punctuation Timeout** are the main levers to prevent broken up utterances.
* Keep **Endpointing** low (\~100ms) as long as the transcriptions are accurate - the words produced are what the user actually said. This helps transcribe audio as soon as possible, leading to better interruptions. The latency of your agent to respond to a spoken utterance will be *at least* the endpointing time.
* Start with longer timeout values (3-5 seconds) and gradually reduce them while monitoring the impact on call quality. Timeouts that are too short can lead to the agent interrupting the caller, and generally having to wait a second or two more for the transcription to be finalized is a nicer user experience than being missheard.
* Keep **Punctuation Timeout** low, (less than 300ms) if you expect your users to speak simple *single* sentences. If you’re expecting your users to have more organic and natural conversations with your agent, then it might make sense to increase the punctuation time to 1-2 seconds. This will give the impression of a patient agent listening carefully and really waiting for the user to be done.
* Keep **No Punctuation Timeout** higher than your Punctuation Timeout, last *least* 1 second, but often more like 3 seconds, to give users more time to complete their thoughts. *Tip: think about how long you would wait to speak if you're having a conversation with someone on the phone, and they just stop mid-sentence. From our research, it's probably more like 3+ seconds.*

In an advanced implementation, it is possible to change the settings on-the-fly during the call, depending on the use case. [Reference](https://docs.voiceflow.com/docs/advanced-using-custom-voice-actions#update-asr-settings-mid-call)

### Broken Up Utterances

If your transcription settings lead the ASR engine to think that a user is done their utterance, but they're actually not, that might lead to a **broken up utterance**.

For example, if a user says

> User: Hi my name is John (silence) Doe from New York

The agent might think that they were done speaking after John. The agent would then respond, while John keeps speaking.

> User: Hi my name is John
>
> Agent: sorry I don't think...
>
> User: Doe from New York.

In general, you'll want to avoid having broken up utterances in the first place, because they break up the user experience. Consider making your Timeout settings less aggressive and more patient.

Voiceflow does have backup handling for this: joining broken up utterances. If a second utterance continues within 3 seconds of one utterance finishing, we'll assume that those utterances should be joined.

Going back to our John Doe example, after the user is finished their sentence (assuming the silence was less than 3 seconds), `{last_utterance}` will actually be `Hi my name is John Doe from New York.`. Similarly, `{vf_memory}` variable will store this as one single utterance.

> 🚧 A warning about Broken Up Uttereances
>
> Even though the utterances will be joined together, the agent will have still received the first, partial, utterance. That means that it might have moved on inside the conversational flow (to a later step or stopping point), which could include updating variables or making external API calls, **whose state will not be rolled back**. It's just taken as if the user had actually said:
>
> > User: Hi my name is John
> >
> > Agent: sorry I don't think...
> >
> > User: *Hi my name is John* Doe from New York.
>
> For this reason, we recommend not having broken up utterances in the first place by adjusting your settings. These broken up utterances are also less of a problem for LLM-first steps, where they generally understand what's going on.

## Transcription Languages

Our Automatic Speech Recognition (ASR) engine can only understand a single language at once, and it needs to know which language to expect in advance.

You can set the transcription language from a dropdown in Settings > Behaviour > Voice.

![](https://files.readme.io/e16de14ed33422e7ee44e1c260ee4cffb7d49f2665b92a675723ea850f0e4ce9-image.png)

If you try to speak a different language than the ASR's settings, it will either miss transcribe what's being said, or not transcribe anything at all. It could look like the agent isn't hearing you at all.

If you want to support multiple languages on Twilio, you can use a DTMF menu to get a numeric input from the user to choose a language, or even have multiple different agents, each with their own phone number for each language (see Voice Custom Actions guide).

## How To

### Set an Audio Cue

1. Navigate to the Audio Cue setting.
2. Click the drop-down menu and select one of the preset sound effects. Hear a preview of the cue by selecting the play button in the dropdown.
3. Test the audio cue by calling your agent and hearing it play after you finish speaking.

<Image align="center" width="50% " src="https://files.readme.io/8b0f4b568d0cbf60ec08f02f49fd8466d02c438b586eb5ce35fb94d4e6409e89-CleanShot_2024-12-02_at_11.51.42.png" />

### Select TTS Voice

1. Navigate to Settings > Behavior > Voice
2. Choose your TTS provider (ElevenLabs, Rime, Google, Amazon, Microsoft) from the top tab selector. Different providers are more or less expensive.
3. For each provider, you can hear what a voice sounds like by pressing the play button, and then select it by clicking on the voice name.
4. Test the voice by calling your agent and listening to its responses.

Explore the variety of TTS voices to find one that callers find natural and engaging to interact with. Don't be afraid to experiment with different options.

![](https://files.readme.io/b9ee5842b4f918981c1fc77d826c99d26efb3601d0e8539973d0518a6ef157fe-image_3.png)

## Troubleshooting

### Agent is Interrupting Caller

* Increase the (ASR) Silence Wait and (ASR) Utterance End timeout values to give callers more time to start and complete their statements.
* Make sure your agent prompts are worded clearly to elicit succinct responses from callers. Open-ended or ambiguous prompts may encourage rambling.