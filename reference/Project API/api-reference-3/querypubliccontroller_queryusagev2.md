---
title: Query assistant usage v2
api:
  file: analytics-api-usage-v2.json
  operationId: QueryPublicController_queryUsageV2
hidden: true
---
## Analytics API Overview

With the Analytics API, you can retrieve the usage data of your conversational assistant. This data can be used to understand how your assistant is being used, such as the number of conversations started, messages sent, and unique users. This information can be valuable for:

* Assessing the performance and effectiveness of your assistant
* Identifying areas for improvement
* Making data-driven decisions about its development and deployment

<br />

## 📋 Request Types

There are different types of requests that can be sent.\
To see a list of all request types, check out the documentation for the `data.name` field below.

Examples include:

* Unique users
* Total interactions
* Top intents
* Credits usage

<br />

### 📘 Example Request and Response

```json Top intents
// REQUEST body

{
  "data": [
    {
      "name": "top_intents",
      "filter": {
        "projectID": "62912f08e83f76001b218690",
        "startTime": "2021-08-01T00:00:00.000Z",
        "endTime": "2021-08-16T00:00:00.000Z",
        "limit": 3
      }
    }
  ]
}
```