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
[block:api-header]
{
  "title": "Overview"
}
[/block]
In this guide, we will take a look at how to setup a custom NLU connection between Dialogflow and Voiceflow. 
[block:callout]
{
  "type": "info",
  "body": "- [Template source code on Github](https://github.com/zslamkov/voiceflow_dialogflow)\n- [Voiceflow](https://www.voiceflow.com) **Chat Assistant** project",
  "title": "Resources"
}
[/block]
###Detect Intent Function

The below `detectIntent` function is responsible for sending a user utterance to our Dialogflow agent and responding with the triggered intent and any relevant entity values. 
[block:callout]
{
  "type": "warning",
  "title": "Intents and Entities must match",
  "body": "For any custom NLU connection to work, it is important that your intents and entities in your NLU match what you have stored in your Voiceflow[ Interaction Model](https://developer.voiceflow.com/docs/terminology#interaction-model)."
}
[/block]
Other data that may be useful in the`DetectIntent` response body include `intentDetectionConfidence` and `languageCode`. For more information of what is available, [see here](https://cloud.google.com/dialogflow/es/docs/reference/rest/v2/DetectIntentResponse).
[block:code]
{
  "codes": [
    {
      "code": "const detectIntent = async (languageCode, queryText, sessionId) => {\n  let sessionPath = sessionClient.projectAgentSessionPath(PROJECTID, sessionId);\n\n  let request = {\n    session: sessionPath,\n    queryInput: {\n      text: {\n        text: queryText,\n        languageCode: languageCode,\n      },\n    },\n  };\n  const responses = await sessionClient.detectIntent(request);\n  const result = responses[0].queryResult;\n\n  const confidence = result.intentDetectionConfidence;\n\n  const obj = result.parameters.fields;\n  const createIntent = (name, value) => ({ name, value });\n  const intents = Object.entries(obj).map(([key, value]) =>\n    createIntent(key, value.stringValue)\n  );\n\n  return {\n    response: result.intent.displayName,\n    entities: intents,\n    confidence: confidence,\n  };\n};",
      "language": "javascript",
      "name": "detectIntent.js"
    }
  ]
}
[/block]
###Intent Request Type
Finally, we will pass the intent name and entities object into a `type: "intent"` request to return the next action in the conversation.
[block:code]
{
  "codes": [
    {
      "code": "isRunning = await interact(userID, {\n  type: \"intent\",\n  payload: {\n    intent: {\n      name: intent.response,\n    },\n    entities: intent.entities,\n    confidence: intent.confidence,\n  },\n}",
      "language": "javascript",
      "name": "intentRequest.json"
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Project file"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "const dialogflow = require(\"@google-cloud/dialogflow\");\nconst axios = require(\"axios\");\nconst { cli } = require(\"cli-ux\");\n\nrequire(\"dotenv\").config();\n\nconst CREDENTIALS = JSON.parse(process.env.CREDENTIALS);\nconst PROJECTID = CREDENTIALS.project_id;\n\nconst CONFIGURATION = {\n  credentials: {\n    private_key: CREDENTIALS[\"private_key\"],\n    client_email: CREDENTIALS[\"client_email\"],\n  },\n};\n\nconst sessionClient = new dialogflow.SessionsClient(CONFIGURATION);\n\nconst detectIntent = async (languageCode, queryText, sessionId) => {\n  let sessionPath = sessionClient.projectAgentSessionPath(PROJECTID, sessionId);\n\n  let request = {\n    session: sessionPath,\n    queryInput: {\n      text: {\n        text: queryText,\n        languageCode: languageCode,\n      },\n    },\n  };\n  const responses = await sessionClient.detectIntent(request);\n  const result = responses[0].queryResult;\n\n  const confidence = result.intentDetectionConfidence;\n\n  const obj = result.parameters.fields;\n  const createIntent = (name, value) => ({ name, value });\n  const intents = Object.entries(obj).map(([key, value]) =>\n    createIntent(key, value.stringValue)\n  );\n\n  return {\n    response: result.intent.displayName,\n    entities: intents,\n    confidence: confidence,\n  };\n};\n\nasync function interact(userID, request) {\n  // call the Voiceflow API with the user's name & request, get back a response\n  const response = await axios({\n    method: \"POST\",\n    url: `https://general-runtime.voiceflow.com/state/user/${userID}/interact`,\n    headers: {\n      Authorization: process.env.API_KEY,\n    },\n    data: {\n      request,\n    },\n  });\n\n  // loop through the response\n  for (const trace of response.data) {\n    switch (trace.type) {\n      case \"text\":\n      case \"speak\": {\n        console.log(trace.payload.message);\n        break;\n      }\n      case \"end\": {\n        // an end trace means the the Voiceflow dialog has ended\n        return false;\n      }\n    }\n  }\n\n  return true;\n}\n\nasync function main() {\n  const userID = await cli.prompt(\"> What is your name?\");\n  // send a simple launch request starting the dialog\n  let isRunning = await interact(userID, { type: \"launch\" });\n\n  while (isRunning) {\n    const nextInput = await cli.prompt(\"> Say something\");\n    // send a simple text type request with the user input\n    let intent = await detectIntent(\"en\", nextInput, userID);\n    isRunning = await interact(userID, {\n      type: \"intent\",\n      payload: {\n        intent: {\n          name: intent.response,\n        },\n        entities: intent.entities,\n        confidence: intent.confidence,\n      },\n    });\n  }\n  console.log(\"The end! Start me again with `npm start`\");\n}\n\nmain();\n",
      "language": "javascript",
      "name": "app.js"
    }
  ]
}
[/block]