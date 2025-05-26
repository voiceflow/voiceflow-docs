---
title: Hallucinations
excerpt: Learn how to reduce hallucinations when using LLMs in Voiceflow
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
      slug: hallucination-reduction
      title: Hallucination reduction
---
## What are Hallucinations?

Hallucinations in the context of Large Language Models (LLMs) refer to instances where the model generates information that is factually incorrect, nonsensical, or unrelated to the input prompt. These are not intentional fabrications, but rather errors in the model's output that can appear convincingly real. Hallucinations can range from subtle inaccuracies to completely fictional statements, making them particularly challenging to detect and manage.

For example, an LLM might confidently state that "The Eiffel Tower was built in 1898 by the architect Frank Lloyd Wright" when asked about famous landmarks. This statement combines real elements (the Eiffel Tower, Frank Lloyd Wright) but creates a wholly inaccurate claim.

## Why do hallucinations happen?

Hallucinations in LLMs primarily happen because of the fundamental way these models operate — next-token prediction. As discussed earlier, LLMs work by predicting the most likely next word or token based on the given input and their training data. This process can lead to hallucinations. 

Here are a few examples why an LLM may hallucinate.

* **Prediction vs. Accuracy:** LLMs are designed to generate the most probable next token, not necessarily the most accurate one. This means they're outputting what's most likely according to their training data, rather than what's factually correct.
* **Limited Context:** The model only has access to a finite amount of context (the input prompt and its training data), which may not always be sufficient to generate accurate responses.
* **Training Data Biases:** If the training data contains inaccuracies or biases, these can be reflected in the model's outputs.
* **Lack of Real Understanding:** Despite their sophistication, LLMs don't truly understand the content they're generating. They're pattern-matching machines, not reasoning engines.

As a result, when faced with ambiguous prompts or queries about topics not well-represented in their training data, LLMs may generate plausible-sounding but incorrect information (or bullshit as François Chollet says) by combining unrelated pieces of data or extrapolating beyond their training. 

Next, learn to reduce hallucinations.
