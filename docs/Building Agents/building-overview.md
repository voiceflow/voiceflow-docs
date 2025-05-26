---
title: Overview
excerpt: Voiceflow is a tool to build complex AI agents with your team.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# When would I use Voiceflow

If you're looking to build a complex AI agent with your team, Voiceflow is the _fastest_ way to do it. It allows you to collaboratively build out an agent, connect to backend services through the API step or custom JavaScript functions, then connect to any interface you want with our API (like a web app, slack, teams, discord, mobile app you name it).

**Voiceflow is most powerful when you are working with a developer,** or at the very least someone who is technical and knows how to make API calls.

# Building Agents on Voiceflow

Creating an AI agent that handles complex queries across multiple channels requires a phased approach. Voiceflow provides a map with three phases: **Crawl, Walk, and Run**, focusing on the core concepts of **Understanding, Deciding, and Responding** to build powerful assistants.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FkOFbBSZlcDk%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DkOFbBSZlcDk&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FkOFbBSZlcDk%2Fhqdefault.jpg&key=02466f963b9b4bb8845a05b53d3235d7&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=kOFbBSZlcDk",
  "title": "How to Scale Your AI Agent | Crawl, Walk, Run",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/kOFbBSZlcDk/hqdefault.jpg",
  "provider": "https://www.youtube.com/",
  "href": "https://www.youtube.com/watch?v=kOFbBSZlcDk",
  "typeOfEmbed": "youtube"
}
[/block]


## Crawl: Out-of-the-box AI Solutions

In the crawl phase, you use basic tools like GPTs and Microsoft Co-Pilot to create an AI loop that handles simple queries. This phase is similar to building a website with Squarespace—sufficient for 70% of use cases. Tools like Zapier can add simple actions, but for more advanced needs, you’ll need to move to the walk phase.

## Walk: Advanced AI Agent Building

The walk phase involves strategic use of LLMs, pulling user information, and layering on business rules. This phase is akin to using Webflow or Photoshop, providing more control and customization. You create highly personalized experiences by integrating business logic and user data.

_This is where Voiceflow is most powerful._

## Run: The Future of AI Agents

In the run phase, AI agents are proactive, constantly learning and updating based on user interactions. This phase focuses on dynamic learning and proactive responses, pushing the boundaries of AI capabilities.

_This is what we build features for._

## Core Concepts: Understand, Decide, Respond

### Understand: Capturing Intent

Understanding involves how your assistant captures user intent and information. Using natural language understanding (NLU) and large language models (LLMs) together enhances accuracy.

### Decide: Processing Information

Deciding combines business rules with AI to provide personalized experiences. Variables, logic, and LLMs determine the best route for user queries.

### Respond: Crafting Answers

Responding varies by phase. In crawl, responses are LLM driven with minimal context. In walk, responses are customized using specific prompts and AI models. In run, responses are dynamic, leveraging advanced models and continuous learning.

## Recommended Launch Approach

- Start in the **Crawl** phase. Build out one clear use case, and launch your agent. Use the transcripts feature to see how users are interacting with your agent and make improvements to it.
  - **Example**: Start with customer support. Answer the most common questions with the knowledge base, and use the API step or a function to create tickets that can't be answered. Spend your time optimizing this and answering more and more complex questions to increase your automation rate.
- Expand to the **Walk** phase by layering on use cases. Once you have maxed out your single use case across the understand, decide, and respond categories. Add on new workflows and repeat.
  - **Example**: Once you've got support tickets locked down, start adding on a sales function. This can be within the same agent or in another separate agent. You can also start to expand to multiple channels. Go from just the chat widget to email, slack, discord, or embedded more natively in your app/website.
- Experiment in the **Run** phase. Start to push the boundaries of your AI agent by connecting to new models and new backend tools to see if you can optimize performance. Follow along with our developer experiments on YouTube and our GitHub repo to see what experiments we're learning from with our own AI agent — Tico!