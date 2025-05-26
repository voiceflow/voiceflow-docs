---
title: Advanced Rag Filtering and Tagging
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

Voiceflow's Knowledge Base (RAG) api allows you to use filters and tags to create more powerful agent. In this recipe you'll learn how to:

- Use a feedback card to tags docs based on LLM answers
- Generate a new doc using “file” upload/tag with user’s question and LLM answer
- Use KB Upload API to add this newly created doc
- Use KB Query API with tags filtering
- Get the best chunk based on “validated” tag and highest score.
- Reduce token usage by avoid using LLM for validated answers
- Limit hallucinations and return same validated answers each time

## Youtube video

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FhYjuZ2qnk2Y%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DhYjuZ2qnk2Y&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FhYjuZ2qnk2Y%2Fhqdefault.jpg&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"640\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=hYjuZ2qnk2Y",
  "title": "Voiceflow Knowledge Base Upload and Tags API to save tokens and return validated answers.",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/hYjuZ2qnk2Y/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=hYjuZ2qnk2Y",
  "typeOfEmbed": "youtube"
}
[/block]


## Try yourself

[Try the template yourself! ](https://creator.voiceflow.com/dashboard?import=6534dc3482bc0a000636907f). Import into your project.