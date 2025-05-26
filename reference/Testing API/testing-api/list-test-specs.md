---
title: List Test Specs
excerpt: List all test specs in the given project.
api:
  file: testing-api.json
  operationId: list-test-specs
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
    "data": [
        {
            "id": "655e2ad2c7f7ed9e4f729fg1",
            "name": "Student Account Questions",
            "generationStatus": "SUCCESS"
        },
        {
            "id": "655h2e5n671b509256015d39",
            "name": "Retirement Conversations",
            "generationStatus": "SUCCESS"
        },
      	{
            "id": "655h2m7m671c129255015b40",
            "name": "Tricky KB Transcripts",
            "generationStatus": "PENDING"
        }
    ]
}
```
