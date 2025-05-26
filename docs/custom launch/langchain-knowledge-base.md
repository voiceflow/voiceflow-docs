---
title: Custom Knowledge Base
excerpt: Use Langchain to create a custom knowledge base to use with Voiceflow
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Overview

This code utilizes Open AI GPT, Langchain, Redis Cache, OpenSearch and Unstructured to fetch content from URLs, sitemap, PDF, Powerpoint, Notion doc and images to create embeddings/vectors and save them in a local OpenSearch database. The created collections can then be used with GPT to answer questions.


[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.loom.com%2Fembed%2F02833f38e3a6461983a2d7c3a3a570b8&display_name=Loom&url=https%3A%2F%2Fwww.loom.com%2Fshare%2F02833f38e3a6461983a2d7c3a3a570b8&image=https%3A%2F%2Fcdn.loom.com%2Fsessions%2Fthumbnails%2F02833f38e3a6461983a2d7c3a3a570b8-00001.gif&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=loom\" width=\"2560\" height=\"1920\" scrolling=\"no\" title=\"Loom embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.loom.com/share/02833f38e3a6461983a2d7c3a3a570b8",
  "title": "Langchain OpenSearch - demos-n-examples - 28 April 2023",
  "image": "https://cdn.loom.com/sessions/thumbnails/02833f38e3a6461983a2d7c3a3a570b8-00001.gif",
  "provider": "loom.com",
  "href": "https://www.loom.com/share/02833f38e3a6461983a2d7c3a3a570b8",
  "typeOfEmbed": "youtube"
}
[/block]


# Instructions & Code Repository

You can find our open source code and step by step instructions on using our Dialog API with it below.

<https://github.com/voiceflow-gallagan/langchain-local-knowledgebase/tree/c466af6c6818c31a5f7d131374cdd07a128182ad>