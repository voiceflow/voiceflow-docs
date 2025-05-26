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

```json
{
  "level": "info",
  "timestamp": "2022-06-15T14:15:30.150Z",
  "kind": "step.exit",
  "message": {
    "componentName": "exit",
    "stepID": "628469f0effe73d544505715",
    "state": null
  }
}
```

### Verbose

```json
{
  "level": "info",
  "timestamp": "2022-06-15T14:15:30.150Z",
  "kind": "step.exit",
  "message": {
    "componentName": "exit",
    "stepID": "628469f0effe73d544505715",
    "state": {
      "stack": [],
      "storage": {},
      "variables": {
        "sessions": 1,
        "user_id": "7e386c6f-ba55-47a4-bd24-c9b367f32600",
        "timestamp": 1655302530,
        "platform": "voiceflow",
        "locale": 0,
        "url_count": 0,
        "intent_confidence": 0,
        "last_utterance": ""
      }
    }
  }
}
```
