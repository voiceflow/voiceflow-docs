---
title: Advanced RAG Filtering and Tagging
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Advanced Rag Filtering and Tagging
  description: >-
    This document explains how to use Voiceflow's Knowledge Base API to create
    more powerful agents by tagging and filtering documents based on user
    feedback and LLM answers.
  image: https://files.readme.io/3237010-Subtle_Logo.png
  keywords:
    - api
    - knowledge base
    - llm
    - tags
    - voiceflow
  robots: index
next:
  description: ''
---
## Intro

Voiceflow's Knowledge Base (RAG) API allows you to use filters and tags to create more powerful agents. In this recipe, you'll learn how to:

* Use a feedback card to tags docs based on LLM answers
* Generate a new doc using “file” upload/tag with user’s question and LLM answer
* Use KB Upload API to add this newly created doc
* Use KB Query API with tags filtering
* Get the best chunk based on “validated” tag and highest score.
* Reduce token usage by avoid using LLM for validated answers
* Limit hallucinations and return same validated answers each time

## YouTube video

<Embed url="https://www.youtube.com/watch?v=hYjuZ2qnk2Y" title="Voiceflow Knowledge Base Upload and Tags API to save tokens and return validated answers." favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/hYjuZ2qnk2Y/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=hYjuZ2qnk2Y" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FhYjuZ2qnk2Y%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DhYjuZ2qnk2Y%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FhYjuZ2qnk2Y%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22640%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## Try yourself

[Try the template yourself! ](https://creator.voiceflow.com/dashboard?import=6534dc3482bc0a000636907f). Import into your project.
