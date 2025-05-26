---
title: Interact
excerpt: >-
  The stateless API receives a request with `action` + `state`, and responds
  with a new `state` + `trace`. Here's what it looks like from the Voiceflow
  creator app prototype tool:


  1. User says/types something, take user's text request and current `state` and
  sends it via webhook to the Dialog Management API.

  2. Dialog Management goes through each block/flow and updates the user
  `state`.

  3. Generate a `trace` and new `state` of the user, send back response.

  4. Client interprets API response, and saves the new `state` to use with the
  next response.


  Repeat all steps each time a user speaks/types to the prototype tool, to
  perform a conversation.


  Let's take a look at this interaction: the blue user text is the request.

  <img
  src="https://user-images.githubusercontent.com/5643574/105523483-6c894d80-5cac-11eb-900c-076ed15c1486.png"
  />


  The simplified example stateless **request**


  ```

  {
    "action": {
      "type": "text",
      "payload": "What is the balance in my chequing account"
    },
    "state": {
      "stack": [{
        "programID": "home flow",
        "nodeID": "prompt node"
      }],
      "storage": {},
      "variables": {
        "chequing_balance": null
      }
    }
  }

  ```


  The simplified example **response**


  ```

  {
    "state": {
      "stack": [{
        "programID": "home flow",
        "nodeID": "yes no choice node"
      }],
      "storage": {},
      "variables": {
        "balance": 0
      }
    },
    "trace": [{
      "type": "speak",
      "payload": {
        "type": "message",
        "message": "the balance in your chequing account is 0 dollars, is that all?"
      },
    }, {
      "type": "choice",
      "payload": {
        "choices": [{"name": "yes"}, {"name": "no"}]
      }
    }],
  }

  ```


  Notice that the `type: text` request got processed by the NLP handler to
  become an `type: intent` request.

  The `state` is updated, and a `trace` is generated in the API response.


  To move the conversation forward, you can create an action object and pass it
  in the response body to `/interact` along with the state and optionally a
  `config` object.

  This will return an updated `state`, an updated `action` (not shown in
  examples), and the trace array containing the traces to display.


  if `state` is undefined/empty, it will automatically use the **default state**
  (starting from the first block).
api:
  file: voiceflow-dialog-management-api-2.json
  operationId: statelessInteract
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---