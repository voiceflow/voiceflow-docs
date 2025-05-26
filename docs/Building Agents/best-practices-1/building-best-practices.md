---
title: Planning your Agent
excerpt: Best practices for planning and building your Agent.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
When building your agents, it's important to follow best practices to be sure that it's easy for you to scale up, make changes and maintain your agent in the long term. In this article, we'll cover a few best practices, including:

* Planning your agents
* Optimizing your Knowledge Base
* Organizing your agent using Workflows and Components
* Laying out your Workflows better with colours, titles, and actions
* Reuse combinations of steps faster with the library

# Planning your Agents

Once you've planned out your agent using the **crawl, walk, run** framework, it's essential to first determine the overall architecture of your agent.

In Voiceflow, an agent has two levels.

1. **The Knowledge Base**: Used as the 'brain' of your agent. Upload documents relevant to your business, and your agent will use AI to answer questions based on the information it has access too.
2. **Workflows**: These are where you design action-based flows. For example, if you are building a support agent, you would upload your support and product documentation to the Knowledge base, so the agent can answer user questions. Then you may want to build a workflow for 'talk to sales' or 'submit a ticket'. That way you can collect specific pieces of information in a controlled manner like the user's email, their issue, etc. and make an API call to create the ticket in Zendesk.
   1. **Triggers:** Each workflow is activated by a trigger. Most often this is something that the user says like 'I want to submit a ticket'. Voiceflow uses AI (Large Language Models and Natural Language Understanding) to understand a user's intent, and match them to a trigger.

When planning your assistant, you want to first identify what the goal of the agent is and upload the appropriate information into the knowledge base.

Once you've thoroughly tested using the 'preview' functionality in the knowledge base to ensure:

1. That your prompt is producing satisfactory responses
2. That you have sufficiently optimized the information in the Knowledge Base

Then you can start building our workflows to scale your agent.

# Optimizing your Knowledge Base

Knowledge Bases are not magic, they use a technology called "Retrieval Augmented Generation" (RAG). It sounds complicated, but is easy to understand and build with Voiceflow!

1. Based *solely* on the question provided (not your prompt) AI looks through a database and finds relevant pieces of information that are similar.
2. It *then* passed those pieces of information to a Large Language Model (like GPT) to answer the user's question using the information provided + your prompt.
3. The answer is then provided to the users.

If the question is bad, then the AI may not find relevant matching information. Things like formatting + the words you use matter! Learn how to optimize the information in your knowledge base to get better AI answers below.

<Embed url="https://www.youtube.com/watch?v=iQJ9ecSwHxg" title="Getting Accurate AI Answers in Voiceflow" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/iQJ9ecSwHxg/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=iQJ9ecSwHxg" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FiQJ9ecSwHxg%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DiQJ9ecSwHxg%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FiQJ9ecSwHxg%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

# Organizing your agent using Workflows and Components

Once you start building out workflows you'll notice *components*. Components are designed for reusability. Think about them like a subfolder you can point to from anywhere.

Workflows should contain the main parts, components should be used for the reusable pieces that you may use in other flows.

In the example below for an e-commerce assistant, we have created a workflow for “order status”. This workflow uses a customer's email to check the status of their most recent orders in our database.

If the order is not found, a customer is presented with the option to submit a ticket. If they choose to do so, they are taken to a “submit a ticket” component, which contains some capture steps and a function to create a ticket in Zendesk with the customer's information.

We have designed it in this way so that we can reuse the “submit a ticket” component in any of our workflows where it makes sense to do so. This component can also be updated from one central place and updates everywhere that it is linked.

![](https://files.readme.io/65037b5-CleanShot_2024-06-19_at_14.35.032x.png)

# Laying out your Workflows better with colours, titles, and actions

When collaborating, it is important to create a design that is easy to navigate. Most customers tend to use a set of colours or design standards with their team to make things easier at a glance. In Voiceflow you can:

* Change the color of blocks
* Change the color of lines, change breakpoints, and add line titles
* Add text markup to the canvas to explain different parts of the workflow
* Tag team members or leave comments on different parts of your design

Actions can also be used to clean up designs and minimize the number of blocks and lines on the canvas. Actions can be accessed from the step menu and can be used to:

* Go to a specific block anywhere in your project (instead of having a line stretching across the workflow)
* Go to a specific trigger (to jump to another workflow)
* Make an API call, execute JavaScript, set a variable, or link to a component (instead of having additional steps or blocks on the canvas)

![](https://files.readme.io/d7bcabc-CleanShot_2024-06-19_at_14.41.422x.png)

# Reuse combinations of steps faster with the library

If you have a set of steps that you are copying and pasting often — you can save them to a 'library' in your project! Just shift + highlight (or click + drag) to select the steps you want, then click add to library.

<Image align="center" src="https://files.readme.io/d7726e7-CleanShot_2024-06-19_at_14.45.49.gif" />

With these tools, you should be able to create and scale your assistant with your team.
