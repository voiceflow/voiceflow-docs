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

```json
{
  "level": "info",
  "timestamp": "2022-06-15T14:15:30.150Z",
  "kind": "global.nlu.intent_resolved",
  "message": {
    "resolvedIntent": "place_order",
    "confidence": 0.956,
    "utterance": "i would like to buy a burger",
    "entities": {
      "shop_item": {
        "value": "burger"
      }
    }
  }
}
```
