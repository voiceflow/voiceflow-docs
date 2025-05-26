---
title: How Voiceflow's NLU Exports Work
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
Voiceflow offers you the ability to export the native training data direct to your production NLU Platforms. The benefits of utilizing your actual NLU model data in your Voiceflow Assistants are:

1. Kick-start your designs by leveraging your existing NLU data building blocks for your Dialog Designs
2. Maintain parity between the NLU data in your designs and prototypes, and what is being used in your production Assistant
3. Speed up the hand-off of your designs to development by providing production-ready data

### Manual Export

For these Integrations we will create export files pre-formatted for upload directly into your NLU platform. 

### Integrations Supported per NLU

We currently support the following integration methods per NLU platform:

|                     |                    |           |
| :------------------ | :----------------- | :-------- |
| Amazon Alexa        | :white_check_mark: | JSON      |
| Amazon Lex V1       | ✅                  | JSON, ZIP |
| IBM Watson          | ✅                  | JSON      |
| Nuance Mix          | ✅                  | XML       |
| Rasa                | ✅                  | YML, ZIP  |
| Salesforce Einstein | ✅                  | CSV       |
| Voiceflow NLU       | ✅                  | CSV       |

### What data is included in a Voiceflow Assistant

For these integrations, it’s important to know what data gets created on our platform as part of an assistant:

![](https://files.readme.io/d0d2103-image.png)

The three main data types included in a Voiceflow assistant are:

- **NLU Data** - this is all the data needed to train an NLU. This includes intents, utterances/training phrases, entities and entity values
- **Logic Data** - this includes external data sources, variables used to handle data, and conditional logic that defines different paths in the dialog design
- **Response Data** - this includes all content of a response (text, speech, visual, etc.) that an assistant would provide to a user

### What data is included in an NLU Integration

Our Integrations are focused on passing the NLU Data only to your NLU Platform. While some NLU Platforms will house your **Logic Data** and **Response Data**, we will not pass that to your NLU platform as part of our exports.

![](https://files.readme.io/58081a3-image.png)

The specific data types contained within your NLU Exports and Uploads will vary per platform, so here is an overview:

| Platform            | Custom Intents     | Built-in Intents | Utterances | Custom Entities | Built-in Entities | Entity Synonyms |
| :------------------ | :----------------- | :--------------- | :--------- | :-------------- | :---------------- | :-------------- |
| Amazon Alexa        | :white_check_mark: | ✅                | ✅          | ✅               | ✅                 | ✅               |
| Amazon Lex V1       | ✅                  | ✅                | ✅          | ✅               | ✅                 | ✅               |
| IBM Watson          | ✅                  | ❌                | ✅          | ✅               | ❌                 | ✅               |
| Nuance Mix          | ✅                  | ❌                | ✅          | ✅               | ❌                 | ✅               |
| Rasa                | ✅                  | ❌                | ✅          | ✅               | ❌                 | ✅               |
| Salesforce Einstein | ✅                  | ❌                | ✅          | ❌               | ❌                 | ❌               |