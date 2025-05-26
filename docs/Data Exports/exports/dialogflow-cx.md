---
title: Dialogflow CX
excerpt: Overview of sample Dialogflow CX connector
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Building a Connector

Connectors are used to convert a Voiceflow <<glossary:agent>> into a format that can be used in other platforms. To build a connector, you will need to extract the relevant data from a Voiceflow project (.vf file) and transform it into the desired format.

> 📘 Recommended reading
> 
> 1. **Voiceflow Project Data Structure: **[Link](https://developer.voiceflow.com/docs/voiceflow-project-data-structure)
> 2. **Project API:** [Link](https://developer.voiceflow.com/reference/fetchproject)

# Sample Connector

Find the sample Voiceflow to Dialogflow CX exporter [here](https://github.com/voiceflow/dfcx-export-script-demo). **This is a starter template which you can build upon to best suit your conversation design system between Voiceflow and Dialogflow CX.**

# Overview

This repo contains a set of functions that allow for exporting a Dialogflow CX agent from a Voiceflow project. The process involves reading the project data, parsing the data, and then generating the domain and stories files.

## Usage

To use and modify this Exporter, you can follow along with the following tutorial series:

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=http%3A%2F%2Fwww.youtube.com%2Fembed%2Fvideoseries%3Flist%3DPLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fplaylist%3Flist%3DPLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2Fhc_50PUUdQU%2Fhqdefault.jpg%3Fsqp%3D-oaymwEWCKgBEF5IWvKriqkDCQgBFQAAiEIYAQ%3D%3D%26rs%3DAOn4CLDTdvh5NN5REkCy-v-sfvasfZrSsg%26days_since_epoch%3D19510&key=02466f963b9b4bb8845a05b53d3235d7&type=text%2Fhtml&schema=youtube\" width=\"853\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/playlist?list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD",
  "title": "How to build a DFCX exporter",
  "favicon": "https://www.youtube.com/s/desktop/b182fc95/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/hc_50PUUdQU/hqdefault.jpg?sqp=-oaymwEWCKgBEF5IWvKriqkDCQgBFQAAiEIYAQ==&rs=AOn4CLDTdvh5NN5REkCy-v-sfvasfZrSsg&days_since_epoch=19510",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/playlist?list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD",
  "typeOfEmbed": "youtube"
}
[/block]


The complete tutorial series includes:

[Introduction: how to build a DFCX exporter (Part 1)](https://www.youtube.com/watch?v=hc_50PUUdQU&list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD&index=1)

[Getting started: how to build a DFCX exporter (Part 2)](https://www.youtube.com/watch?v=Zy7YqS3zCXY&list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD&index=2)

[DFCX adapter setup: how to build a DFCX exporter (Part 3)](https://www.youtube.com/watch?v=NMSRfNYYRrY&list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD&index=3)

[Set up a service account on DFCX: how to build a DFCX exporter (Part 4)](https://www.youtube.com/watch?v=4IR8raZlnbs&list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD&index=4)

[Running the export script: how to build a DFCX exporter (Part 5)](https://www.youtube.com/watch?v=Y38pdNRE1to&list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD&index=5)

[Transforming entities: how to build a DFCX exporter (Part 6)](https://www.youtube.com/watch?v=dckyUJxpz5g&list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD&index=6)

[Walkthrough of completed adapter: how to build a DFCX exporter (Part 7)](https://www.youtube.com/watch?v=moAHYXuIFGE&list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD&index=7)

[Transforming flows and pages: how to build a DFCX exporter (Part 8)](https://www.youtube.com/watch?v=062FakB2KD0&list=PLKYemGIohRgBJF2jzir9F6DshCKYMZ9ZD&index=8)