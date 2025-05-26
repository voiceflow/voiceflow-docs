---
title: Overview
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
The Dialog Manager API (DM API) allows any application to talk with a Voiceflow diagram using HTTP calls  
to the **interact endpoint**.

Conversation State
------------------

The DM API automatically creates and manages the conversation state. Identical requests to the DM API may produce different responses depending on your diagram's logic and the previous request that the API received.

Note that this means the DM API is **not a REST API** as it does not satisfy the [statelessness property](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm). The DM API's responses depend not only on the request, but also stored state within the server. Keep this in mind while working with the DM API.

### Tracking conversation state

All endpoints take in a `userID` parameter, which is used to identify the caller and assign them a unique  
conversation state object.

#### Multiple conversation sessions

Multiple conversation sessions to the same Voiceflow project can be running simultaneously. Each session is identified by the `userID` that you specify. 

For example, customer A should communicate with `/state/user/customerA/interact` whereas customer B should communicate with `/state/user/customerB/interact`. 

When customer A gives a response, such as "I would like a large pizza", it will advance their specific conversation session identified by `/state/user/customerA/interact`. For example, the app might then ask what toppings customer A wants.

Meanwhile, `/state/user/customerB/interact`'s session remains unchanged, e.g, it might be waiting for customer B to give their order. 

#### Format of `userID`

The format of `userID` is up to you. You can choose any string that fits your particular domain such as `user1234` or `507f191e810c19729de860ea`.

There are a few best practices to defining a `userID` format:

1. **Unique** - The `userID` should be unique to each user. Otherwise, if two users share the same `userID`, the Voiceflow app may leak information about user A's conversation to user B, which is a potential privacy violation.

2. **Non-sensitive** - It is not recommended to use sensitive or private information in the `userID` such  
   as emails, real names, or phone numbers. 

versionID
---------

DM API endpoints also accept a `versionID` header whose value is a **version alias** that points to a particular version of your Voiceflow project.

The currently supported aliases are:

- `development` - The version displayed on the Voiceflow Creator's canvas

- `production` - The version that has been published 

Use the `development` alias whenever you are experimenting with your API and the `production` version when integrating Voiceflow with your web app.

### Updating your version

To update the `'development'` version exposed by the DM API, you must:

1. Make your changes on the canvas and NLU manager

2. Hit the blue Run button in the Voiceflow canvas to compile the diagram

3. Hit the "Train Assistant" button in the Prototype tool to train the NLU model

To update the `'production'` version exposed by the DM API, you must:

1. Make your changes on the canvas and NLU manager

2. Hit the Publish button at the top-right corner of the Voiceflow canvas