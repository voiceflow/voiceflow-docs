---
title: Overview
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
\*\**The Testing API is in Beta*

\*\*The Testing API allows you to run simulated tests at scale to determine the accuracy of your assistants responses. This can be used to test the accuracy of different prompts and KB data.

The testing API is meant to solve a few key problems:

1. Evaluating how good a Knowledge base response is
2. Lowering the barrier for AI testing
3. Making it easier to go to production by having regression tests.

The main use case demo’d below is the KB use case, but this can also be used for static and NLU responses.

* Using the exact match field to make sure you hit the correct intent
* Using the exact match field to detect copy changes.

Here is a quick video demo on how the Testing API can be used:

<Embed url="https://www.loom.com/share/31c5c64db0de4a8da1aec239c25ffc86" title="Testing the Knowledge Base with the Programmatic Generation" image="https://cdn.loom.com/sessions/thumbnails/31c5c64db0de4a8da1aec239c25ffc86-1700510177535.gif" provider="loom.com" href="https://www.loom.com/share/31c5c64db0de4a8da1aec239c25ffc86" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.loom.com%252Fembed%252F31c5c64db0de4a8da1aec239c25ffc86%26display_name%3DLoom%26url%3Dhttps%253A%252F%252Fwww.loom.com%252Fshare%252F31c5c64db0de4a8da1aec239c25ffc86%26image%3Dhttps%253A%252F%252Fcdn.loom.com%252Fsessions%252Fthumbnails%252F31c5c64db0de4a8da1aec239c25ffc86-1700510177535.gif%26key%3D02466f963b9b4bb8845a05b53d3235d7%26type%3Dtext%252Fhtml%26schema%3Dloom%22%20width%3D%22100%25%22%20style%3D%22aspect-ratio%3A%2016%20%2F%209%22%20scrolling%3D%22no%22%20title%3D%22Loom%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />
