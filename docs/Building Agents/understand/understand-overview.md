---
title: Overview
excerpt: Understanding is how your agent captures and interprets information.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
In building an AI agent, being able to capture and understand intents and information is crucial. An agent's understanding involves a few different processes.

1. **Basic User Input**: Using [buttons](https://developer.voiceflow.com/v2.0/docs/buttons) or [capturing](https://developer.voiceflow.com/v2.0/docs/capture) their whole responses.
2. **[Intent Recognition](https://developer.voiceflow.com/v2.0/docs/intents):** Understanding what a user wants to do. 
3. **[Entity Extraction](https://developer.voiceflow.com/v2.0/docs/entities):** Extracting specific information from a user's input.

In Voiceflow, we use both Natural Language Understanding (NLU) and Large Language Models (LLMs) to accomplish these. Intent and entity extraction are often used together, like in the example below. To learn more about how they are different, see [Intents vs Entities](https://developer.voiceflow.com/v2.0/docs/intents-vs-entities).

![](https://files.readme.io/f2ab34a-CleanShot_2024-06-07_at_13.27.112x.png)

These technologies help in accurately capturing user intent and information, which is foundational for any effective assistant. Optimizing this process becomes **increasingly important** as the complexity and volume of interactions grow.

This section walks you through how to use steps to capture information in your AI agent with Voiceflow and how to optimize it, from basic input to advanced user understanding.

# How Voiceflow matches to triggers and intents

## Overview

The LLM-based intent classifier introduces a novel hybrid methodology, blending traditional Natural Language Understanding (NLU) with the expansive capabilities of Large Language Models (LLMs) to classify user intents. This synthesis allows for the precision and targeted understanding of NLU with the contextual breadth and depth provided by LLMs, delivering a robust and nuanced approach to intent recognition.

![](https://files.readme.io/5c2cbc6-image.png)

## Key Features

- **Efficient Agent Building**: Unlike traditional models that require extensive datasets for training, our approach necessitates only a handful of sample utterances and an intent description. This streamlined process reduces the workload and accelerates the development of sophisticated conversational agents, enabling teams to focus on refining interactions rather than compiling large datasets.
- **Performance Enhancement**: Leveraging LLMs significantly improves intent recognition accuracy, enabling the system to understand and classify a wide array of user intents with minimal ambiguity. This results in more relevant and accurate responses, enhancing user interaction quality.
- **Predictability Through Hybrid Approach**: By combining the strengths of LLMs with traditional NLU techniques, this feature offers a balanced and predictable approach to intent classification. This hybrid model ensures reliability in classification while embracing the advanced capabilities of LLMs for context understanding and ambiguity resolution.
- **Customization Flexibility**: The system is designed with customization at its core. Developers can modify the prompt wrapper code to perfectly align with their specific use case, allowing for a tailored conversational experience that meets the unique needs of their application.

> 📘 Example template
> 
> Download our Banking Agent template [here](https://drive.google.com/uc?export=download&id=1hNdxZ4KSiBWVO0R8l7vCNVFmsQsiLKG_) to start testing immediately.