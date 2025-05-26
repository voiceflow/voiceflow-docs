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

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FtzyA-r-oEK0%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DtzyA-r-oEK0&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FtzyA-r-oEK0%2Fhqdefault.jpg&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=tzyA-r-oEK0",
  "title": "Send Voiceflow agent last transcript to user's email",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/tzyA-r-oEK0/hqdefault.jpg",
  "provider": "https://www.youtube.com/",
  "href": "https://www.youtube.com/watch?v=tzyA-r-oEK0",
  "typeOfEmbed": "youtube"
}
[/block]


## Follow along

Clone [this template ](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbDFhSlpiMkZ3ak5nYnIzQU5WNWs2SzNoMkVOd3xBQ3Jtc0ttaldQQVJKRHRoUXF0S0dXRFMzTkFVSW1fOVdtWHpkdVhuNjEwajFvMzlYcU1TZEIySkZZT0x3V2hKRXdLNE94V3dtTFFxaEt3V3J5c1VSWHViZDZTeFYwSlBzMFhROThkd2h1cGFwcVJWN2diZWZfSQ&q=https%3A%2F%2Fcreator.voiceflow.com%2Fdashboard%3Fimport%3D655386ba50d94e00072d183d&v=tzyA-r-oEK0)into your Voiceflow project to get started.