---
title: Improving understanding
excerpt: What to do if your assistant isn't understanding properly
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: basic
      slug: response-ai-set-ai
      title: Response AI and Set AI
---
# Understanding hierarchy

Voiceflow has a hierarchy of how it matches to a user's question and what it does if it doesn't understand.

1. **Local Intents**: It first looks to see if you have any intents on the step that the user is on.
2. **Global Triggers**: It then looks to see if what the user said matches any of the global triggers
3. **Local No Match**: If none of the above conditions are met, the agent will follow the ***local no match***
4. **KB Fallback**: If there is no local no match present, then the agent will attempt to answer the question with the Knowledge base
5. **Global No Match**: If the question cannot be answered by the knowledge base, then it will activate the Global no match.

# Matching to the wrong triggers

## How intent matching works

Voiceflow uses AI + NLU to match to a trigger. It operated in the following way.

1. Is what a user said similar to the utterances provided within an intent?
2. From the top 5 intents that have similar utterances — which triggers *description* best matches what the user is trying to accomplish?

## Improving intent matching

If your agent isn't matching to the right triggers, follow the steps below

1. Turn on *Intent Confidence* from the prototype debug menu. This will show you what intent is getting matched too and what the confidence level is.

![](https://files.readme.io/e525572-CleanShot_2024-06-20_at_19.05.182x.png)

2. Add more similar utterances to the correct intent
3. If it's incorrectly matching to an intent, remove utterances from the incorrect intent that are similar to what the user asked
4. Update the descriptions for both intents and include examples (this is what the AI uses to determine what to match too).
5. **As a last resort**: If you still need more fine-tuned control — you can change the AI model and modify the AI prompt that is used to match intent descriptions in the settings on the *intent CMS*. Only do this if you are familiar with prompting, as this may break your assistant. 

   ![](https://files.readme.io/b8554b7-CleanShot_2024-06-20_at_19.07.392x.png)

# Not extracting intents properly

Please note that we are working on releasing an AI powered capture step. In the meanwhile, you can do the following:

## Extending entity capture

If you're finding that a built-in entity like *email* is not capturing certain types of emails — you can extend the training data by clicking the + sign on the entity editor and adding more examples. This will train the model to also look for examples similar to the ones you've added.

![](https://files.readme.io/ac0b061-CleanShot_2024-06-20_at_19.17.072x.png)

## Using AI to extract an entity

If the capture step is not working for your use case, you can use the set AI step to attempt to extract an entity.

* Higher tiered models like GPT-4 Turbo or Claude are often better at extraction tasks
* This method is recommended if the captured entity doesn't follow an expected format (i.e., a username or song title)
* This works best if the AI is provided examples

***See the section on the Response & Set AI steps for more examples of prompt chaining***

![](https://files.readme.io/184984b-CleanShot_2024-06-20_at_19.14.352x.png)
