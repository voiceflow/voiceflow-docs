---
title: step.exit
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Examples
### Non-verbose
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"level\": \"info\",\n  \"timestamp\": \"2022-06-15T14:15:30.150Z\",\n  \"kind\": \"step.exit\",\n  \"message\": {\n    \"componentName\": \"exit\",\n    \"stepID\": \"628469f0effe73d544505715\",\n    \"state\": null\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]
### Verbose
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"level\": \"info\",\n  \"timestamp\": \"2022-06-15T14:15:30.150Z\",\n  \"kind\": \"step.exit\",\n  \"message\": {\n    \"componentName\": \"exit\",\n    \"stepID\": \"628469f0effe73d544505715\",\n    \"state\": {\n      \"stack\": [],\n      \"storage\": {},\n      \"variables\": {\n        \"sessions\": 1,\n        \"user_id\": \"7e386c6f-ba55-47a4-bd24-c9b367f32600\",\n        \"timestamp\": 1655302530,\n        \"platform\": \"voiceflow\",\n        \"locale\": 0,\n        \"url_count\": 0,\n        \"intent_confidence\": 0,\n        \"last_utterance\": \"\"\n      }\n    }\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]