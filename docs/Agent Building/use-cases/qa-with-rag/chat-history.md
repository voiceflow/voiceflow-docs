---
title: Memory
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Memory is a great way to provide context for LLMs and prompts. There are three ways to incorporate chat memory into Voiceflow, **automatic** at the step level, with the **vf_memory** variable or **custom** with low level variables.

# Automatic memory

Each Voiceflow AI step allows you to configure memory. Once you have placed your  AI step, you can configure it in the Editor. In the editor, you will have three different options to prompt your Assistant:

![](https://files.readme.io/09de606-image.png)

**Respond with prompt **- When the Step is hit during a user's session, the Prompt you provide will be the only data passed to the LLM to generate a response. This option is useful when you want an LLM to perform a very specific function, or generate a very specific response, and including Memory could mess that up.

**Use Memory and Prompt ** - This will pass only the previous 10 turns of the conversation to the LLM and allow it to response without any guidance from you. This will enable a purely-conversational interaction between the user and your Assistant, without you providing it a specific goal or task. 

**Respond using memory only** - When hit during a user session, the Prompt you provide will be augmented with the previous 10 turns in the conversation, and the LLM will generate a response from both pieces of data. This option is best if you want to enable the most dynamic possible output from the LLM, because this will provide the most context possible for it to inform it's response.(only available on Response AI)

# VF_Memory variable

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/25ddb5e-CleanShot_2024-05-10_at_09.21.502x.png",
        null,
        "Available "
      ],
      "align": "center",
      "caption": "The vf_memory variable in the CMS view"
    }
  ]
}
[/block]


# Low level configuration with last_response and last_utterance

If you need more low level control, can manually construct your memory within the Voiceflow builder, using Voiceflow functions or using Dialog Manager API. 

> 📘 Custom memory is a great way to improve prompt performance especially when building personas

## Voiceflow builder for low level variables

In the builder you can access the `last_utterance` and `last_response` variables either in response steps, or code steps (javascript and functions) an example below or via the API

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a8ce2ad-CleanShot_2024-05-10_at_09.52.462x.png",
        null,
        "Using last_utterance and last_response in Voiceflow step"
      ],
      "align": "center",
      "caption": "Using last_utterance and last_response in Voiceflow step"
    }
  ]
}
[/block]


## Using Voiceflow functions to construct memory variables

Voiceflow functions allow you to build modular and reusable functions with code within the Voiceflow IDE. We create a new variable named _custom_memory_. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6d89e69-image.png",
        null,
        "Defining a custom memory"
      ],
      "align": "center",
      "caption": "Defining a custom memory"
    }
  ]
}
[/block]


We then define a new function map input variables for the `last_utterance`, `last_response`, and our previous `custom_memory` instance, append them and output them. In this example we are building an e-commerce agent.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b98e079-image.png",
        null,
        "Building a custom memory function\n\n"
      ],
      "align": "center",
      "caption": "Building a custom memory function"
    }
  ]
}
[/block]


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f73859a-image.png",
        null,
        "Using a custom memory function and having a conversation"
      ],
      "align": "center",
      "caption": "Using a custom memory function and having a conversation"
    }
  ]
}
[/block]


And that's how to use functions to build custom memory! For more information on functions checkout this documentation [here](https://learn.voiceflow.com/hc/en-us/articles/22213934251533-Functions)

## Using the API to update memory variables

The second approach to build memory is to use the Dialogue Manager API.  

> 📘 Use this approach when you have some custom logic orchestrated outside of Voiceflow or need to enrich the data

In our example we'll make the memory e-commerce specific and inject additional context from our website. We customize the custom_memory variable in the variables section of the request.

```python python
import requests

url = "https://general-runtime.voiceflow.com/state/user/userID"

payload = {
    "stack": [
        {
            "programID": "6062631246b44d80a8a345b4",
            "diagramID": "653fb8df7d32ab70457438f4",
            "nodeID": "60626307fd9a230006a5e289"
        }
    ],
    "variables": {
        "custom_memory": """Clerk: Were there any mugs you were looking at?
        Customer: Yes i liked the blue colour but the style of the rex mug.
        Additional information: The Customer clicked on two items the light blue origin mug and the green rex mug.""",
    }
}
headers = {
    "accept": "application/json",
    "content-type": "application/json"
}

response = requests.put(url, json=payload, headers=headers)

print(response.text)
```

For more details on the dialogue manager API checkout our [api docs](https://developer.voiceflow.com/reference/poststate-1)