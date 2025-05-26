---
title: step.flow
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
      "code": "{\n  \"level\": \"info\",\n  \"timestamp\": \"2022-06-15T14:15:30.150Z\",\n  \"kind\": \"step.flow\",\n  \"message\": {\n    \"componentName\": \"flow\",\n    \"stepID\": \"628469f0effe73d544505715\",\n    \"flow\": {\n      \"before\": {\n        \"name\": \"ROOT\",\n        \"programID\": \"62912f08e83f76001b218692\"\n      },\n      \"after\": {\n        \"name\": null,\n        \"programID\": \"62912f08e83f76001b218695\"\n      }\n    }\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]
`flow` is `null` when the chosen condition does not connect to a node on the canvas.