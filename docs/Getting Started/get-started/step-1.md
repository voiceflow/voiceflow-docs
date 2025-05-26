---
title: 'Step 1: Create your agent'
excerpt: Get an AI agent up and running in under 5 minutes.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: Get your API key and deploy your project
  pages:
    - type: basic
      slug: step-1-get-api-key
      title: 'Step 2: Get API Key'
---
Agents are the core of Voiceflow. Each agent is defined by the workflows driving its internal logic, but represents a single “application”.

## **Step 1: Create a new <<glossary:agent>>**

In your workspace, click the 'New Agent' button on the top right. Give your agent a name.

![](https://files.readme.io/0778c5a-CleanShot_2024-06-24_at_13.57.542x.png)

This walkthrough will focus on building and deploying a basic agent.

![](https://files.readme.io/d2951e4-CleanShot_2024-06-19_at_16.25.412x.png)

## Step 2: Add a step to the canvas

Designing on Voiceflow starts at the step-level, which includes adding, editing, and connecting steps/blocks on the canvas and creating paths in your agent. Drag a step from this menu into your agent.

The AI steps allow you to send prompts to different AI models like GPT-4 and Claude. You can specify if you want to use the knowledge base or not to answer the prompt.

Details on each step can be found [here](https://learn.voiceflow.com/hc/en-us/articles/9174803155341-What-are-Steps-Blocks).

![](https://files.readme.io/d9d21ba-CleanShot_2024-06-19_at_16.31.222x.png)

## **Step 3: Upload data to knowledge base**

When the agent is created, go to the Knowledge Base. Here you can click on 'Add Data Source' on the top right and add as many PDFs, URLs, or Text files as you want to power your agent.

Once uploaded, your AI agent will use these documents to answer questions via GPT. The more documents you upload, the better the answers will be.

**Note: There is a 10mb file limit per upload.**

![](https://files.readme.io/d2951e4-CleanShot_2024-06-19_at_16.25.412x.png)

<br />

Once you've uploaded some initial documents, press “Preview” at the top of the screen. This allows you to ask the Knowledge Base questions and see what the responses are. Clicking “sources” will allow you to see where the answers are being pulled from. Clicking “settings” will allow you to modify the AI prompt being used to generate the answer.

![](https://files.readme.io/fda479e-CleanShot_2024-06-19_at_16.26.492x.png)

## **Step 4: Run a prototype**

Once you have a basic agent, run a prototype to make sure that it works the way you intended. If it isn't working the way you expect, check our guide to debugging [here](https://www.loom.com/share/1d36e4e0eae3478bae4cadc55ba0433b).

![](https://files.readme.io/5072e95-CleanShot_2024-06-19_at_16.32.112x.png)