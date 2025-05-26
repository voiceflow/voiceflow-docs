---
title: Understanding the dialog state stack
excerpt: Learn about the components of Voiceflow's state object
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Overview

In Voiceflow, a dialog state is assigned to a unique `userID`. This userID can be any string and is typically something unique that easily references the person on the session - such as an username, email, device ID, or phone number. (e.g. user54646, [user@gmail.com](mailto:user@gmail.com), 1-647-424-4242, etc.). If you're not sure what to call it just for testing purposes, you can just pick a random `{userID}`.

The response schema consists of two main properties:

1. Stack
2. Variables

We will cover each property below, as well as an overview of the Voiceflow context model.

## Stack

The stack is an array of flows that are currently active in the conversation. Each flow contains:

- A `programID`: the ID of the flow, which can be found in the URL of the address bar `<https://creator.voiceflow.com/project/{versionID}/canvas/{**programID**>)`
- `nodeID`: current block this flow is on
- `variables`: flow-scoped variables
- `storage`: internal flow parameters for runtime
- `commands`

In the example below, you can see that there are three flows available on the stack (`620e669eac2f70001cf9d85a`, `620e669eac2f70001cf9d85b` and `620e669eac2f70001cf9d85c`) and we are currently sitting on flow `620e669eac2f70001cf9d85c`, as denoted by the `nodeID` pointing to a block within this flow.

**Note:** the `programID` of the first flow in the stack is always the `versionID` of the <<glossary:Agent>>.

**Example stack**

```json
"stack": [
        {
            "nodeID": null,
            "programID": "620e669eac2f70001cf9d85a", //<-- versionID of the agent
            "storage": {},
            "commands": [],
            "variables": {}
        },
        {
            "nodeID": null,
            "programID": "620e669eac2f70001cf9d85b", //<-- starting flow
            "storage": {
                "output": [
                    {
                        "children": [
                            {
                                "text": "What size?"
                            }
                        ]
                    }
                ]
            },
            "commands": [],
            "variables": {}
        },
        {
            "nodeID": "61f40992f0e4e70a1f2328d1",
            "programID": "620e669eac2f70001cf9d85c",//<-- top-level flow
            "storage": {
                "outputMap": null,
                "output": [
                    {
                        "children": [
                            {
                                "text": "You can get an additional pizza for half the price today. Would you like to do that?"
                            }
                        ]
                    }
                ]
            },
            "commands": [],
            "variables": {
            			"discount_code": "DEAL4TWO"
            }
        }
```

## Variables

The two ways you can create variable keys in your Interaction Model is through:

1. Entities
2. Variables

The difference between **Entities** and **Variables** is how they are assigned values at runtime. An `entity` value is assigned through a user interaction (e.g. utterance) whereas a `variable` is dynamically assigned a value from the design itself based on a user action (e.g. through an API call or custom code).

**Variable examples** 

```json global_variables
"variables": {
        "type": "pepperoni",
        "size": "large",
        "amount": 6,
        "sessions": 0,
        "user_id": "1234",
        "timestamp": 1645112935,
        "platform": 0,
        "locale": 0,
        "side": 0,
        "intent_confidence": 100,
        "last_utterance": "large"
    }
```
```json flow_variable
{
            "nodeID": "61f40992f0e4e70a1f2328d1",
            "programID": "620e669eac2f70001cf9d85c",//<-- top-level flow
            "storage": {
                "outputMap": null,
                "output": [
                    {
                        "children": [
                            {
                                "text": "You can get an additional pizza for half the price today. Would you like to do that?"
                            }
                        ]
                    }
                ]
            },
            "commands": [],
            "variables": {
            			"discount_code": "DEAL4TWO" //<-- flow-scoped variable
            }
```

## Voiceflow Context Model

In this video, we'll explain Voiceflow's entire Context Model in more detail.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FIUp1Kz-2xVY%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DIUp1Kz-2xVY&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FIUp1Kz-2xVY%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=IUp1Kz-2xVY&ab_channel=TylerHan",
  "title": "Voiceflow Context Model - Intents, Commands, and Flows",
  "favicon": "https://www.youtube.com/s/desktop/ecd7151d/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/IUp1Kz-2xVY/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=IUp1Kz-2xVY&ab_channel=TylerHan"
}
[/block]