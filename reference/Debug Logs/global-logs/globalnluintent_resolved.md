---
title: global.nlu.intent_resolved
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
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"level\": \"info\",\n  \"timestamp\": \"2022-06-15T14:15:30.150Z\",\n  \"kind\": \"global.nlu.intent_resolved\",\n  \"message\": {\n    \"resolvedIntent\": \"place_order\",\n    \"confidence\": 0.956,\n    \"utterance\": \"i would like to buy a burger\",\n    \"entities\": {\n      \"shop_item\": {\n        \"value\": \"burger\"\n      }\n    }\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]