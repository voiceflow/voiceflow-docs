---
title: Interact Stream
excerpt: >-
  Sends a request to advance the conversation session with your Voiceflow
  project, recieving a stream of events back.
api:
  file: voiceflow-dialog-management-api.json
  operationId: stateInteractStream
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
This endpoint initiates a streaming interaction session with a Voiceflow agent. Clients connect to this endpoint to receive server-side events (SSE) using the `text/event-stream` format. This allows for real time events during progression through the flow.

Streaming events can be used to drastically improve latency and provide a more natural conversation by sending information to the user as soon as it's ready, instead of waiting for the entire Voiceflow turn to be finished.

<Image align="center" src="https://files.readme.io/0a604aae2fafd21f0037cc20219dce4b92c8f9d28b062a183d34a0c51f23d946-Screenshot_2024-09-23_at_10.39.24_PM.png" />

In the block above, events would be sent as goes: 

* The API immediately sends an event for Message 1 ("give me a moment") 
* Then a long API Call holds up the rest of the answer
* Once the API call is finished, the API  sends an event for Message 2 "got it...".

Streaming allows us to respond first with Message 1 before going into the long API Call (`long-running-api-request`).

From the user's perspective, the agent will respond *"give me a moment..."*, and after the API finishes in 10 seconds, then  *"got it, your flight is booked for..."*. This helps prevent an awkward silence while the API runs in the background and prepares the user to wait for an action to be finished.

Streaming is great for breaking up long-running, blocking steps such as: AI Set/AI Response/Prompt, API, JavaScript, Function, KB Search.

The response is a stream of  `trace` events, which each roughly corresponds with a step on the canvas, sent as the step is invoked. Visit [Trace Types](https://docs.voiceflow.com/reference/trace-types) to learn about the different types of traces.

An Authorization header is required to validate the request. Learn more at: [https://docs.voiceflow.com/reference/authentication](https://docs.voiceflow.com/reference/authentication)

Your `projectID` is also required as part of the URL, find this in the agent settings page:

<Image align="center" width="100% " src="https://files.readme.io/e8387d61979d3f1b9f7c95b5d2e5f9f502704f16f2eb7409fe23b4d31a3b971e-Screenshot_2024-09-26_at_12.05.28_PM.png" />

> Note: this is not the same ID in the URL `creator.voiceflow.com/project/.../`

### Example Request

```curl cURL
curl --request POST \
     --url https://general-runtime.voiceflow.com/v2/project/$PROJECT_ID/user/$userID/interact/stream \
     --header 'Accept: text/event-stream' \
     --header 'Authorization: $VOICEFLOW_API_KEY' \
     --header 'content-type: application/json' \
     --data '
{
  "action": {
    "type": "launch"
  }
}
```

### Example Response

```json Response
event: trace
id: 1
data: {
  "type": "text",
	"payload": {
    "message": "give me a moment...",
  },
  "time": 1725899197143
}

event: trace
id: 2
data: {
  "type": "debug",
  "payload": {
    "type": "api",
    "message": "API call successfully triggered"
  },
  "time": 1725899197146
}

event: trace
id: 3
data: {
  "type": "text",
	"payload": {
    "message": "got it, your flight is booked for June 2nd, from London to Sydney.",
  },
  "time": 1725899197143
}

event: end
id: 4
```

You can check out an example project here using the API: [https://github.com/voiceflow/streaming-wizard](https://github.com/voiceflow/streaming-wizard)

For more details on advanced settings, reference dedicated documentation:

* [completion\_events](https://docs.voiceflow.com/reference/stream-completion-events-1) to stream LLM responses as they are being generated, instead of waiting for the entire response