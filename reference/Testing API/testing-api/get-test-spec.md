---
title: Get Test Spec
excerpt: Get details of a given test spec.
api:
  file: testing-api.json
  operationId: get-test-spec
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

## Example Response

```json json
{
  "data": {
    "_id": "6561158523123f9ff39f2e89",
    "createdAt": "2023-11-27T09:09:11.159983",
    "updatedAt": "2023-11-27T09:09:11.167664",
    "name": "Retirement Conversations",
    "projectID": "653bf84d681dd7142727726g",
    "documentIDs": [
      "655f755a7d3f628bc6bdf0c3",
      "6560e328c806dacf3beadd61",
      "6560ab37d7de27af2292179a",
      "655f792d7d3f628bc6bdf0c4",
      "6560e328c806dacf3beadd63",
      "6560d8c9c806dacf3beadd5d",
    ],
    "generationStatus": "SUCCESS",
    "type": "api",
    "defaultMatchType": "SimilarityScore",
    "defaultMatchField": 0.8,
    "modelSettings": [
      {
        "model": "claude-instant-v1",
        "temperature": 0.42,
        "maxTokens": 101,
        "systemPrompt": "You are a friendly customer service agent.",
      }
    ],
    "transcripts": [
      {
        "_id": "655e2ae8c7f7ed9e4f729fe6",
        "documentID": "6553c090c7e8db0008bc50e4",
        "items": [
          {
            "role": "user",
            "content": "When should I begin saving for retirement?",
          },
          {
            "role": "assistant",
            "validationOptions": {
              "text": "It's never too early to start saving for retirement. This may make saving and planning for retirement easier than starting to save later in your career.",
            },
          },
        ]
      },
    ],
    "description": "Some general retirement transcripts",
    "tokenUsage": 500,
    "creationSource": "generated",
  }
}
```