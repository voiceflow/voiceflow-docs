---
title: Interact
excerpt: >-
  Sends a request to advance the conversation session with your Voiceflow
  project.


  ### Requests

  There are different types of requests that can be sent. To see a list of all
  request types, check out the documentation for the `action` field below.


  To start a conversation, you should send a **launch request**. Then, to pass
  in your user's response, you should send a **text request**. If you have your
  own NLU matching, then you may want to directly send an **intent request**.


  See the Request **Examples** on the right panel for more examples of valid
  request bodies.


  ### Response Traces

  After processing your request, the Dialog Manager API will then respond with
  an array of "traces" which are pieces of the overall response from the
  project:

  ```json

  [{
    "type": "speak",
    "payload": {
      "type": "message",
      "message": "would you like fries with that?"
    }
  }, {
    "type": "visual",
    "payload": {
      "image": "https://voiceflow.com/pizza.png"
    }
  }]

  ```

  In the example above, the Voiceflow project responded by saying "would you
  like fries with that?" and an image of a pizza. You can then display the
  chatbot's response and the image in your app.


  There are many types of response traces. Each trace is produced by a
  particular block on your Voiceflow project. Expand the documentation for the
  200 OK response below to see a list of possible response traces.


  ### Legacy responses

  For legacy compatibility, you set the `verbose` query parameter to `true` to
  get a response similar to our legacy Stateless API.


  ```json

  // <- simplified verbose response body {
    "state": {
      "stack": [{
        "programID": "home flow",
        "nodeID": "yes no choice node"
      }],
      "storage": {},
      "variables": {
        "pizza_type": "pepperoni"
      }
    },
    "trace": [{
      "type": "speak",
      "payload": {
        "type": "message",
        "message": "would you like fries with that?"
      }
    }, {
      "type": "visual",
      "payload": {
        "image": "https://voiceflow.com/pizza.png"
      }
    }]
  }

  ```
api:
  file: voiceflow-dialog-management-api.json
  operationId: stateInteract
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---