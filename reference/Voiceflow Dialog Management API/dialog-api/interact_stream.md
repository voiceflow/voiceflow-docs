---
title: (Beta) Interact Streaming
excerpt: ''
api:
  file: streaming-runtime-api.json
  operationId: Interact_stream
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
> 📘 
> 
> This feature is currently in beta as we continue to refine functionalities and enhance performance based on customer feedback and our development roadmap. We appreciate your contributions to help us improve this service.

This endpoint initiates a streaming interaction session with a Voiceflow agent. Clients connect to this endpoint to send and receive server-side events (SSE) using the `text/event-stream` format. This allows for continuous interaction without the need to poll or initiate multiple HTTP requests.

Additionally, the endpoint incorporates a new set of trace types—`completion-start`, `completion-continue`, and `completion-end`—introduced by the Response AI step (excluding KB data source). These trace types facilitate the delivery of text streaming as the large language model (LLM) generates the response message.

#### Example Request

```curl cURL
curl --request POST \
     --url https://general-runtime.voiceflow.com/v2beta1/interact/12345/production/stream \
     --header 'Accept: text/event-stream' \
     --header 'Authorization: $VOICEFLOW_API_KEY' \
     --header 'content-type: application/json' \
     --data '
{
  "action": {
    "type": "launch"
  },
  "session": {
    "userID": "1234",
    "sessionID": "session_123"
  }
}
```

#### Example Response from Response AI step

```json Response
    event: trace
    id: 51af815f-742c-48d2-84fc-adfa54854fba
    data: {
      "type": "trace",
      "trace": {
        "type": "completion-start",
        "payload": {
          "completion": "Welcome to our service.",
          "type": "text",
          "tokens": {
            "model": "gpt-3.5-turbo",
            "answer": 0,
            "query": 2,
            "total": 2
          }
        }
      }
    }

    event: trace
    id: 7fa9477a-0ccd-4e2b-8e30-733ccdf4c455
    data: {
      "type": "trace",
      "trace": {
        "type": "completion-continue",
        "payload": {
          "completion": "How can I help you today?",
          "tokens": {
            "answer": 0,
            "query": 0,
            "total": 0
          }
        }
      }
    }

    event: trace
    id: ba08dc7a-1432-4f9f-b12d-c1b84a325dac
    data: {
      "type": "trace",
      "trace": {
        "type": "completion-continue",
        "payload": {
          "completion": " Perhaps you're interested in our latest offers or need assistance with an existing order?",
          "tokens": {
            "answer": 1,
            "query": 0,
            "total": 1
          }
        }
      }
    }

    event: trace
    id: f4affc6e-f1b7-480d-ad60-5f2bd8a0c60a
    data: {
      "type": "trace",
      "trace": {
        "type": "completion-end",
        "payload": {
          "completion": "Let me know if you have any other questions!",
          "tokens": {
            "answer": 1,
            "query": 0,
            "total": 1
          }
        }
      }
    }
```

You can check out an example project here using the API: <https://github.com/voiceflow/streaming-wizard>