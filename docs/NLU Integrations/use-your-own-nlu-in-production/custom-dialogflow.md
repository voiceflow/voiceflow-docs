---
title: Dialogflow ES
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
## Overview

In this guide, we will take a look at how to setup a custom NLU connection between Dialogflow and Voiceflow. 

> 📘 Resources
>
> * [Template source code on Github](https://github.com/zslamkov/voiceflow_dialogflow)
> * [Voiceflow](https://www.voiceflow.com) **Chat Assistant** project

### Detect Intent Function

The below `detectIntent` function is responsible for sending a user utterance to our Dialogflow agent and responding with the triggered intent and any relevant entity values. 

> 🚧 Intents and Entities must match
>
> For any custom NLU connection to work, it is important that your intents and entities in your NLU match what you have stored in your Voiceflow[ Interaction Model](https://developer.voiceflow.com/docs/terminology#interaction-model).

Other data that may be useful in the`DetectIntent` response body include `intentDetectionConfidence` and `languageCode`. For more information of what is available, [see here](https://cloud.google.com/dialogflow/es/docs/reference/rest/v2/DetectIntentResponse).

```javascript detectIntent.js
const detectIntent = async (languageCode, queryText, sessionId) => {
  let sessionPath = sessionClient.projectAgentSessionPath(PROJECTID, sessionId);

  let request = {
    session: sessionPath,
    queryInput: {
      text: {
        text: queryText,
        languageCode: languageCode,
      },
    },
  };
  const responses = await sessionClient.detectIntent(request);
  const result = responses[0].queryResult;

  const confidence = result.intentDetectionConfidence;

  const obj = result.parameters.fields;
  const createIntent = (name, value) => ({ name, value });
  const intents = Object.entries(obj).map(([key, value]) =>
    createIntent(key, value.stringValue)
  );

  return {
    response: result.intent.displayName,
    entities: intents,
    confidence: confidence,
  };
};
```

### Intent Request Type

Finally, we will pass the intent name and entities object into a `type: "intent"` request to return the next action in the conversation.

```javascript intentRequest.json
isRunning = await interact(userID, {
  type: "intent",
  payload: {
    intent: {
      name: intent.response,
    },
    entities: intent.entities,
    confidence: intent.confidence,
  },
}
```

## Project file

```javascript app.js
const dialogflow = require("@google-cloud/dialogflow");
const axios = require("axios");
const { cli } = require("cli-ux");

require("dotenv").config();

const CREDENTIALS = JSON.parse(process.env.CREDENTIALS);
const PROJECTID = CREDENTIALS.project_id;

const CONFIGURATION = {
  credentials: {
    private_key: CREDENTIALS["private_key"],
    client_email: CREDENTIALS["client_email"],
  },
};

const sessionClient = new dialogflow.SessionsClient(CONFIGURATION);

const detectIntent = async (languageCode, queryText, sessionId) => {
  let sessionPath = sessionClient.projectAgentSessionPath(PROJECTID, sessionId);

  let request = {
    session: sessionPath,
    queryInput: {
      text: {
        text: queryText,
        languageCode: languageCode,
      },
    },
  };
  const responses = await sessionClient.detectIntent(request);
  const result = responses[0].queryResult;

  const confidence = result.intentDetectionConfidence;

  const obj = result.parameters.fields;
  const createIntent = (name, value) => ({ name, value });
  const intents = Object.entries(obj).map(([key, value]) =>
    createIntent(key, value.stringValue)
  );

  return {
    response: result.intent.displayName,
    entities: intents,
    confidence: confidence,
  };
};

async function interact(userID, request) {
  // call the Voiceflow API with the user's name & request, get back a response
  const response = await axios({
    method: "POST",
    url: `https://general-runtime.voiceflow.com/state/user/${userID}/interact`,
    headers: {
      Authorization: process.env.API_KEY,
    },
    data: {
      request,
    },
  });

  // loop through the response
  for (const trace of response.data) {
    switch (trace.type) {
      case "text":
      case "speak": {
        console.log(trace.payload.message);
        break;
      }
      case "end": {
        // an end trace means the the Voiceflow dialog has ended
        return false;
      }
    }
  }

  return true;
}

async function main() {
  const userID = await cli.prompt("> What is your name?");
  // send a simple launch request starting the dialog
  let isRunning = await interact(userID, { type: "launch" });

  while (isRunning) {
    const nextInput = await cli.prompt("> Say something");
    // send a simple text type request with the user input
    let intent = await detectIntent("en", nextInput, userID);
    isRunning = await interact(userID, {
      type: "intent",
      payload: {
        intent: {
          name: intent.response,
        },
        entities: intent.entities,
        confidence: intent.confidence,
      },
    });
  }
  console.log("The end! Start me again with `npm start`");
}

main();
```
