---
title: Query assistant usage (legacy)
excerpt: "With the Analytics API, you can retrieve data about the usage of your conversational assistant. This data can be used to understand how your assistant is being used, such as the number of conversations started, messages sent, and unique users. This information can be valuable for assessing the performance and effectiveness of your assistant, identifying areas for improvement, and making data-driven decisions about its development and deployment.\n\n### Requests\nThere are different types of requests that can be sent. To see a list of all request types, check out the documentation for the `query` field below.\n\nExamples include unique users, understood messages, top intents and total interactions. Example request to retrieve top 3 intents below:\n```json\n{\r\n  \"query\": [\r\n    {\r\n      \"name\": \"top_intents\",\r\n      \"filter\": {\r\n          \"projectID\": \"62912f08e83f76001b218690\",\r\n          \"startTime\": \"2021-08-01T00:00:00.000Z\",\r\n          \"endTime\": \"2021-08-16T00:00:00.000Z\",\r\n          \"limit\": 3\r\n    }\r\n   }\r\n ]\r\n}\n```\n\n### Response\nAfter processing your request, the Analytics API will then respond with the results:\n```json\n{\r\n  \"result\": [\r\n    {\r\n      \"intents\": [\r\n        {\r\n          \"name\": \"info_personal\",\r\n          \"count\": 152\r\n        },\r\n        {\r\n          \"name\": \"info_company\",\r\n          \"count\": 101\r\n        },\r\n        {\r\n          \"name\": \"info_name\",\r\n          \"count\": 80\r\n        },\r\n   ]\r\n}\n```\nIn the example above, the Voiceflow project responded with the top 3 intents for the assistant with projectID: `62912f08e83f76001b218690`."
api:
  file: analytics-api.json
  operationId: QueryPublicController_queryUsage
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
> 🚧
>
> This version of the Analytics API is now in legacy status. We're excited to announce that a new version will be released soon, powering the redesigned Analytics dashboard with improved performance and additional metrics.
