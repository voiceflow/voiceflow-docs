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

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2F9QazOTPrzmA%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D9QazOTPrzmA&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2F9QazOTPrzmA%2Fhqdefault.jpg&key=02466f963b9b4bb8845a05b53d3235d7&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=9QazOTPrzmA",
  "title": "Optimizing Your AI Agents Triggers [Part 3.1 Support Course]",
  "favicon": "https://www.youtube.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/9QazOTPrzmA/hqdefault.jpg",
  "provider": "https://www.youtube.com/",
  "href": "https://www.youtube.com/watch?v=9QazOTPrzmA",
  "typeOfEmbed": "youtube"
}
[/block]


<br />

## The Role of Intents in Agent Design

Intents are foundational elements in designing conversational agents because they:

- **Guide Conversation Flow**: Help determine the next steps in the conversation based on user input.
- **Enhance Understanding**: Enable the agent to interpret user messages accurately, even if phrased differently.
- **Improve User Experience**: Allow for more natural and efficient interactions by anticipating user needs.

## How Intents Work in Voiceflow

In Voiceflow, intents are defined within the **Intent CMS**. Each intent includes:

- **Name**: A clear identifier for the intent (e.g., `BookAppointment`).
- **Description**: A brief explanation of when the intent should be triggered.
- **Utterances**: Example phrases users might say to invoke the intent.
- **Required Entities** (optional): Specific pieces of information needed to fulfill the intent.

Intents are utilized in various steps within Voiceflow, such as:

- **Choice Step**: To branch the conversation based on different user intents.
- **Button Step**: To provide clickable options that trigger intents.
- **Trigger Step**: To jump to different parts of the conversation when certain intents are recognized.

## Intents vs. Entities

While **intents** capture the user's goal, **entities** represent specific pieces of information within the user's input that are necessary to fulfill that intent. For example:

- **Intent**: `showWeather`
- **Entities**: `Date`, `City`

![](https://files.readme.io/0c8fa062c4cc691148161ddccbb1b2e34ae3790a545ae1b0bae031a4e3d7cf01-image.png)

Understanding the distinction between intents and entities is crucial for designing effective conversational agents. Intents determine **what** the user wants to do, and entities provide the details needed to complete that action.

## Benefits of Using Intents

- **Simplifies Design**: Organizing user goals into intents streamlines the conversation design process.
- **Enhances Scalability**: New functionalities can be added by introducing new intents without overhauling existing structures.
- **Facilitates Maintenance**: Clear intent definitions make it easier to update and manage the agent over time.