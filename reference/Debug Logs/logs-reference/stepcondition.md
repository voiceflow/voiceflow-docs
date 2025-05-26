---
title: step.condition
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

```json
{
  "level": "info",
  "timestamp": "2022-06-15T14:15:30.150Z",
  "kind": "step.condition",
  "message": {
    "componentName": "condition",
    "stepID": "628469f0effe73d544505715",
    "path": {
      "componentName": "speak",
      "stepID": "62c47ac699eca10006f20cbb"
    }
  }
}
```

`path` is `null` when the chosen condition does not connect to a node on the canvas.
