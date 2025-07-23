---
title: Query assistant usage v2
excerpt: >-
  With the Analytics API, you can retrieve the usage data of your conversational
  assistant. This data can be used to understand how your assistant is being
  used, such as the number of conversations started, messages sent, and unique
  users. This information can be valuable for assessing the performance and
  effectiveness of your assistant, identifying areas for improvement, and making
  data-driven decisions about its development and deployment.### RequestsThere
  are different types of requests that can be sent. To see a list of all request
  types, check out the documentation for the `query` field below.Examples
  include unique users, understood messages, top intents and total interactions.
  Example request to retrieve top 3 intents below:```json{  "query": [    {     
  "name": "top_intents",      "filter": {          "projectID":
  "62912f08e83f76001b218690",          "startTime":
  "2021-08-01T00:00:00.000Z",          "endTime":
  "2021-08-16T00:00:00.000Z",          "limit": 3    }   } ]}```###
  ResponseAfter processing your request, the Analytics API will then respond
  with the results:```json{  "result": [    {      "intents": [       
  {          "name": "info_personal",          "count": 152        },       
  {          "name": "info_company",          "count": 101        },       
  {          "name": "info_name",          "count": 80        },   ]}```In the
  example above, the Voiceflow project responded with the top 3 intents for the
  assistant with projectID: `62912f08e83f76001b218690`.
api:
  file: analytics-api-usage-v2.json
  operationId: QueryPublicController_queryUsageV2
hidden: true
---