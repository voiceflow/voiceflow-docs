---
title: Overview
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
> [block:embed]{"html":"<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2Fskel9AlZnkw%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3Dskel9AlZnkw&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2Fskel9AlZnkw%2Fhqdefault.jpg&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>","url":"https://www.youtube.com/watch?v=skel9AlZnkw","title":"Using Voiceflow with Mistral AI or Open Sourced AI Model","favicon":"https://www.google.com/favicon.ico","image":"https://i.ytimg.com/vi/skel9AlZnkw/hqdefault.jpg","provider":"https://www.youtube.com/","href":"https://www.youtube.com/watch?v=skel9AlZnkw","typeOfEmbed":"youtube"}[/block]

# Response outputs

Responding is straightforward in Voiceflow. You can use any of the following methods:

1. **[Text](https://developer.voiceflow.com/v2.0/docs/text)**: The text step allows you to display text to the user. You can include variables in any message to dynamically display information.
2. **[Images & GIFs](https://developer.voiceflow.com/v2.0/docs/images)**: The image step supports both images and GIFs.
3. **Other Media**: For media outside of this, there are a few ways to display it.
   1. **Using our Webchat**: The Voiceflow [Web chat](https://developer.voiceflow.com/v2.0/docs/web-chat-overview) supports iframes. You can also create your own custom widgets to display in the webchat (ie. calendar pickers, forms) using a custom widget (docs in the Web Chat section under deploying agents)
   2. **Using our API**: You can use a custom action step or a function to pass a custom 'trace' to the runtime. This way you can include the URL for the media you wish to receive and display it on your front end.

For all of these formats, you can either use hard-coded values, variables, or integrate AI answers.