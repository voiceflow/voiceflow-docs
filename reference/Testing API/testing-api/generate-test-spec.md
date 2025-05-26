---
title: Generate Test Spec
excerpt: >-
  Add a new test spec to your project. This endpoint supports automatic
  transcript generation along with manual transcript upload.
api:
  file: testing-api.json
  operationId: generate-test-spec
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
> 🚧 Testing APIs are currently under Public Preview
>
> To add your project to the Public Preview, contact your customer success manager, or contact the Voiceflow team via the discord channel.

## Example Requests

### Auto Generated Transcripts

By omitting the `transcripts` parameter, they will automatically be generated for you from your Knowledge Base documents.

```json JSON
{
  "data": {
    "name": "gpt vs claude",
    "modelSettings": [
      {
        "model": "claude-instant-v1",
        "temperature": "0.42",
        "maxTokens": "100",
        "systemPrompt": "You are a knowledge base"
      },
      {
        "model": "gpt-3.5-turbo",
        "temperature": "0.42",
        "maxTokens": "100",
        "systemPrompt": "You are a knowledge base"
      }
    ]
  }
}
```

### Manual Transcripts

If you have specific transcripts you'd like to test, supply them via the `transcripts` param in the request body.

```json
{
  "data": {
    "name": "gpt vs claude",
    "modelSettings": [
      {
        "model": "claude-instant-v1",
        "temperature": "0.42",
        "maxTokens": "100",
        "systemPrompt": "You are a knowledge base"
      },
      {
        "model": "gpt-3.5-turbo",
        "temperature": "0.42",
        "maxTokens": "100",
        "systemPrompt": "You are a knowledge base"
      }
    ],
    "transcripts": [
      [
        {
          "role": "user",
          "content": "What teams played in the 2023 nba finals?"
        },
        {
          "role": "assistant",
          "validationOptions": {
            "text": "The Denver Nuggets played against the Miami Heat."
          }
        },
        {
          "role": "user",
          "content": "and who won?"
        },
        {
          "role": "assistant",
          "validationOptions": {
            "text": "The Denver Nuggets won."
          }
        },
        {
          "role": "user",
          "content": "are you sure about that?"
        },
        {
          "role": "assistant",
          "validationOptions": {
            "text": "Yes",
            "matchType": "TextMatch",
            "matchField": "exact"
          }
        }
      ],
      [
        {
          "role": "user",
          "content": "When did the Denver Nuggets win the NBA championship? "
        },
        {
          "role": "assistant",
          "validationOptions": {
            "text": "The Denver Nuggets won the NBA championship in 2023."
          }
        }
      ]
    ]
  }
}
```

## Example Response

```json json
{
  "data": {
    "_id": "6568e78a9942bb09c2ac722a",
    "createdAt": "2023-11-27T09:09:11.159983",
    "updatedAt": "2023-11-27T09:09:11.167664",
    "name": "gpt vs claude",
    "projectID": "653bf84d681dd7000727726c",
    "type": "api",
    "defaultMatchType": "SimilarityScore",
    "defaultMatchField": 0.8,
    "modelSettings": [
      {
        "model": "claude-instant-v1",
        "temperature": "0.42",
        "maxTokens": "100",
        "systemPrompt": "You are a knowledge base"
      },
      {
        "model": "gpt-3.5-turbo",
        "temperature": "0.42",
        "maxTokens": "100",
        "systemPrompt": "You are a knowledge base"
      }
    ],
    "creationSource": "manual"
  }
}
```