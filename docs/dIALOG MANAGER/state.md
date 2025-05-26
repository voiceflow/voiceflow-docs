---
title: State
excerpt: Learn about the components of Voiceflow's state object
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
### Overview

In Voiceflow, a dialogue state is assigned to a unique `userID`. This userID can be any string and is typically something unique that easily references the person on the session - such as an username, email, device ID, or phone number. (e.g. user54646, [user@gmail.com](mailto:user@gmail.com), 1-647-424-4242, etc.). If you're not sure what to call it just for testing purposes, you can just pick a random `{userID}` like steve.

The response schema consists of two main properties:

1. Stack
2. Variables

We will cover each property below.

#### Stack

The stack is an array of flows that are currently active in the conversation. Each flow contains:

* A `programID`: the ID of the flow, which can be found in the URL of the address bar `<https://creator.voiceflow.com/project/{versionID}/canvas/{**programID**>)`
* `nodeID`: current block this flow is on
* `variables`: flow-scoped variables
* `storage`: internal flow parameters for runtime
* `commands`

In the example below, you can see that there are three flows available on the stack (`620e669eac2f70001cf9d85a`, `620e669eac2f70001cf9d85b` and `620e669eac2f70001cf9d85c`) and we are currently sitting on flow `620e669eac2f70001cf9d85c`, as denoted by the `nodeID` pointing to a block within this flow.

**Note:** the `programID` of the first flow in the stack is always the `versionID` of the project.

**Example stack**

```json
"stack": [
        {
            "nodeID": null,
            "programID": "620e669eac2f70001cf9d85a", //<-- versionID of the project
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

#### Variables

The two ways you can create variable keys in your Interaction Model is through:

1. Entities
2. Variables

The difference between **Entities** and **Variables** is how they are assigned values at runtime. An `entity` value is assigned through a user interaction (e.g. utterance) whereas a `variable` is dynamically assigned a value from the design itself based on a user action (e.g. through an API call or custom code).

When creating a new variable, you can also define whether it is a **Global** or **Flow** variable, as shown in the screenshot below. A Global variable persists indefinitely while a Flow variable will exist only as long as the flow is in the stack.

<Image title="Screen Shot 2022-02-27 at 9.24.52 AM.png" alt={795} width="80%" src="https://files.readme.io/58059d2-Screen_Shot_2022-02-27_at_9.24.52_AM.png">
  Global and Flow variables
</Image>

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

### Voiceflow Context Model

In this video, we'll explain Voiceflow's entire Context Model in more detail.

<Embed url="https://www.youtube.com/watch?v=IUp1Kz-2xVY&ab_channel=TylerHan" title="Voiceflow Context Model - Intents, Commands, and Flows" favicon="https://www.youtube.com/s/desktop/ecd7151d/img/favicon.ico" image="https://i.ytimg.com/vi/IUp1Kz-2xVY/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=IUp1Kz-2xVY&ab_channel=TylerHan" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FIUp1Kz-2xVY%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DIUp1Kz-2xVY%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FIUp1Kz-2xVY%252Fhqdefault.jpg%26key%3Df2aa6fc3595946d0afc3d76cbbd25dc3%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />
