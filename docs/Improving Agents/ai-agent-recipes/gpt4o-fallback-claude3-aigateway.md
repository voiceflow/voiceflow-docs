---
title: GPT-4o with fallback to Claude 3 Sonnet
excerpt: ''
deprecated: true
hidden: true
metadata:
  title: GPT-4o with fallback to Claude 3 Sonnet
  description: >-
    This document provides a tutorial on creating a fallback mechanism that
    switches from OpenAI's GPT-4o to Anthropic's Claude 3 Sonnet for
    uninterrupted service during outages, aimed at developers and conversational
    AI enthusiasts. You can find more information and import the Voiceflow agent
    from the provided links.
  image: https://files.readme.io/4f0cb22-Subtle_Logo.png
  keywords:
    - gpt-4o
    - claude
    - sonnet
    - anthropic
    - fallback
    - llm
    - cloudflare
    - ai gateway
    - voiceflow
  robots: index
next:
  description: ''
---
## Intro

In this tutorial you will learn how to create an intelligent fallback mechanism that seamlessly switches from OpenAI's GPT-4o to Anthropic's Claude 3 Sonnet, ensuring uninterrupted service even during outages. This step-by-step guide is designed for developers and conversational AI enthusiasts aiming to enhance the reliability and performance of their AI agents.

Cloudflare AI Gateway doc:\
[https://developers.cloudflare.com/ai-gateway](https://developers.cloudflare.com/ai-gateway)

You can import the Voiceflow agent from this link:\
[https://creator.voiceflow.com/dashboard?import=66436ed6153640657231d699](https://creator.voiceflow.com/dashboard?import=66436ed6153640657231d699)

## Video

<Embed url="https://www.youtube.com/watch?v=qu6lJjOlTmw" title="Create a Seamless Fallback from OpenAI GPT-4o to Anthropic Claude 3 Sonnet in your Voiceflow agent" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/qu6lJjOlTmw/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=qu6lJjOlTmw" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252Fqu6lJjOlTmw%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253Dqu6lJjOlTmw%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252Fqu6lJjOlTmw%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22640%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />