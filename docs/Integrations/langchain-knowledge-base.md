---
title: Custom Knowledge Base
excerpt: Use Langchain to create a custom knowledge base to use with Voiceflow
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

This code utilizes Open AI GPT, Langchain, Redis Cache, OpenSearch and Unstructured to fetch content from URLs, sitemap, PDF, Powerpoint, Notion doc and images to create embeddings/vectors and save them in a local OpenSearch database. The created collections can then be used with GPT to answer questions.

<Embed url="https://www.loom.com/share/02833f38e3a6461983a2d7c3a3a570b8" title="Langchain OpenSearch - demos-n-examples - 28 April 2023" image="https://cdn.loom.com/sessions/thumbnails/02833f38e3a6461983a2d7c3a3a570b8-00001.gif" provider="loom.com" href="https://www.loom.com/share/02833f38e3a6461983a2d7c3a3a570b8" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.loom.com%252Fembed%252F02833f38e3a6461983a2d7c3a3a570b8%26display_name%3DLoom%26url%3Dhttps%253A%252F%252Fwww.loom.com%252Fshare%252F02833f38e3a6461983a2d7c3a3a570b8%26image%3Dhttps%253A%252F%252Fcdn.loom.com%252Fsessions%252Fthumbnails%252F02833f38e3a6461983a2d7c3a3a570b8-00001.gif%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dloom%22%20scrolling%3D%22no%22%20title%3D%22Loom%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

# Instructions & Code Repository

You can find our open source code and step by step instructions on using our Dialog Manager API with it below.

[https://github.com/voiceflow-gallagan/langchain-local-knowledgebase/tree/c466af6c6818c31a5f7d131374cdd07a128182ad](https://github.com/voiceflow-gallagan/langchain-local-knowledgebase/tree/c466af6c6818c31a5f7d131374cdd07a128182ad)
