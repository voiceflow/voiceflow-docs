---
title: step.custom_code
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
### Success
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"level\": \"info\",\n  \"timestamp\": \"2022-06-15T14:15:30.150Z\",\n  \"kind\": \"step.custom_code\",\n  \"message\": {\n    \"componentName\": \"custom_code\",\n    \"stepID\": \"628469f0effe73d544505715\",\n    \"changedVariables\": {\n      \"city\": {\n        \"before\": 0,\n        \"after\": \"San Francisco\"\n      },\n      \"state\": {\n        \"before\": 0,\n        \"after\": \"CA\"\n      }\n    },\n    \"error\": null\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]
## Error
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"level\": \"info\",\n  \"timestamp\": \"2022-06-15T14:15:30.150Z\",\n  \"kind\": \"step.custom_code\",\n  \"message\": {\n    \"componentName\": \"custom_code\",\n    \"stepID\": \"628469f0effe73d544505715\",\n    \"changedVariables\": null,\n    \"error\": \"TypeError: Value must be a string\"\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]