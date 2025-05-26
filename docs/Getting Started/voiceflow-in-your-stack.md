---
title: How Voiceflow fits in your tech stack
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
Voiceflow is primarily a platform for building **advanced AI agents**, and is quite versatile in the ways that it can fit in your tech stack to solve specific solutions. From deploying chat and voice agents, to integrating knowledge bases, this article will cover different ways Voiceflow fits in your organization's tech stack.

# How to think about Voiceflow

Think about Voiceflow as the orchestration layer between your front-end, back-end services, and AI models.

Voiceflow holds the agent logic and stores where the users are in their conversation (their _conversation state_). It is able to send and receive messages from your front-end interface (whether that is the first party web chat, a custom web app, Slack etc.) and push/pull data from your back-end services (like a database, CMS, or any other service with an API).

Voiceflow also has a number of AI models that it is connected to, so you can use them out of the box.

> 📘 Our product focus
> 
> At Voiceflow we prioritize **extensibility and customization**. So rather than create many out of the box integrations, we have instead focused on creating powerful developer tools and APIs so you can connect to your tools in your way.

![](https://files.readme.io/0bdbb59-CleanShot_2024-06-20_at_15.27.362x.png)

# Building your Agents

## Sending and Receiving Data from your Back-end Services

Voiceflow is able to send and receive data from other services in two ways.

1. **The API Step:** This is a step in Voiceflow that allows you to make an API call to any service and store the response in _variables_.
2. **Functions:** Custom functions allow you to write a JavaScript function that can use a fetch request. You can therefore use this to send/receive data, transform data, and even return traces imitating any step from text or image, or even custom traces like a [Custom Action](https://developer.voiceflow.com/v2.0/docs/custom-actions).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1b17a03-CleanShot_2024-06-20_at_15.39.582x.png",
        null,
        "This function makes a call to the Zendesk API to create a ticket containing information about the customer."
      ],
      "align": "center",
      "caption": "This function makes a call to the Zendesk API to create a ticket containing information about the customer."
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7f74d6f-CleanShot_2024-06-20_at_15.40.422x.png",
        null,
        "This is what the function looks like when it is added to a workflow."
      ],
      "align": "center",
      "caption": "This is what the function looks like when it is added to a workflow."
    }
  ]
}
[/block]


## Using AI Models in Voiceflow

Voiceflow has a growing number of AI large language models (LLMs) that are natively built in. You can leverage different LLMs in different parts of your design (AI response, KB synthesis, LLM intent classification) and send prompts with dynamic variables to them. In this way, Voiceflow helps you **save time** with all the LLM integrations you might want already built in.

LLMs can be leveraged in the following ways (we are adding more each week)

