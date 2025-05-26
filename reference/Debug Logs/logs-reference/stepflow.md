---
title: step.flow
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
  "kind": "step.flow",
  "message": {
    "componentName": "flow",
    "stepID": "628469f0effe73d544505715",
    "flow": {
      "before": {
        "name": "ROOT",
        "programID": "62912f08e83f76001b218692"
      },
      "after": {
        "name": null,
        "programID": "62912f08e83f76001b218695"
      }
    }
  }
}
```

`flow` is `null` when the chosen condition does not connect to a node on the canvas.
