---
title: Run Test Spec
excerpt: Run an existing Test Spec
api:
  file: testing-api.json
  operationId: run-test-spec
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: >-
    Check the results of the test run you've created with the Get Test Run
    Endpoint!
---
> 🚧 Testing APIs are currently under Public Preview
> 
> To add your project to the Public Preview, contact your customer success manager, or contact the Voiceflow team via the discord channel.

A Test Spec can be run many times, each of which is represented by a Test Run.

## Example Response

```json
{
  "data": {
    "id": "testRunID"
  }
}
```

You can use the `testRunID` to check the status & results of the test.