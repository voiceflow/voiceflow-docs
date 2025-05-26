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

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FdayOZyRQ4g4%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DdayOZyRQ4g4&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FdayOZyRQ4g4%2Fhqdefault.jpg&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"640\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=dayOZyRQ4g4",
  "title": "How to Integrate Voiceflow with VAPI Custom LLM for Web and Phone Calls",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/dayOZyRQ4g4/hqdefault.jpg",
  "provider": "https://www.youtube.com/",
  "href": "https://www.youtube.com/watch?v=dayOZyRQ4g4",
  "typeOfEmbed": "youtube"
}
[/block]


This method works both with text and voice agents. In a voice agent use the speak step to get the output spoken. In a text agent, use the basic text step to get the output spoken. Any other types of output from your Voiceflow agent (like audio step, buttons, images, etc...) won't be spoken by your agent on VAPI.

To learn more about building voice agents with VAPI, join their community on [Discord](https://discord.gg/nKWqC9PC2g).

## Workshop

You can also see a longer workshop we did with the VAPI community to learn a bit more about building voice agents on Voiceflow deployed through VAPI.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FPbS9rfopZQA%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DPbS9rfopZQA&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FPbS9rfopZQA%2Fhqdefault.jpg&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=PbS9rfopZQA",
  "title": "Using VAPI to Deploy a Voiceflow Voice Agent | Full Workshop",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/PbS9rfopZQA/hqdefault.jpg",
  "provider": "https://www.youtube.com/",
  "href": "https://www.youtube.com/watch?v=PbS9rfopZQA",
  "typeOfEmbed": "youtube"
}
[/block]