1. **Response AI**: Send a prompt to a LLM and display the response to the user (and even supports Markdown formatting).
2. **Set AI**: Send a prompt to an LLM and store the output in a variable (useful for leveraging AI to assist with entity capture, summarization, computation and more).
3. **Knowledge Base**: Voiceflow has a built-in Vector Database and RAG solution. When you use the [Knowledge Base](https://developer.voiceflow.com/v2.0/docs/knowledge-base) the KB uses the question passed to return relevant chunks from the Vector Database, and then passes those chunks along with your prompt to an LLM of your choice to synthesize a response to the user.
4. **LLM Intent Classification**: LLMs can be used to classify intents instead of using the NLU, that can often be much more accurate or context aware.

![](https://files.readme.io/925e277-CleanShot_2024-06-20_at_15.37.492x.png)

If you have a self-hosted model or want to use a model outside the ones we provide, you can use a function or an API call to send and receive information to a custom model, so you can **BYO model**.

- Response and Set AI can be mimicked using custom functions that are either returning traces of text, or updating variables. For an example of this, see the [GPT 4o function](https://www.voiceflow.com/function/connect-to-gpt-4o) we made an hour after release.
- Knowledge Base Synthesis can be done in a custom function with a BYO model by using the KB API with **synthesis disabled** and then using your own model through API calls to synthesize an answer.
- LLM intent classification unfortunately can't currently be easily mimicked.

# Deploying your Agents

There are various ways your Agents can fit into your tech stack for it to insert itself into user experiences:

## Front-end website with web chat

Voiceflow's built-in web chat is the easiest way to deploy your Voiceflow agent into production. All the UI and Dialog Manager APIs are fully implemented for you.

Simply insert the out-of-the-box JavaScript snippet into your front-end HTML, typically through inserting it into your default footer component in React for any other front-end frameworks. Regardless of where you place the code snippet, the agent will appear fixed to the screen and in accord with your appearance settings for the web chat.

You can also embed your agent into an iframe.

You can learn more about the [web chat here](https://developer.voiceflow.com/v2.0/docs/web-chat-overview).

## Custom front-end interfaces

Voiceflow is able to interact with any front-end interface. It does this through the Dialog Manager API through sending a variety of message types called _traces_. Our web chat implements all these traces out of the box, so to make a custom interface you would choose how you handle each trace type (text, images, buttons, etc.).

A trace is a standard format in which Voiceflow sends a message. Below is an example of an _image trace_ where Voiceflow is sending an image.

```
{
  "type": "visual",
  "payload": {
    "visualType": "image",
    "image": "https://assets-global.website-files.com/example-file.png",
    "dimensions": {
      "width": 800,
      "height": 800
    }
}
```

You can use these to render an image on your front-end. There are a variety of built-in trace types that you can find here: [See all trace types.](https://developer.voiceflow.com/v2.0/reference/trace-types)

If there is a type of message that Voiceflow does not have, you can create a _custom trace_ to render things like file upload, calendar pickers, or trigger any kind of custom functionality. This is available when using our built-in webchat widget or your own custom interface.

You would use our _custom action_ functionality to do this. You can see an [example of how a custom action is used](https://developer.voiceflow.com/v2.0/docs/render-custom-widgets-effects#3-trigger-the-extension-with-a-custom-action) with our webchat to render a custom widget.

## Custom back-end apps

Using the [Dialog Manager API](https://developer.voiceflow.com/v2.0/reference/overview), you can build your own custom interface that interacts directly with your Voiceflow agent. 

This can be used for everything from creating pretty custom chat agent UIs like [toplyne.io](https://toplyne.io/) does on their website.

![](https://files.readme.io/d110d94-CleanShot_2024-06-26_at_23.15.172x.png)

Or fully custom interfaces like an AI enhanced article reader, Voiceflow in Minecraft or even in Unity! 

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FDxIsHNxr_0g%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DDxIsHNxr_0g&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FDxIsHNxr_0g%2Fhqdefault.jpg&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=DxIsHNxr_0g",
  "title": "An Embedded AI Article Reader Developed in Voiceflow",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/DxIsHNxr_0g/hqdefault.jpg",
  "provider": "https://www.youtube.com/",
  "href": "https://www.youtube.com/watch?v=DxIsHNxr_0g",
  "typeOfEmbed": "youtube"
}
[/block]


You can learn more about building custom interfaces [here](https://developer.voiceflow.com/v2.0/docs/custom-interfaces-overview).

# Using the Knowledge Base Independently

Through the extensive Knowledge Base Management and Query APIs, Voiceflow's Knowledge Base can also be used as an easy-to-use RAG and vector database solution, outside of being integrated directly into a Voiceflow agent.

To use a Knowledge Base on its own:

1. Upload documents to a new project's Knowledge Base (text files, PDFs, URLs)
2. Query with the KB using the [KB Query APIs](https://developer.voiceflow.com/v2.0/reference/post_knowledge-base-query)
3. Continuously update and add more documents to your knowledge base through CI/CD pipelines, for example with the [KB Management APIs](https://developer.voiceflow.com/v2.0/reference/post_v3alpha-knowledge-base-docs-upload) 

This can be useful to use either the knowledge base on its own, or as secondary knowledge bases for a main project, letting you segregate different types of documents.