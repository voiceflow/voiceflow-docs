---
title: Set AI step
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
> 🚧
>
> We encourage all users to use the prompt type in the [Set step](https://docs.voiceflow.com/docs/variables-set) moving forward to perform dynamic variable setting.

The Set AI step let you leverage the power of LLMs like GPT 4 to do reasoning and prompt chaining.

## Response or Set AI?

* **Response AI**: This displays the AI response *directly* to the customer. You can select the Knowledge base or the AI model directly as the data source. This supports Markdown formatting. You can learn more about it [here](https://developer.voiceflow.com/v2.0/docs/response-ai).
* **Set AI**: This saved the AI response to a *variable*. So the user never sees it. Mastering the Set AI step is key to developing an advanced agent, as it allows you to do *prompt chaining*.

Both steps can either directly use models, or also respond using your [Knowledge Base](https://developer.voiceflow.com/v2.0/docs/knowledge-base).

## Configuring your Set AI step

Since the prompt part of the Set AI step is almost identical to the Response AI step, you can see its documentation [here](https://developer.voiceflow.com/v2.0/docs/response-ai).

The only important difference is that you can run multiple Set AI steps in **parallel** (at the same time). They will all share the same system prompt and model, but can have different instructions. This does mean though that you shouldn't use the output of one  set into another in the same step.

![](https://files.readme.io/21c3b1c-image.png)

## Prompt chaining

Prompt chaining is a method to get an AI to follow a chain of thought by passing an LLM output into the input of another LLM, with another prompt around it. 

Prompt chaining is easy to do in Voiceflow with a chain of Set AI steps. 

This can be done to reduce hallucinations, for example, by getting the AI to double-check itself and write corrections if necessary. For a great example of prompt chaining, see the video below.

<Embed url="https://www.youtube.com/watch?v=BHxhFd1vqkg" title="Removing Hallucinations for a Wells Fargo Customer Support Banking Agent | Making Bots" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/BHxhFd1vqkg/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=BHxhFd1vqkg" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FBHxhFd1vqkg%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DBHxhFd1vqkg%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FBHxhFd1vqkg%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## Output parsing

Sometimes we might want to use an LLM to drive the logic inside our agent, like choosing a path to go down or select an option from a list. A prompt (from our [Unity NPC demo](https://youtu.be/-_grpoO6AJ0?si=XYztfP4ZsOu7lLOX)) could look like:

```
Based off the message, choose an appropriate face sprite from the list for the character who is speaking it to have on. Be emotive and like an actor, and be very creative in choosing, and lean into the Climber's emotions.

#CHOICES

normal
distracted
angry
panic
sad
suprised
upset
phone

#CLIMBER MESSAGE YOU'RE REACTING TO 

{last_utterance}


#REACTION MESSAGE TO CLASSIFY

{split_sentence}


#INSTRUCTION

Simply answer back with the choice from the list. For example, in response to talking about a gift, you respond: suprised.

Now take a deep breath. Do not answer with anything else other than the choice. 

#CHOICE
```

We would like to get out only the choice, but the LLM might answer something like `The face to choose is: normal`, even thought we told it not to.

In this case, you should do some parsing on the LLM's output. Effective methods include:

* Searching for if the output *includes* one of a set of expected options. If you're looking for 0 or 1, instead of checking that the output is equal to “0”, check if it contains “0”.
* Ask the LLM to wrap its answer in predicable characters. Often, using backticks (\`) is effective. You can then use a [JavaScript step](https://developer.voiceflow.com/v2.0/docs/javascript-step) to extract the string between backticks.
