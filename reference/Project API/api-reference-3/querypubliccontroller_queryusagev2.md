---
title: Query assistant usage v2
api:
  file: analytics-api-usage-v2.json
  operationId: QueryPublicController_queryUsageV2
hidden: true
---
## 📊 Analytics API Overview

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

// ------------------------------------------

// RESPONSE body

{
  "result": {
    "intents": [
      {
        "name": "info_personal",
        "count": 152
      },
      {
        "name": "info_company",
        "count": 101
      },
      {
        "name": "info_name",
        "count": 80
      }
    ]
  }
}

```
```json Total interactions
// REQUEST body 

{
  "data": [
    {
      "name": "interactions",
      "filter": {
        "projectID": "62912f08e83f76001b218690",
        "startTime": "2021-08-01T00:00:00.000Z",
        "limit": 3
      }
    }
  ]
}

// ------------------------------------------

// RESPONSE body

{
  "result": {
    "cursor": 296,
    "items": [
      {
        "period": "2025-06-13T18:00:00.000Z",
        "projectID": "62912f08e83f76001b218690",
        "environmentID": "684c6d43ea3aff06439c1561",
        "type": "canvas-prototype",
        "count": 18
      },
      {
        "period": "2025-07-16T23:00:00.000Z",
        "projectID": "62912f08e83f76001b218690",
        "environmentID": "684c6d43ea3aff06439c1561",
        "type": "dialog-management",
        "count": 6
      },
      {
        "period": "2025-07-16T17:00:00.000Z",
        "projectID": "62912f08e83f76001b218690",
        "environmentID": "684c6d43ea3aff06439c1561",
        "type": "dialog-management",
        "count": 4
      }
    ]
  }
}

```