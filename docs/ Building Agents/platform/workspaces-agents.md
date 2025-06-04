---
title: Workspaces and Projects
excerpt: Create awesome agents and keep them organized.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Your Voiceflow account is organized into workspaces and projects. Think of a workspace as a “team” or a “company”,  with each workspace containing one or more projects. Each project is its own AI agent with its own logic, [knowledge base](doc:knowledge-base-1), and [workflows](doc:workflows).

<br />

## Workspaces

Your workspace is home to your projects and is the first thing you'll see when [logging into Voiceflow](https://creator.voiceflow.com). You can organize your projects inside a workspace using folders, and can customize a project's icon, name, and description by hovering over the project and clicking the three dots that appear. From there, you can also export your agent as a `.vf` file, or share a clone link which allows others to copy your agent.

If you are on a Teams or Enterprise plan, you can create multiple workspaces - just click the name of your workspace in the top left corner of the dashboard, then click **new workspace**.

<Image align="center" src="https://files.readme.io/f5e2a9a2275cafec17969b8ce5c13c59dc807b049ebc25d8688c0b32a63b385c-CleanShot_2025-06-04_at_15.56.522x.png" />

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