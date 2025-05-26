---
title: Quick Start Guide
excerpt: Use our APIs to launch to any channel or to build a custom production workflow
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: 'More details on our Dialog Manager API:'
  pages:
    - type: endpoint
      slug: stateinteract
      title: interact
---
> 📘 What can you do with our APIs?
>
> *Join our discord[here](https://discord.gg/JXRbEv7nD2) to get help and see what people are building!*&#xD83D;�
>
> Voiceflow lets teams build, test, and launch AI <Glossary>agent</Glossary> (also referred to as a 'project' or 'assistant') to any channel, for any use case.
>
> **APIs**
>
> Voiceflow offers a suite of APIs to launch and host AI Agents, as well as build custom tools, interfaces and workflows on-top of Voiceflow.
>
> **Popular APIs include:**
>
> * **[Dialog Manager API](https://developer.voiceflow.com/reference/overview):** launch your Agent with hosted dialog state management
> * **[Knowledge Management API](https://developer.voiceflow.com/reference/post_v3alpha-knowledge-base-docs-upload):** manage Knowledge Base data with a CRUD API
> * **[Knowledge Query API](https://developer.voiceflow.com/reference/post_knowledge-base-query):** query your managed Knowledge Base
> * **[Analytics API](https://developer.voiceflow.com/reference/querypubliccontroller_queryusage):** retrieve Agent usage data
> * **[Transcripts API](https://developer.voiceflow.com/reference/fetchtranscripts)** retrieve end-user conversation transcripts
> * **[NLU API](https://developer.voiceflow.com/reference/post_publish-projectid)** train and run inference on VFNLU
>
> These APIs can be used together with Voiceflow's Agent building platform to create custom solutions.
>
> **Popular solutions include:**
>
> 1. **Single Source of Truth:** Use the Voiceflow Agent Builder as a single-source of truth for Agent designs, programmatically retrieving structured design content (JSON) with the [Project API](https://developer.voiceflow.com/reference/fetchproject)
> 2. **Build and Launch:** build low-code with the Agent builder, deploy with the [Dialog Manager API](https://developer.voiceflow.com/reference/overview)
> 3. **Managed Knowledge Base:** use the [Knowledge Base Management API](https://developer.voiceflow.com/reference/post_v3alpha-knowledge-base-docs-upload) and [Knowledge Base Query API](https://developer.voiceflow.com/reference/post_knowledge-base-query) to act as a managed Knowledge Base service
>
> **Custom Launch**
>
> Using our Dialog API directly gives you the flexibility to launch to any channel. These code samples and others on our [github](https://github.com/voiceflow/demos-n-examples) provide a starting point to launch to a custom channel.

# How Voiceflow works

Voiceflow is a collaborative tool that features a powerful collaborative low-code AI <Glossary>agent</Glossary> building platform. Agents built with Voiceflow are represented by structured [JSON files called .VF files](https://developer.voiceflow.com/docs/voiceflow-project-data-structure).

The below Voiceflow Agent design is an example of what is structured using the .VF JSON file.

![](https://files.readme.io/266dbbc-small-CleanShot_2023-05-01_at_22.58.00.png)

You can find Voiceflow's Agent design platform documentation [here](https://learn.voiceflow.com/hc/en-us/articles/14538287359629-Introducing-Voiceflow-Docs-and-Guides).

## Launch your <Glossary>agent</Glossary> directly

Agents built on Voiceflow offer a [Dialog Manager API](https://developer.voiceflow.com/reference/overview) which manages conversation state at runtime.

This enables developers to offload the mundane work of managing dialog state machines to the designer who creates and maintains the conversation logic with Voiceflow's graphic design interface. Developers can use the Dialog API for production use cases, or custom interface prototypes, where Voiceflow is hidden in the background. 

Private cloud deployments are [available upon request](https://www.voiceflow.com/demo). The Dialog API can use Voiceflow's NLU, or your own 3rd party or custom NLU to resolve intents.
