---
title: Managing interuptions
excerpt: Humans might talk over your agent. Here's how to handle that.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Voiceflow voice agents operate on a turn-by-turn model. At any given moment, the user is at a specific state in the conversation, which is tied to a step in the workflow (e.g. a [message step](doc:message), [capture step](doc:capture-v2), or [API step](doc:api-step)).

During voice interactions, users may interrupt the agent while it's speaking. Handling these interruptions correctly is important for maintaining a natural and functional experience.

## Voice Interruption

### Interruption Threshold

The first setting is **Interruption Threshold** which is the number of words before the agent will stop talking. The Automatic Speech Recognition (ASR) is always running and will have "partial" transcriptions.

*The agent will still be running in the background*, but will no longer talk over the user.

### Full Interruption

A full interruption is when an **full utterance** is resolved by the ASR, and the next turn begins before the previous one ends. A utterance is determined by the other Telephony settings such as *Silence Wait*, *Utterance End*, *Punctuation Wait*, etc.

## Interruption State

Reference the sample agent below. After the user says something, there are a series of simple message steps broken up by long running API / Prompt steps.

<Image align="center" src="https://files.readme.io/e11c3fae9ec0ccc46daa6855306f8821c80060d93a8d857491385fa27dd8f280-Capture_decran_le_2024-12-20_a_11.46.34.png" />

Message steps are always nearly instanteous, but other steps (API, Functions, Prompts) are blocking and take some time before we can proceed.

When an interruption happens, as the previous turn hasn't made it to **"next state"**, we will always start at the capture step under **"starting point"**.

The previous turn will also stop executing. For example if the interruption happened during "*GET - long API call"*, it will no longer call *"long LLM prompt"* and use up tokens in the background.

If the previous turn has made it to **"next state"**, we are no longer interrupting, but rather just starting the next turn normally.

> 📘 Audio does not represent current state
>
> What the agent is speaking to the user has a slight delay and the actual state of the conversation is likely ahead of the speech (speech is buffered).
>
> For example when we hit "message 1":
>
> 1. "*GET - long API call"* is next and starts running (background task).
> 2. generate the Text-to-Speech audio
> 3. play the audio, this takes even longer
>
> <Image align="center" src="https://files.readme.io/909ddd22690f4e66d5e04126f15e6567068d5bb1de016fe2b7b298d128e567a2-Capture_decran_le_2024-12-20_a_12.20.31.png" />
>
> In the current example, the API step has already started the call by the time the first message is speaking.
>
> By the time "message 3 / last message" is speaking, the turn is done and the user already is on **"next state"**.
>
> This is done for maximum latency gains during voice conversations - and minimize awkward silences, but can be hard to debug.