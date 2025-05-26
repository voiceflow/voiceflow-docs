---
title: step.set
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
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"level\": \"info\",\n  \"timestamp\": \"2022-06-15T14:15:30.150Z\",\n  \"kind\": \"step.set\",\n  \"message\": {\n    \"componentName\": \"set\",\n    \"stepID\": \"628469f0effe73d544505715\",\n    \"changedVariables\": {\n      \"city\": {\n        \"before\": 0,\n        \"after\": \"San Francisco\"\n      },\n      \"state\": {\n        \"before\": 0,\n        \"after\": \"CA\"\n      }\n    }\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]
The default variable value of `0` is used in `changedVariables`.