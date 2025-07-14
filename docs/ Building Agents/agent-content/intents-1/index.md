---
title: Intents
excerpt: Route conversation and decisions based on user input.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  pages:
    - title: Watch our Intents video on YouTube
      type: link
      url: https://www.youtube.com/watch?v=SkEakBxkE8w
---
## What are Intents?

Intents help route a conversation based on what the user means, not just what they say. The user's input doesn’t need to exactly match the Intent - instead, the agent will match user input to an Intent based on the underlying meaning of the message.

Intents are supported in the following places:

* The [Choice step](doc:choice-v2)
* The [Button step](doc:buttons-v2)
* Globally using [Triggers](doc:trigger)

<br />

> ℹ️ The Agent step doesn't use Intents.
>
> Modern AI agents can be built without using Intents, and instead through the [Agent step](doc:agents). Features such as prompting and exit conditions allow you to replicate similar behaviour to Intents without needing to manually create an Intent.

<br />

## How to create Intents

Intents can either be defined within the [CMS](doc:cms) or through the [Choice step](doc:choice-v2) and [Button step](doc:buttons-v2). Each intent includes the following things:

* **Name**: A clear identifier for the intent (e.g., `BookAppointment`).
* **Description**: A brief explanation of when the intent should be triggered.
* **Utterances**: Example phrases users might say to invoke the intent.
* **Required Entities** (optional): Specific pieces of information required in prior to fulfill the intent.

<Image align="center" src="https://files.readme.io/35e3c6fee828adf56873325c232f6556a39cb31e0a4a26d3da207fd80dba5252-Frame_48095773.png" />

## Using intents

Intents are utilized in various steps within Voiceflow, such as:

<Tabs>
  <Tab title="Choice Step">
    <h3>Choice Step</h3>
    To branch the conversation based on different user intents.

    <Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSzTDGRDyQXUw9e3lryuWbOH7E5ApCIBaitDYK" />
  </Tab>

  <Tab title="Trigger Step">
    <h3>Trigger Step</h3>
    To jump to different parts of the conversations with triggers when certain intents are recognized.

    <Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSvFUFY1xoDVQXmAUr9uGNzwaYSd78tfRT6F1x" />
  </Tab>

  <Tab title="Button Step">
    <h3>Button Step</h3>
    To provide clickable options that invoke triggers when certain intents are recognized.

    <Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NS2ezL43gQD9nLFZ4JORio7WdbTegAGUcvxfw6" />
  </Tab>
</Tabs>