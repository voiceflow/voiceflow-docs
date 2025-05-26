---
title: Dialogflow CX
excerpt: Overview of sample Rasa connector
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Building a Connector

Connectors are used to convert a Voiceflow project into a format that can be used in other platforms. To build a connector, you will need to extract the relevant data from a Voiceflow project (.vf file) and transform it into the desired format.

> 📘 Recommended reading
>
> 1. **Voiceflow Project Data Structure:**[Link](https://developer.voiceflow.com/docs/voiceflow-project-data-structure)
> 2. **Project API:** [Link](https://developer.voiceflow.com/reference/fetchproject)

# Sample Connector

Find the sample Voiceflow to Dialogflow CX exporter [here](https://github.com/voiceflow/dfcx-export-script-demo). **This is a starter template which you can build upon to best suit your conversation design system between Voiceflow and Dialogflow CX.**

# Overview

This repo contains a set of functions that allow for exporting a Dialogflow CX agent from a Voiceflow project. The process involves reading the project data, parsing the data, and then generating the domain and stories files.

## Usage

To use and modify this Exporter, you can follow along with the following tutorial series:

<Embed url="https://www.youtube.com/playlist?list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD" title="How to build a DFCX exporter" favicon="https://www.youtube.com/s/desktop/b182fc95/img/favicon.ico" image="https://i.ytimg.com/vi/hc_50PUUdQU/hqdefault.jpg?sqp=-oaymwEWCKgBEF5IWvKriqkDCQgBFQAAiEIYAQ==&rs=AOn4CLDTdvh5NN5REkCy-v-sfvasfZrSsg&days_since_epoch=19510" provider="youtube.com" href="https://www.youtube.com/playlist?list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttp%253A%252F%252Fwww.youtube.com%252Fembed%252Fvideoseries%253Flist%253DPLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fplaylist%253Flist%253DPLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252Fhc_50PUUdQU%252Fhqdefault.jpg%253Fsqp%253D-oaymwEWCKgBEF5IWvKriqkDCQgBFQAAiEIYAQ%253D%253D%2526rs%253DAOn4CLDTdvh5NN5REkCy-v-sfvasfZrSsg%2526days_since_epoch%253D19510%26key%3D02466f963b9b4bb8845a05b53d3235d7%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22853%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

The complete tutorial series includes:

[Introduction: how to build a DFCX exporter (Part 1)](https://www.youtube.com/watch?v=hc_50PUUdQU\&list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD\&index=1)

[Getting started: how to build a DFCX exporter (Part 2)](https://www.youtube.com/watch?v=Zy7YqS3zCXY\&list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD\&index=2)

[DFCX adapter setup: how to build a DFCX exporter (Part 3)](https://www.youtube.com/watch?v=NMSRfNYYRrY\&list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD\&index=3)

[Set up a service account on DFCX: how to build a DFCX exporter (Part 4)](https://www.youtube.com/watch?v=4IR8raZlnbs\&list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD\&index=4)

[Running the export script: how to build a DFCX exporter (Part 5)](https://www.youtube.com/watch?v=Y38pdNRE1to\&list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD\&index=5)

[Transforming entities: how to build a DFCX exporter (Part 6)](https://www.youtube.com/watch?v=dckyUJxpz5g\&list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD\&index=6)

[Walkthrough of completed adapter: how to build a DFCX exporter (Part 7)](https://www.youtube.com/watch?v=moAHYXuIFGE\&list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD\&index=7)

[Transforming flows and pages: how to build a DFCX exporter (Part 8)](https://www.youtube.com/watch?v=062FakB2KD0\&list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD\&index=8)
