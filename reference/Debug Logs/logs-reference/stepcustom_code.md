---
title: step.custom_code
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

### Success

```json
{
  "level": "info",
  "timestamp": "2022-06-15T14:15:30.150Z",
  "kind": "step.custom_code",
  "message": {
    "componentName": "custom_code",
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
    },
    "error": null
  }
}
```

## Error

```json
{
  "level": "info",
  "timestamp": "2022-06-15T14:15:30.150Z",
  "kind": "step.custom_code",
  "message": {
    "componentName": "custom_code",
    "stepID": "628469f0effe73d544505715",
    "changedVariables": null,
    "error": "TypeError: Value must be a string"
  }
}
```
