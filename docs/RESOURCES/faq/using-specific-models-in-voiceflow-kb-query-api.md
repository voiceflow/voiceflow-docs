---
title: Using Specific Models in Voiceflow KB Query API
excerpt: >-
  This FAQ guide will help you understand how to use specific language models
  when querying the Voiceflow Knowledge Base API.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## How do I specify a particular language model for my query?

Use the `settings` object in your request body, and set the `model` property to your desired model name.

## What does the settings object look like for specifying a model?

Here's an example of how to structure your settings object:

```json
{
  "settings": {
    "model": "gpt-4-turbo"
  }
}

```

## Which models are available to choose from?

The following models are currently available:

- gpt-3.5-turbo
- gpt-4-turbo
- gpt-4
- claude-instant-v1
- claude-v1
- claude-v2
- claude-3-haiku
- claude-3-sonnet
- claude-3.5-sonnet
- claude-3-opus
- gemini-pro-1.5

## What's the default model if I don't specify one?

If you don't specify a model, the API will use the model you choose in the KB settings.

## Can I change other settings along with the model?

Yes, you can also set the `temperature` and provide a custom `system` message in the same settings object.

## How would a complete request look with a specific model?

Here's an example of a complete request specifying a model:

```json
{
  "question": "What are the benefits of AI?",
  "settings": {
    "model": "gpt-4-turbo",
    "temperature": 0.2
  }
}
```

## Will using a different model affect my token usage?

Yes, different models may consume different amounts of tokens, which can affect your usage and costs. Be sure to monitor your token consumption when switching between models.

## Are all models equally suitable for all types of queries?

No, some models may perform better for certain tasks. It's best to experiment and choose the model that gives the best results for your specific use case.

***

Remember to always refer to the latest API documentation for the most up-to-date information on available models and features.