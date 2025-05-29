---
title: Shopify In-Store Copilot
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
## Overview

This custom interface puts your Voiceflow agent **straight into your Shopify store**, connecting your store's product data to an AI chat agent that can intelligently respond based on the page and the product being displayed, and serving powerful custom buttons like **add to cart**.

![](https://files.readme.io/ce5165e-image.png)

This project is built using Shopify's Theme App Extension system, and creates a custom block you can add anywhere to your Shopify store. On the backend, this is a Voiceflow custom interface using the Dialog Manager API to interact with your Voiceflow agent through a custom interface rather than through the basic web chat. This gives developers full control over how your custom interface looks and works.

![](https://files.readme.io/dcc8ab8-image.png)

Having a deeply embedded AI agent in your store is great for enhancing user engagement with dynamic conversation starters, product recommendations, and with great extensibility for custom features. Learn the steps to configure logic, integrate data, and improve customer experience.

## Instructions, Code, and Videos

You can find the setup instructions and code on GitHub [here](https://github.com/SuperZooper3/Voiceflow-In-Store-Shopify). Note that this current setup of the integration is a proof of concept, and shouldn't be deployed to a production Shopify store without at least hiding the Voiceflow API key through a proxy. This repo should be a good starting point for anyone looking to integrate a Voiceflow agent into your Shopify store.

Here's an overview video of the Shopify integration, discussing the advantages of building this kind of AI integration with Voiceflow:

<Embed url="https://www.youtube.com/watch?v=o-D4X1QCUv4" title="Revolutionizing Shopify E-Commerce with Embedded AI Agents" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/o-D4X1QCUv4/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=o-D4X1QCUv4" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252Fo-D4X1QCUv4%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253Do-D4X1QCUv4%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252Fo-D4X1QCUv4%252Fhqdefault.jpg%26key%3D02466f963b9b4bb8845a05b53d3235d7%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22640%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

You can also see a developer walkthrough of this integration.

<Embed url="https://www.youtube.com/watch?v=PQpQVdaGVtU" title="Integrating AI with Shopify Using Voiceflow: Technical Walkthrough" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/PQpQVdaGVtU/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=PQpQVdaGVtU" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FPQpQVdaGVtU%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DPQpQVdaGVtU%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FPQpQVdaGVtU%252Fhqdefault.jpg%26key%3D02466f963b9b4bb8845a05b53d3235d7%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22640%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />
