---
title: VAPI
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
## Overview

[VAPI](https://vapi.ai) is a great way to deploy your Voiceflow agents to production in an audio environment. It handles everything from Automatic Speech Recognition (ASR), to AI powered Text to Speech (TTS) with providers like ElevenLabs, and even hosting your agent on a live phone number, all with very low latency. 

To connect your Voiceflow agent to VAPI, you'll have to host a proxy, using VAPI's custom LLM features. It receives VAPI's text completion requests and formats them to be sent to the Voiceflow interact API, and then processes Voiceflow's response to be fed back to VAPI to be spoken. All you'll need to do is host this proxy yourself on a server for the messages to be routed between Voiceflow and VAPI.

## Instructions and Code

We've already built an example integration for you to use, with detailed setup instructions. You can find the GitHub repository with all the code and instructions to set up the integration yourself [here](https://github.com/voiceflow-gallagan/vf-vapi). Here's also a video going over this integration.

<Embed url="https://www.youtube.com/watch?v=dayOZyRQ4g4" title="How to Integrate Voiceflow with VAPI Custom LLM for Web and Phone Calls" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/dayOZyRQ4g4/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=dayOZyRQ4g4" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FdayOZyRQ4g4%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DdayOZyRQ4g4%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FdayOZyRQ4g4%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22640%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

This method works both with text and voice agents. In a voice agent use the speak step to get the output spoken. In a text agent, use the basic text step to get the output spoken. Any other types of output from your Voiceflow agent (like audio step, buttons, images, etc...) won't be spoken by your agent on VAPI.

To learn more about building voice agents with VAPI, join their community on [Discord](https://discord.gg/nKWqC9PC2g).

## Workshop

You can also see a longer workshop we did with the VAPI community to learn a bit more about building voice agents on Voiceflow deployed through VAPI.

<Embed url="https://www.youtube.com/watch?v=PbS9rfopZQA" title="Using VAPI to Deploy a Voiceflow Voice Agent | Full Workshop" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/PbS9rfopZQA/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=PbS9rfopZQA" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FPbS9rfopZQA%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DPbS9rfopZQA%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FPbS9rfopZQA%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />
