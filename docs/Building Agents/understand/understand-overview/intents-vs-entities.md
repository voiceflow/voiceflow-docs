---
title: Intents vs Entities
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
_What are Intents? What are Entities? How do Intents and Entities differ?_

Before we dive deeper into managing your conversation model, it's important to set a baseline understanding of the conversational components and fundamentals that will allow you to build dynamic, non-linear conversations.

This can be best explained with a conceptual example: “What cake do I buy for my birthday?”

On analyzing the above statement, we can understand two basic things:

- The person is interested in buying a cake
- The occasion is a birthday

The former is the **Intent**, the latter, an **Entity**.‍ These are the building blocks for most conversation queries.

Now, imagine you run a bakery, you might not just be selling cakes; you might also sell muffins, cookies, breads, and much more. In that case, you would want to add two or more **Entities** with the **Intent** of buying.

![](https://files.readme.io/27c39d4-image.png)

In the graphic above, we can understand that the user’s intention is to access the weather.

To break it down further, let’s define a few terms.

- **Intent** — Intention, or purpose of the user in the conversational flow
- **Entity** — A data point or value which you can extract from a conversation (and can be slotted into a category/type)
- **Utterance** — The input(s)/response that your end-users provide to your conversational experience

Your conversational interface will derive intents and entities from utterances.

The difference between an **Intent** and **Entity** is that the intent is the goal that your user has when they’re sending a message to your conversational experience, while the entity is the modifier that your user makes use of to describe their query.

Alternatively, the **Intent** is an action that the user wants to perform, and the **Entity** is a keyword that you want to be extracted from the user’s utterance.

The **Trigger** step (which used to be known as the intent step) can be used to jump around workflows and through the conversation flow when intents are uttered by users. You can learn more about it [here](https://developer.voiceflow.com/v2.0/docs/trigger).

Therefore, while developing and designing a flexible and dynamic conversation, user/customer intents and entity recognition is crucial.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FEjvLSO4we40%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DEjvLSO4we40&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FEjvLSO4we40%2Fhqdefault.jpg&key=02466f963b9b4bb8845a05b53d3235d7&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=EjvLSO4we40",
  "title": "Capturing and Manipulating Information with Entities, Logic, and Intents",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/EjvLSO4we40/hqdefault.jpg",
  "provider": "https://www.youtube.com/",
  "href": "https://www.youtube.com/watch?v=EjvLSO4we40",
  "typeOfEmbed": "youtube"
}
[/block]