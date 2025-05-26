---
title: step.capture
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

### Capture

```json
{
  "level": "info",
  "timestamp": "2022-06-15T14:15:30.150Z",
  "kind": "step.capture",
  "message": {
    "componentName": "capture",
    "stepID": "628469f0effe73d544505715",
    "changedVariables": {
      "city": {
        "before": 0,
        "after": "San Francisco"
      },
      "state": {
        "before": 0,
        "after": "CA"
      }
    }
  }
}
```

The default variable value of `0` is used in `changedVariables`.
