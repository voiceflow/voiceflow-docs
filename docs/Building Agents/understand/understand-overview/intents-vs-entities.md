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
*What are Intents? What are Entities? How do Intents and Entities differ?*

Before we dive deeper into managing your conversation model, it's important to set a baseline understanding of the conversational components and fundamentals that will allow you to build dynamic, non-linear conversations.

This can be best explained with a conceptual example: “What cake do I buy for my birthday?”

On analyzing the above statement, we can understand two basic things:

* The person is interested in buying a cake
* The occasion is a birthday

The former is the **Intent**, the latter, an **Entity**.‍ These are the building blocks for most conversation queries.

Now, imagine you run a bakery, you might not just be selling cakes; you might also sell muffins, cookies, breads, and much more. In that case, you would want to add two or more **Entities** with the **Intent** of buying.

![](https://files.readme.io/27c39d4-image.png)

In the graphic above, we can understand that the user’s intention is to access the weather.

To break it down further, let’s define a few terms.

* **Intent** — Intention, or purpose of the user in the conversational flow
* **Entity** — A data point or value which you can extract from a conversation (and can be slotted into a category/type)
* **Utterance** — The input(s)/response that your end-users provide to your conversational experience

Your conversational interface will derive intents and entities from utterances.

The difference between an **Intent** and **Entity** is that the intent is the goal that your user has when they’re sending a message to your conversational experience, while the entity is the modifier that your user makes use of to describe their query.

Alternatively, the **Intent** is an action that the user wants to perform, and the **Entity** is a keyword that you want to be extracted from the user’s utterance.

The **Trigger** step (which used to be known as the intent step) can be used to jump around workflows and through the conversation flow when intents are uttered by users. You can learn more about it [here](https://developer.voiceflow.com/v2.0/docs/trigger).

Therefore, while developing and designing a flexible and dynamic conversation, user/customer intents and entity recognition is crucial.

<Embed url="https://www.youtube.com/watch?v=EjvLSO4we40" title="Capturing and Manipulating Information with Entities, Logic, and Intents" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/EjvLSO4we40/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=EjvLSO4we40" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FEjvLSO4we40%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DEjvLSO4we40%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FEjvLSO4we40%252Fhqdefault.jpg%26key%3D02466f963b9b4bb8845a05b53d3235d7%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />
