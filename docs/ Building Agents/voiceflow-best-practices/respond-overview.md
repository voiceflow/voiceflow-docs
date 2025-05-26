---
title: Responding to messages
excerpt: >-
  Responding is generating contextual responses for customers and sending them
  to your interface
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: basic
      slug: knowledge-base
      title: Knowledge Base
    - type: basic
      slug: render-custom-widgets-effects
      title: Custom Widgets & Effects (beta)
---
In the responding phase, the goal is to craft accurate and effective replies. This can be done either by using Voiceflow's built-in AI responses, or packaging responses with deterministic steps like text or images. 

# Responding with AI

The key to crafting effective AI responses lies in the information you are providing, your prompt, and which model you choose to use. To craft effective responses, you should:

1. **Provide the AI with relevant context about the users asking the question.** You can include variables in the prompts that you are sending to the AI. A good example is passing it the user is a developer or not, so the AI can provide more technical answers.
2. **Choose the right model.** Voiceflow offers a wide range of different models you can select, from various providers like OpenAI or Anthropic. Models like GPT 4o are more accurate, but are more expensive and slower. Models like GPT-3.5 are cheaper and faster, but less accurate. Ensure that you use the right model for the right task by considering these tradeoffs and running experiments. 
3. **Ensure your Knowledge Base Information is optimized.** Bad information in leads to bad answers out. Watch the video in the knowledge base doc to understand how to optimize the information in your knowledge base.

You're never going to get it right on the first time. Our advice is to start small, launch, and then improve your agent overtime by seeing how users are interacting with it.

AI often responds directly through text, with the [Response AI](https://developer.voiceflow.com/v2.0/docs/response-ai-set-ai) step. You can also use AI in more nuanced ways by using [Set AI](https://developer.voiceflow.com/v2.0/docs/response-ai-set-ai) to store an AI answer, that can then be parsed to fill out suggested buttons, choose a direction to branch in your agent, or more.

> 📘 Using an external model
>
> If you cant find the AI model you want to use in Voiceflow, you can always use the API step or create a Function to send and recieve a message from an external model!
>
> <Embed url="https://www.youtube.com/watch?v=skel9AlZnkw" title="Using Voiceflow with Mistral AI or Open Sourced AI Model" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/skel9AlZnkw/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=skel9AlZnkw" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252Fskel9AlZnkw%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253Dskel9AlZnkw%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252Fskel9AlZnkw%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

# Response outputs

Responding is straightforward in Voiceflow. You can use any of the following methods:

1. **[Text](https://developer.voiceflow.com/v2.0/docs/text)**: The text step allows you to display text to the user. You can include variables in any message to dynamically display information.
2. **[Images & GIFs](https://developer.voiceflow.com/v2.0/docs/images)**: The image step supports both images and GIFs.
3. **Other Media**: For media outside of this, there are a few ways to display it.
   1. **Using our Webchat**: The Voiceflow [Web chat](https://developer.voiceflow.com/v2.0/docs/web-chat-overview) supports iframes. You can also create your own custom widgets to display in the webchat (ie. calendar pickers, forms) using a custom widget (docs in the Web Chat section under deploying agents)
   2. **Using our API**: You can use a custom action step or a function to pass a custom 'trace' to the runtime. This way you can include the URL for the media you wish to receive and display it on your front end.

For all of these formats, you can either use hard-coded values, variables, or integrate AI answers.