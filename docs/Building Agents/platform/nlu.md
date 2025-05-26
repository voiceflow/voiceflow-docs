---
title: Natural Language Understanding (NLU)
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# What is an NLU?

NLU, or Natural Language Understanding, refers to a model designed to manage common tasks in a conversational flow, such as capturing entities and classifying intents. Compared to Large Language Models (LLMs), NLUs are smaller and faster, but may have reduced accuracy.

With Voiceflow, whenever you add intents or entities and train your agent, a base Voiceflow NLU model is fine-tuned to optimally classify your intents and entities based off the examples you give.

# Training your Prototype NLU

## Training Your Prototype (NLU)? How do I train my assistant? How do I train the model?

You can ensure that your Voiceflow conversation prototype is trained with the model (utterances, intents, entities) in your Voiceflow assistant coupled with the analysis, handling & intent/task fulfillment, or NLU (Natural Language Understanding).

Voiceflow will prompt you if your Assistant needs training to create a high-fidelity testing experience. In entering Test mode, you will be prompted or see a display message in the Training window drop-down (above the Dialog window drop-down).

***Tip:** Always train your model after adding or modifying your Intents, Utterances and Entities. This ensures you’re testing with the most up-to-date model, and is best practice.*

![](https://files.readme.io/ec1bf07-CleanShot_2024-06-06_at_10.36.392x.png)

Training is important not only to understand where you can improve your design but also to navigate:

1. the model structure
2. the logic and sounds

The more you build, the more you should be training – and training your most recent model will be the most accurate depiction of your real user experience. Training your NLU is a critical part of creating a high-fidelity testing experience.

With Smart Prototyping & our native NLU/NLP, we now support various new use cases and testing opportunities, in combination with our Voice/Chat Voiceflow Assistants. This will make it easier for designers to test at a higher level of intelligence and teammates/user testers to experience a more representative version of your designs.

## Best Practices with NLU Prototyping

If you edit the overall dialogue model (addition / change / deletion of sample utterances, addition / change / deletion of slots/entities, etc.), you will need **Train Assistant** again.

For optimal performance, you should have at least 5-10 Utterances for each Intent and at least 10 values for your Entities.

# NLU Training Duration

**How long does it take to Train Assistant? How long does training take?**

After you hit **Train Assistant**, it can take up to a few minutes (1-2) to train your assistant. Typically, the timing depends on the number of intents and other conversation logic (intents & entities) in your [Agent CMS](https://developer.voiceflow.com/v2.0/docs/cms).

Upon completion of the training of your assistant's model, you will notice that the **Train Assistant** button is greyed out, and you are now using the highest-fidelity testing for your assistant.
