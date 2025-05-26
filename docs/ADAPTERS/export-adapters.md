---
title: Export Adapters
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Overview

VoiceFlow is an NLU-agnostic Assistant design and development platform. Because of that, you can design any of the core data types required to build a functional assistant and dialogue manager directly with the tools available on your design campus.

If you are designing your Assistants in Voiceflow, and then handing off these designs off to be implemented on a third-party NLU platform, this process can be painful:

- It requires manual context transfer from designers to developers
- Time is wasted manually re-creating data from Voiceflow in another platform
- Iteration is hard because each change requires a new handoff

To address these issues, we recommend that Conversational AI Teams on Voiceflow build an Exporter to adapt all relevant Assistant data created as part of their Voiceflow design process into production-ready data sets.

## What data can be exported?

You can categorize a Voiceflow Assistant into three primary data sets:

1. NLU Model
   - Intents and Training Phrases
   - Entity Types, Values and Synonyms
2. Logic 
   - Intent-based Routes
   - Condition-based Routes
   - Parameters
   - Event Handlers
3. Response Content
   - Agent Responses
   - Webhook Fulfillment

![](https://files.readme.io/bd4b204-Group_36.png)

There is not 1:1 parity between the functionality you can design into an Assistant in Voiceflow and Dialogflow CX. In this guide, we can help identify how to best include the relevant data sets you’re looking to export for production in your designs, using our existing feature sets, and work-arounds where required.

## What is the Export workflow?

When you have a Voiceflow Assistant design ready for export to Dialogflow, the workflow to get your data exported is:

![](https://files.readme.io/4113339-Group_35.png)

### Pull your .VF Project Data: 

Your Voiceflow Assistant data structure is represented in a structured JSON format, that includes the individual data sets, and the relationship between the nodes in your design. You can find a detailed breakdown for the .VF Project JSON structure [here](https://developer.voiceflow.com/docs/voiceflow-project-data-structure). 

This data can be accessed manually via the ‘Share’ menu on your project, by selecting the Export As… > Assistant File Content > Assistant File (JSON) option, or programmatically by calling the [Project API](https://developer.voiceflow.com/reference/fetchproject). 

### NLU Exporter: 

The next step in the workflow is to transform your .VF JSON data into the required data structure