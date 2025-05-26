---
title: Overview
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# What is Voiceflow?

Voiceflow is the fastest way to _**build and scale high complexity AI agents**_ with your team. 

It is composed of the following products:

1. **A vector database**: Quickly create a vector database to use with our built-in prompt manager for basic and advanced RAG solutions with the Voiceflow _Knowledge Base_.
2. **A collaborative workflow builder**: Create complex flows with your team that leverage logic, variables, and JavaScript functions to accomplish tasks with _Workflows_. Collaborate and build in real-time.
3. **JavaScript functions**: Send, receive, and manipulate data from other tools in your tech stack with _Functions_. Create them once and reuse them in your workflows.
4. **A suite of APIs**: Connect your agent to any custom interface to build a native co-pilot, IVR, discord bot, slack agent, WhatsApp assistant and more. We also have an out-of-the-box _Webchat Widget_ that can be used natively with Voiceflow.

# How Voiceflow works

Voiceflow is a collaborative tool that features a powerful collaborative low-code AI <<glossary:agent>> building platform. Agents built with Voiceflow are represented by structured [JSON files called .VF files](https://developer.voiceflow.com/docs/voiceflow-project-data-structure).

The below Voiceflow Agent design is an example of what is structured using the .VF JSON file.

You can find Voiceflow's Agent design platform documentation [here](https://learn.voiceflow.com/hc/en-us/articles/14538287359629-Introducing-Voiceflow-Docs-and-Guides).

## Launch your <<glossary:agent>> directly

Agents built on Voiceflow offer a [Dialog Manager API](https://developer.voiceflow.com/reference/overview) which manages conversation state at runtime.

This enables developers to offload the mundane work of managing dialog state machines to the designer who creates and maintains the conversation logic with Voiceflow's graphic design interface. Developers can use the Dialog API for production use cases, or custom interface prototypes, where Voiceflow is hidden in the background. 

Private cloud deployments are [available upon request](https://www.voiceflow.com/demo). The Dialog API can use Voiceflow's NLU, or your own 3rd party or custom NLU to resolve intents.