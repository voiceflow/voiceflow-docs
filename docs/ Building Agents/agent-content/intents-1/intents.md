---
title: Introduction to Intents
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
## What Are Intents?

In the realm of conversational AI, **intents** represent the underlying goals or purposes behind a user's input. They are the actions the user wants to perform or the information they seek through their queries. By identifying intents, your Voiceflow agent can understand what the user is trying to achieve and respond appropriately.

<Embed url="https://www.youtube.com/watch?v=SkEakBxkE8w" href="https://www.youtube.com/watch?v=SkEakBxkE8w" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FSkEakBxkE8w%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DSkEakBxkE8w%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FSkEakBxkE8w%252Fhqdefault.jpg%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" providerUrl="https://www.youtube.com/" providerName="YouTube" />

<br />

## The Role of Intents in Agent Design

Intents are foundational elements in designing conversational agents because they:

* **Guide Conversation Flow**: Help determine the next steps in the conversation based on user input.
* **Enhance Understanding**: Enable the agent to interpret user messages accurately, even if phrased differently.
* **Improve User Experience**: Allow for more natural and efficient interactions by anticipating user needs.

## How Intents Work in Voiceflow

In Voiceflow, intents can either be defined within the **Intent CMS** or certain steps under the **Listen section**. Each intent includes:

* **Name**: A clear identifier for the intent (e.g., `BookAppointment`).
* **Description**: A brief explanation of when the intent should be triggered.
* **Utterances**: Example phrases users might say to invoke the intent.
* **Required Entities** (optional): Specific pieces of information required in prior to fulfill the intent.

<Image align="center" width="35% " src="https://files.readme.io/29f4acbb8d4b909e72a471e8c4a1e3a2bbb09ee9726a661c2601683362c9bb72-CleanShot_2025-07-14_at_11.30.562x.png" />

<br />

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

## Intents vs. Entities

While **intents** capture the user's goal, **entities** represent specific pieces of information within the user's input that are necessary to fulfill that intent. For example:

* **Intent**: `showWeather`
* **Entities**: `Date`, `City`

![](https://files.readme.io/0c8fa062c4cc691148161ddccbb1b2e34ae3790a545ae1b0bae031a4e3d7cf01-image.png)

Understanding the distinction between intents and entities is crucial for designing effective conversational agents. Intents determine **what** the user wants to do, and entities provide the details needed to complete that action.

## Benefits of Using Intents

* **Simplifies Design**: Organizing user goals into intents streamlines the conversation design process.
* **Enhances Scalability**: New functionalities can be added by introducing new intents without overhauling existing structures.
* **Facilitates Maintenance**: Clear intent definitions make it easier to update and manage the agent over time.