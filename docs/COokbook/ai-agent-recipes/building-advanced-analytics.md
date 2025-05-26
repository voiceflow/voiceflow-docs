---
title: Building Advanced Analytics
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Advanced Analytics Proxy for Voiceflow Chat Widget
  description: >-
    This document explains how to build an advanced analytics proxy using
    Node.js for Voiceflow, allowing for the collection and analysis of response
    traces for analytics purposes. Check out the video tutorial on their YouTube
    channel for more information.
  image: https://files.readme.io/311d80d-Subtle_Logo.png
  keywords:
    - analytics
    - ' middleware'
    - ' api'
    - ' proxy'
    - ' node'
    - ' api'
    - ' gateway'
    - ' docker'
    - ' llm'
  robots: index
next:
  description: ''
---
## Overview

This recipe demonstrates how to build an advanced analytics proxy to build advanced analytics with Voiceflow. It contains a Node.js application that acts as a proxy between a Chat Widget and the Voiceflow Dialog Manager (DM) API. The primary purpose of this proxy is to intercept requests sent from the Chat Widget to the Voiceflow DM API's /interact endpoint, allowing for the collection, parsing, and analysis of response traces for analytics purposes.

[Github link](https://github.com/voiceflow-gallagan/vf-analytics-proxy?tab=readme-ov-file)

[block:image]{"images":[{"image":["https://files.readme.io/d4bc0f9-image.png",null,null],"align":"center","caption":"Request to the proxy"}]}[/block]

## Video tutorial

Checkout the build on our youtube channel.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FkltzIN1zdVM%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DkltzIN1zdVM&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FkltzIN1zdVM%2Fhqdefault.jpg&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=kltzIN1zdVM",
  "title": "How to Build Advanced Analytics with an Analytics Proxy",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/kltzIN1zdVM/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=kltzIN1zdVM",
  "typeOfEmbed": "youtube"
}
[/block]