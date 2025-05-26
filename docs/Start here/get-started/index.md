---
title: Quick Start Guide
excerpt: Use our APIs to launch to any channel or to build a custom production workflow
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
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
> Voiceflow lets teams build, test, and launch AI Agents to any channel, for any use case.
>
> **APIs**
>
> Voiceflow offers a suite of APIs to launch and host AI Agents, as well as build custom tools, interfaces and workflows on-top of Voiceflow.
>
> **Popular APIs include:**
>
> * **[Dialog API](https://developer.voiceflow.com/reference/overview):** launch your Agent with hosted dialog state management
> * **[Knowledge Management API](https://developer.voiceflow.com/reference/post_v3alpha-knowledge-base-docs-upload):** manage Knowledge Base data with a CRUD API
> * **[Knowledge Query API](https://developer.voiceflow.com/reference/post_knowledge-base-query):** query your managed Knowledge Base
> * **[Project API](https://developer.voiceflow.com/reference/fetchproject):** query content from your Voiceflow Agent design represented in JSON
> * **[Analytics API](https://developer.voiceflow.com/reference/queryusage):** retrieve Agent usage data
> * **[Transcripts API](https://developer.voiceflow.com/reference/fetchtranscripts)** retrieve end-user conversation transcripts
> * **[NLU API](https://developer.voiceflow.com/reference/post_publish-projectid)** train and run inference on VFNLU
>
> These APIs can be used together with Voiceflow's Agent building platform to create custom solutions.
>
> **Popular solutions include:**
>
> 1. **Single Source of Truth:** Use the Voiceflow Agent Builder as a single-source of truth for Agent designs, programmatically retrieving structured design content (JSON) with the [Project API](https://developer.voiceflow.com/reference/fetchproject)
> 2. **Build and Launch:** build low-code with the Agent builder, deploy with the [Dialog API](https://developer.voiceflow.com/reference/overview)
> 3. **Managed Knowledge Base:** use the [Knowledge Base Management API](https://developer.voiceflow.com/reference/post_v3alpha-knowledge-base-docs-upload) and [Knowledge Base Query API](https://developer.voiceflow.com/reference/post_knowledge-base-query) to act as a managed Knowledge Base service
>
> **Quick Launch**
>
> We have a few built-in integrations and let you deploy to a channel like Webchat, WhatsApp, SMS, and Microsoft Teams quickly with minimal code. These are fast but are limited in customizability.
>
> **Custom Launch**
>
> Using our Dialog API directly gives you the flexibility to launch to any channel. These code samples and others on our [github](https://github.com/voiceflow/demos-n-examples) provide a starting point to launch to a custom channel.

# How Voiceflow works

Voiceflow is a collaborative tool that features a powerful collaborative low-code AI Agent building platform. Agents built with Voiceflow are represented by structured [JSON files called .VF files](https://developer.voiceflow.com/docs/voiceflow-project-data-structure).

The below Voiceflow Agent design is an example of what is structured using the .VF JSON file.

![](https://files.readme.io/266dbbc-small-CleanShot_2023-05-01_at_22.58.00.png)

You can find Voiceflow's Agent design platform documentation [here](https://learn.voiceflow.com/hc/en-us/articles/14538287359629-Introducing-Voiceflow-Docs-and-Guides).

## Launch your assistant directly

Agents built on Voiceflow offer a [Dialog API](https://developer.voiceflow.com/reference/overview) which manages conversation state at runtime.

This enables developers to offload the mundane work of managing dialog state machines to the designer who creates and maintains the conversation logic with Voiceflow's graphic design interface. Developers can use the Dialog API for production use cases, or custom interface prototypes, where Voiceflow is hidden in the background. 

Private cloud or premises Dialog Manager deployments are [available upon request](https://www.voiceflow.com/demo). The Dialog API can use Voiceflow's NLU, or your own 3rd party or custom NLU to resolve intents.

## Build a custom production workflow

Agents built on Voiceflow act as a headless CMS as the Agents content and structure can be pulled at any moment using the [Project API](https://developer.voiceflow.com/reference/fetchproject).

For teams with large custom Agents on legacy NLU platforms, the design-development hand-off can be a pain due to design work being done with spreadsheets and misc flowcharts. 

Voiceflow allows non-technical team-members to design, test and iterate on Agent content **while developers can pull the structured JSON content**. 

This means that developers don't need to re-create an assistant from scratch and can instead focus on custom integrations.

> 📘 Custom actions
>
> You can add [Custom Actions](https://developer.voiceflow.com/reference/custom-actions-1) to Voiceflow's design canvas for your non-technical team-members to use and represent any functionality not natively represented in Voiceflow.

## Working with Voiceflow's APIs

Once an Agent has been built on Voiceflow, there are two options for deployment:

1. **[Dialog API](https://developer.voiceflow.com/reference/overview):** run the Agent's state management, and NLU through Voiceflow's Dialog API
2. **[Project API](https://developer.voiceflow.com/reference/fetchproject):** pull content from the Agent design by API, effectively using Voiceflow as a CMS

Alternatively, Voiceflow offers one-click integrations with many channels that allow for no or low-code deployment options. These are called Channel Integrations.
