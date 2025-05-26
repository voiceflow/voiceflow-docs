---
title: step.api
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Examples
###Success
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"level\": \"info\",\n  \"timestamp\": \"2022-06-15T14:15:30.150Z\",\n  \"kind\": \"step.api\",\n  \"message\": {\n    \"componentName\": \"api\",\n    \"stepID\": \"628469f0effe73d544505715\",\n    \"request\": {\n      \"method\": \"POST\",\n      \"url\": \"https://example.com/\",\n      \"body\": null,\n      \"bodyType\": null,\n      \"headers\": null,\n      \"query\": null\n    },\n    \"response\": {\n      \"statusCode\": 200,\n      \"statusText\": \"OK\",\n      \"body\": null,\n      \"headers\": null\n    }\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]
### Verbose success
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"level\": \"verbose\",\n  \"timestamp\": \"2022-06-15T14:15:30.150Z\",\n  \"kind\": \"step.api\",\n  \"message\": {\n    \"componentName\": \"api\",\n    \"stepID\": \"628469f0effe73d544505715\",\n    \"request\": {\n      \"method\": \"POST\",\n      \"url\": \"https://example.com/?foo=bar\",\n      \"body\": \"{\\\"foo\\\": \\\"bar\\\"}\",\n      \"bodyType\": \"rawInput\",\n      \"headers\": {\n        \"Content-Type\": \"application/json\"\n      },\n      \"query\": {\n        \"foo\": \"bar\"\n      }\n    },\n    \"response\": {\n      \"statusCode\": 200,\n      \"statusText\": \"OK\",\n      \"body\": \"{\\\"foo\\\": \\\"bar\\\"}\",\n      \"headers\": {\n        \"Content-Type\": \"application/json\"\n      }\n    }\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]
### Error
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"level\": \"error\",\n  \"timestamp\": \"2022-06-15T14:15:30.150Z\",\n  \"kind\": \"step.api\",\n  \"message\": {\n    \"componentName\": \"api\",\n    \"stepID\": \"628469f0effe73d544505715\",\n    \"request\": {\n      \"method\": \"POST\",\n      \"url\": \"https://example.com/\",\n      \"body\": null,\n      \"bodyType\": null,\n      \"headers\": null,\n      \"query\": null\n    },\n    \"response\": {\n      \"statusCode\": 500,\n      \"statusText\": \"Internal Server Error\",\n      \"body\": null,\n      \"headers\": null\n    }\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]
### Verbose error
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"level\": \"verbose\",\n  \"timestamp\": \"2022-06-15T14:15:30.150Z\",\n  \"kind\": \"step.api\",\n  \"message\": {\n    \"componentName\": \"api\",\n    \"stepID\": \"628469f0effe73d544505715\",\n    \"request\": {\n      \"method\": \"POST\",\n      \"url\": \"https://example.com/?foo=bar\",\n      \"body\": \"{\\\"foo\\\":\\\"bar\\\"}\",\n      \"bodyType\": \"rawInput\",\n      \"headers\": {\n        \"Content-Type\": \"application/json\"\n      },\n      \"query\": {\n        \"foo\": \"bar\"\n      }\n    },\n    \"response\": {\n      \"statusCode\": 500,\n      \"statusText\": \"Internal Server Error\",\n      \"body\": \"{\\\"foo\\\":\\\"bar\\\"}\",\n      \"headers\": {\n        \"Content-Type\": \"application/json\"\n      }\n    }\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]