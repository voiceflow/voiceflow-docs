---
title: Getting started
excerpt: Best practices when using the Voiceflow platform.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
When building your agents, it's important to follow best practices to be sure that it's easy for you to scale up, make changes and maintain your agent in the long term. In this article, we'll cover a few best practices, including:

- Planning your agents
- Optimizing your Knowledge Base
- Organizing your agent using Workflows and Components
- Laying out your Workflows better with colours, titles, and actions
- Reuse combinations of steps faster with the library

# Planning your Agent

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

# Tips when building your Agent

Effective organization of your Voiceflow Agent is crucial for creating scalable, maintainable, and user-friendly conversational experiences.

Some general best practices include:

1. **Consistent Naming Conventions:** Use clear, descriptive names for your folders, workflows, and components. This makes navigating the Agent structure easier for you and your team.
2. **Modular Design:** Break down complex functionalities into smaller, manageable workflows. This makes your Agent easier to maintain and update.
3. **Balance Granularity:** While breaking things down is good, avoid creating too many tiny workflows or components. Aim for a balance between modularity and simplicity.
4. **Consider Scalability:** Design your folder structure and workflows with future expansion in mind. Leave room for adding new features or functionalities without disrupting the existing organization.
5. **Leverage Version Control: **Use version control features to track changes and collaborate effectively with your team.
6. **Optimize for Reusability:** When creating components or sub-workflows, think about how they might be reused in different contexts within your Agent.
7. **User-Centric Design: **Always keep the end-user in mind when organizing your Agent. The structure should facilitate natural, intuitive conversations.
8. **Consistent Color Coding:** Develop and stick to a color coding system for your blocks and connection lines inside the Workflow Builder. This visual organization can significantly improve the readability and maintainability of your Agent.
9. **Thoughtful Layout: **Regularly review and refine the visual layout of your Workflows. A clear, logical arrangement of blocks can make your Agent much easier to understand and maintain.
10. **Strategic Use of Actions:** Utilize actions to streamline your workflows where appropriate, reducing clutter and improving efficiency.

By applying these organizational and visual design principles, you can create a Voiceflow Agent that's not only powerful and effective but also intuitive to navigate and maintain. Remember, good organization, clear visual design, and efficient use of Voiceflow's features like actions are key to creating conversational experiences that truly resonate with users and meet your business objectives.

# Voiceflow Platform Structure

Voiceflow’s Agent building platform has three core systems:

1. **Knowledge Base: **The Knowledge Base is a repository and management system for content that your AI Agent uses to provide accurate and contextually relevant responses. 
2. **Workflow Builder:** Workflows are structured sequences of steps and actions designed to manage and automate the conversation flows of your virtual assistant.
3. **Content Management System: **The Voiceflow CMS houses all the components of your Agent in one place, including the Knowledge Base, workflows, reusable components, functions and more.

Let’s first explore the Knowledge Base and its best practices.