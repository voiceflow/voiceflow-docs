---
title: Evaluations
excerpt: >-
  Evaluations are a set of custom criteria you can define to determine whether
  specific events occurred during a conversation—based on the transcript data.
deprecated: false
hidden: true
metadata:
  robots: index
---
Evaluations are custom, automated checks that run against [Transcripts](). They allow you to detect whether specific events, phrases, or intents occurred during a conversation—making it easier to measure quality, compliance, and outcomes from your agent's interactions at scale.

> You might use Evaluations to check if:
>
> * The user expressed satisfaction or frustration during their conversation.
> * The agent responded with a specific confirmation (e.g. “I’ve uploaded that for you”).
> * The agent avoided restricted terms or phrases.

Evaluations run automatically on transcripts and surface pass/fail results or other structured outputs directly in the transcript view.

> 📌 Evaluations consume credits!
>
> Each evaluation consumes credits based on the number of transcripts processed, the length of each transcript and the model selected.

## Creating evaluations

\[ video of navigating from workflow to evaluations ]

Evaluations can be created in the **Measure** section of Voiceflow creator. Evaluations can return three types of results: **binary**, **text** or **rating**. Binary results provide a simple yes/no outcome—useful for checking whether a specific event occurred—while text results return a freeform string, often used for summaries, labels, or more descriptive feedback. Rating results provide a numerical value between a given range.

<Image align="center" src="https://files.readme.io/c60990cf4ac882cf5f650d59a7cb92a8b7fb6647fc7ca1b03b53de62ea10da05-CleanShot_2025-07-23_at_12.12.172x.png" />

Evaluations can be created either from scratch or by using a predefined template. Templates provide a quick starting point for common use cases and can be customized.

To save time, you can use the **⚡ icon** to automatically generate an evaluation based on a short description or instruction. This allows you to quickly create evaluation criteria without writing a detailed prompt from scratch.

To preview or test out an evaluation with your agent, you can click on **Test on transcript**.

## Enabling and disabling evaluations

Once an evaluation is created, it is **automatically** enabled by default. This means it will be run on all future transcripts that meet the evaluation's conditions.

If you want to *disable* an evaluation, simply click into the evaluation and toggle the **On/Off** switch. This stops the evaluation from running on new transcripts, while keeping existing results intact.

You can also identify the status of an evaluation at a glance:

\[ insert picture ]

* **Enabled** evaluations are marked with a green bar on the left side of the row.
* **Disabled** evaluations display a grey bar instead.

This quick visual indicator makes it easy to scan and manage which evaluations are currently active in your project.

## Measuring evaluation performance

go to transcripts

show where evals are with hover

if transcript is clicked on you can see if evals were successful on the sidebar

## Batch run on transcripts