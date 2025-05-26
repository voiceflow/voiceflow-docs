---
title: List Test Runs
excerpt: List all test runs in the given project.
api:
  file: testing-api.json
  operationId: list-test-spec-runs
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

The surface level information for your test runs will be returned. For a detailed view of a given test run, check the Get Test Run Endpoint.

```json json
{
  "data": [
    {
      "id": "testRunID1",
      "testSpecID": "testSpecID",
      "status": "SUCCESS"
    },
    {
      "id": "testRunID2",
      "testSpecID": "testSpecID",
      "status": "PENDING"
    },
    {
      "id": "testRunID3",
      "testSpecID": "testSpecID",
      "status": "ERROR"
    },
  ]
}
```
