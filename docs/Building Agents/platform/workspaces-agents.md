---
title: Workspaces and Agents
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
On a high level, your Voiceflow account is organized into Workspaces and Agents. Think of a Workspace as a “team” or a “company”, and each workspace can contain multiple agents (projects), that each contains their specific logic, knowledge base, variables and more.

## Workspace

Your workspace is home to your agents. If you are on a Teams or Enterprise plan, you can have multiple workspaces with multiple agents. When creating your Voiceflow account, it'll ask you to name your own workspace. We recommend calling it `Name's Workspace` like `Daniel's Workspace`.

![](https://files.readme.io/4994ac5-CleanShot_2024-06-07_at_17.09.04.png)

## Permissions and collaborators

Collaboration is done on a ***workspace level*** in Voiceflow. So when you invite a viewer, they will have access to everything in the workspace. You can choose to have someone be an editor on a specific agent, but they will **still be able to see all other agents** in the workspace. To share a prototype with someone without giving them access to the internals of your agent, use the [**prototypes** feature](https://developer.voiceflow.com/v2.0/docs/sharing-prototypes), which lets you quickly send them a link to try out your agent.

To change an individual's permission level for an agent, click on the options button and select *manage access*. 

![](https://files.readme.io/1b219de-CleanShot_2024-06-07_at_17.11.54.png)

## Agents

Each project in Voiceflow is a single agent. Each agent has its own dedicated

* Knowledge Base
* Workflows
* Data

When you make an update to an agent (ie. adding new data sources to the knowledge base), that update is available to everyone interacting with the agent. 

One agent can be connected to multiple channels (discord, slack, whatsapp, etc.) via the Dialog API. 

![](https://files.readme.io/efc228b-CleanShot_2024-07-11_at_10.47.512x.png)
