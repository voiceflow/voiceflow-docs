---
title: Update Test Spec
excerpt: Update an existing test spec.
api:
  file: testing-api.json
  operationId: update-test-spec
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

## Example Request

```json
{
  "data": {
    "name": "this is a new test name",
    "description": "this is a new test description",
    "modelSettings": [
      {
        "model": "gpt-3.5-turbo",
        "temperature": "0.42",
        "maxTokens": "150",
        "systemPrompt": "Respond in English and answer the question."
      }
    ]
  }
}
```

## Example Response

```json json
{
  "data": {
    "_id": "6564a30718bdf17894a332ff",
    "createdAt": "2023-11-27T09:09:11.159983",
    "updatedAt": "2023-11-27T09:09:11.167664",
    "name": "this is a new test name",
    "projectID": "653bf84d681dd7000727726c",
    "generationStatus": "SUCCESS",
    "type": "api",
    "defaultMatchType": "SimilarityScore",
    "defaultMatchField": 0.8,
    "modelSettings": [
      {
        "model": "gpt-3.5-turbo",
        "temperature": "0.42",
        "maxTokens": "150",
        "systemPrompt": "Respond in English and answer the question."
      }
    ],
    "transcripts": [
      {
        "_id": "655e2ae8c7f7ed9e4f729fe6",
        "documentID": "6553c090c7e8db0008bc50e4",
        "items": [
          {
            "role": "user",
            "content": "What is the largest city in Florida?",
          },
          {
            "role": "assistant",
            "validationOptions": {
              "text": "Jacksonville is the largest city in Florida."
            },
          }
        ]
      }
    ],
    "description": "this is a new test description",
    "tokenUsage": 0,
    "creationSource": "manual",
  }
}
```
