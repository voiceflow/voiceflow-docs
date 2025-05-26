---
title: What are LLMs?
excerpt: Learn what Large Language Models are, and how you can use them in your builds.
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
      slug: prompting
      title: Prompting
---
## What is an LLM?

Large Language Models (LLMs) are a type of deep learning model designed to understand and generate human language. They are trained on vast amounts of text data, allowing them to learn the intricacies of language structure, syntax, and semantics.

## How does an LLM work?

LLMs work using a concept called next-token prediction. Essentially, the model tries to predict the most likely word or token that follows a given sequence of words by learning from patterns in the training data.

During training, the model is fed a sequence of words and tries to predict the next word in the sequence. The model learns and adjusts its internal parameters by comparing its predictions to the next word. This process is repeated millions of times on a massive dataset, allowing the model to build a deep understanding of language.

Most LLMs use a Transformer architecture. Transformers are designed to process sequential data, like text, by paying attention to different parts of an input sequence. This allows the model to understand the context and relationships between words.

For example, consider the phrase: "Check the deposit."

This phrase could have multiple interpretations depending on the context:

In banking, it might mean "Verify that a deposit has been made."  
In geology, it could mean "Examine the sedimentary deposit."  
Gambling might mean, "Look at the money that's been bet."

A Transformer would process this phrase by paying attention to surrounding words and context:

If the preceding text mentions a bank account, the model would likely interpret "check" as a verb meaning "to verify" and "deposit" as a noun referring to money added to an account.  
If the text discusses rock formations, the model might interpret "check" as "examine" and "deposit" as a geological formation.  
If the context is about a casino, the model could interpret "check" as "look at" and "deposit" as the money placed for a bet.

This attention mechanism allows the Transformer to understand not just the words themselves but their meaning in context. Based on the surrounding information, it can differentiate between "check" as a verb or a noun and "deposit" as money or sediment.

By processing text this way, Transformers can handle ambiguous language much more effectively than simpler models (Like a Natural Language Understanding (NLU) engine), making them particularly well-suited for complex language tasks requiring a nuanced understanding of context.

To start using Large Language Models in Voiceflow, it's time to learn about Prompting.