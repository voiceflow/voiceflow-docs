---
title: Overview and setup
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
In this guide, we'll walk you through using your first Voiceflow API with a simple Python interface to chat with your agent. You can also find a video version of the same guide below.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FKUqpPeJ6DkQ%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DKUqpPeJ6DkQ&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FKUqpPeJ6DkQ%2Fhqdefault.jpg&key=02466f963b9b4bb8845a05b53d3235d7&type=text%2Fhtml&schema=youtube\" width=\"640\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=KUqpPeJ6DkQ",
  "title": "Getting Started with Voiceflow APIs",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/KUqpPeJ6DkQ/hqdefault.jpg",
  "provider": "https://www.youtube.com/",
  "href": "https://www.youtube.com/watch?v=KUqpPeJ6DkQ",
  "typeOfEmbed": "youtube"
}
[/block]


This guide will primarily be taught in Python is easy to get started with, and the lessons learned here should be applicable to any programming language. 

There will still be JavaScript NodeJS equivalents in a second tab on all the code examples, and you can find examples in more languages on our [API Examples GitHub repo](https://github.com/voiceflow/api-examples). This guide is based off the Python example from there, but goes a bit more in depth with more APIs.

You'll learn:

- How to get your Voiceflow Project API key
- Using the Dialog Manager API (DM API)
  - How to send requests to Voiceflow APIs
  - How to start a conversation
  - How to parse the output traces
  - How to send user replies
  - How to deal with other traces (button, end, and more)
- Using the Transcripts and other APIs
  - Saving your user transcript

We encourage you to follow along step by step, but if you ever get lost or would jump ahead to the [finished code](https://github.com/SuperZooper3/Voiceflow-Getting-Started-APIs-Guide/blob/main/VoiceflowAPIGuide_Finished.py) (for both **Python and JavaScript**), you can find it here. Whenever you see 👉, that means that there's a **step to take** in the guide. Speaking of which…

👉 Make sure you've installed [Python](https://www.python.org/downloads/), and create a new empty file called `VoiceflowAPIGuide.py`. Since we'll be using web requests to interact with Voiceflow APIs, make sure to import the `requests` library. If you're following along in JavaScript (using NodeJS), make sure to install axios with `npm install axios`.

```python
import requests
```
```javascript
const axios = require('axios');
```

👉 Import [this Voiceflow project](https://github.com/SuperZooper3/Voiceflow-Getting-Started-APIs-Guide/blob/main/Voiceflow_API_Getting_Started_Part_1.vf) into your workspace. You can click a download button in the top right. It's the template we'll be using for this project, and since this guide is focused on using the APIs, it's a pretty basic project.

![](https://files.readme.io/75827eb-image.png)

<br />

![](https://files.readme.io/fcd626a-image.png)

👉 Once you've imported the project, run a test from inside Voiceflow by clicking the run button in the top right. Make any changes you want to, and then click _Publish_ in the top right. This puts out a version of your Voiceflow agent that we can work with. There's no need to give it a name. If you forget to publish, your agent won't work and the returned JSON will just be `[]`.

![](https://files.readme.io/7ea0217-image.png)

> 📘 Next up: [How to get your Voiceflow Project API key](https://docs.voiceflow.com/reference/how-to-get-your-voiceflow-project-api-key)