---
title: step.random
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
  "kind": "step.random",
  "message": {
    "componentName": "random",
    "stepID": "628469f0effe73d544505715",
    "path": {
      "componentName": "speak",
      "stepID": "62c47ac699eca10006f20cbb"
    }
  }
}
```

`path` is `null` when the chosen path does not connect to a node on the canvas.
