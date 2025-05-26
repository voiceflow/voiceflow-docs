---
title: Generate Automated Emails with User Transcripts
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Generate Automated Emails with User Transcripts
  description: >-
    This document provides a recipe for setting up a "send to email" feature to
    send the last conversation to the user when requested, using Voiceflow
    Transcripts API, LLM and Resend API, and Javascript to generate an HTML
    version of the transcript with an auto-generated TLDR.
  image: https://files.readme.io/efacd60-Subtle_Logo.png
  keywords:
    - transcript
    - voiceflow
    - api
    - llm
    - ai
    - ' email'
    - ' send'
    - ' summary'
  robots: index
next:
  description: ''
---
## Intro

In this recipe we will learn how to setup a "send to email" feature to send the last conversation to the user when requested. We will talk about Voiceflow Transcripts API, LLM and Resend API and the use of some Javascript to generate an HTML version of the transcript with an auto generated TLDR.

## Video

<Embed url="https://www.youtube.com/watch?v=tzyA-r-oEK0" title="Send Voiceflow agent last transcript to user's email" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/tzyA-r-oEK0/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=tzyA-r-oEK0" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FtzyA-r-oEK0%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DtzyA-r-oEK0%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FtzyA-r-oEK0%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## Follow along

Clone [this template ](https://www.youtube.com/redirect?event=video_description\&redir_token=QUFFLUhqbDFhSlpiMkZ3ak5nYnIzQU5WNWs2SzNoMkVOd3xBQ3Jtc0ttaldQQVJKRHRoUXF0S0dXRFMzTkFVSW1fOVdtWHpkdVhuNjEwajFvMzlYcU1TZEIySkZZT0x3V2hKRXdLNE94V3dtTFFxaEt3V3J5c1VSWHViZDZTeFYwSlBzMFhROThkd2h1cGFwcVJWN2diZWZfSQ\&q=https%3A%2F%2Fcreator.voiceflow.com%2Fdashboard%3Fimport%3D655386ba50d94e00072d183d\&v=tzyA-r-oEK0)into your Voiceflow project to get started.
