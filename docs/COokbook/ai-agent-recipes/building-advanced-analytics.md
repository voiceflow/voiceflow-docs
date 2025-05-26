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

<Image alt="Request to the proxy" align="center" src="https://files.readme.io/d4bc0f9-image.png">
  Request to the proxy
</Image>

## Video tutorial

Checkout the build on our youtube channel.

<Embed url="https://www.youtube.com/watch?v=kltzIN1zdVM" title="How to Build Advanced Analytics with an Analytics Proxy" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/kltzIN1zdVM/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=kltzIN1zdVM" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FkltzIN1zdVM%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DkltzIN1zdVM%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FkltzIN1zdVM%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />
