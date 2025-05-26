---
title: Intro to Dialog Managers
excerpt: Overview of a Dialog Manager interaction.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
### Overview

A Dialog Manager (DM) is the connective tissue of any conversational AI experience. It is responsible for the state and flow of the conversation.

In this guide, we will be exploring the entire dialogue stack and the crucial role a Dialog Manager plays.

### How dialogue flows

To begin, we will take a closer look at each component of a dialogue stack by following the journey of a spoken user utterance into a voice-enable device:

`"Hello, I would like to check the shipping status of my Blue Jays baseball cap"`

#### Speech Recognition

When the input is a spoken utterance (an audio file), the first step is to convert it to unstructured text using speech-to-text software (STT). 

#### Natural Language Understanding

The unstructured text is then passed into a natural language understanding (NLU) layer to transform it into a representation that is understandable by a program. The NLU serves three main functions:

- Domain Identification: Determine which domain is best served to understand the utterance
- User Intent Detection: Classify the user's intent by analyzing utterance. 
- Slot filling: Identifies span of words in an utterance that correspond to certain parameters (slots or entities) of the utterance.

In the case of our example utterance, we might expect to trigger an intent named `shipping` with a training phrase that looks like this `I want shipping status of {product}`, where the output looks something to below:

```json
"intent": {
        "name": "shipping"
      },
"entities": {
        "product": "blue jays baseball cap"
      }
```



#### Dialog Manager

The NLU output will now be used to make a request of the DM to determine the next action in the conversation. 

The two main tasks of a DM is managing conversation `state` and the `design`:  

- **Conversation state**: Keeping track of conversation history and variables
- **Conversation design**: Making decisions about the next action. 

We will briefly cover both tasks below to help understand the importance of each.

**Conversation state**  
Conversation state is a critical component for any **contextual** conversation. State data typically includes a record of where a user is in their conversation, system variable like `last utterance`, `user ID`, and `locale`, and hardcoded variable/entities set by the conversation designer to populate with values at runtime.   

> 📘 
> 
> Learn more about Voiceflow's context model [here](https://developer.voiceflow.com/docs/state).

**Conversation design**  
The conversation design involves deciding what to do next in the context of the current conversation state. The next step may include prompting for verification or outputting some content. The conversation logic is typically completed at design time, with conversation turns determined by factors such as the values available via the conversation state. For example, using our sample utterance, we may ask the user to verify the `order number` if they have more than one baseball cap out for delivery before proceeding to the next step.

WIth the above definitions in mind, let's continue along the dialogue flow with our example. 

When the request is made to the DM, we will assume that a unique `customer ID` was also passed into the header of the request which is associated with a contact on our third-party shipping service. Once the DM receives the request with the NLU data and `customer ID`, it will (1) populate the conversation state variable of `product` with the entity value of the same name and (2) populate the variable of `userID` with the `customer ID`, and (3) finally check where the user is at in the conversation. Based on this, the conversation state object may look something like below:

```json state.json
{
    "position": [
        {
            "flowID": "shipping_status",
        }
    ],
    "variables": {
        "product": "blue jays baseball cap",
        "userID": "1234",
    }
}
```



Next, based on the current state, the conversation design will (1) send an API request to the third-party shipping service with the `userID` and the `product` to receive a response with the shipping status. In this case, let's say the shipping status returned is "Out for delivery", which will also be saved as a value for the state variable `shipping_status`. Below is the updated state:

```json state.json
{
    "position": [
        {
            "flowID": "shipping_status",
        }
    ],
    "variables": {
        "product": "blue jays baseball cap",
        "userID": "1234",
        "shipping_status": "Out for delivery"
    }
}
```



At last, we land on the final step in the design which is to return the shipping status (`"Out for delivery"`) to the user. The output of the DM is a list of instructions to other parts of the dialog system to complete the dialog journey.

#### Natural Language Generation

In more technical dialogue systems, there may be an isolated natural language generation (NLG) tool that is responsible for taking an output from a DM, typically in a semantic representation (program-readable), which is then converted to human language within the NLG software. Today, many conversational AI providers include a highly-abstracted NLG in their tool for ease of use.

The output from the NLG to expect will be a text response that may look something like `"Your order is {out for delivery}"`,

#### Text-to-Speech

Finally, as this is a voice assistant, we will need to pass our text response through a text-to-speech service to build an audio file that can be sent back to the user. This is also where any SSML tags, if introduced by the NLG, will be used for the generation of synthetic speech.

#### The Response

The user will now hear **"your order is out for delivery" ** on their voice-enable device! Congratulations on making it through a full dialogue roundtrip between a human and a conversational assistant. 

Now, conversations are rarely limited to a single interaction like our example above; it is much more common to have many interactions that span across domains, topics and even various natural language tools. Imagine how important a Dialog Manager becomes, as the only stateful component of the dialogue system, when building truly assistive conversational experience.