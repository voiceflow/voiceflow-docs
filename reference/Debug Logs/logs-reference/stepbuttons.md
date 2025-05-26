---
title: step.buttons
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

### Follow path

```json
{
  "level": "info",
  "timestamp": "2022-06-15T14:15:30.150Z",
  "kind": "step.buttons",
  "message": {
    "componentName": "buttons",
    "stepID": "628469f0effe73d544505715",
    "intent": null,
    "url": null,
    "path": {
      "componentName": "speak",
      "stepID": "62c47ac699eca10006f20cbb"
    }
  }
}
```

### URL + follow path

```json
{
  "level": "info",
  "timestamp": "2022-06-15T14:15:30.150Z",
  "kind": "step.buttons",
  "message": {
    "componentName": "buttons",
    "stepID": "628469f0effe73d544505715",
    "intent": null,
    "url": "https://example.com",
    "path": {
      "componentName": "speak",
      "stepID": "62c47ac699eca10006f20cbb"
    }
  }
}
```

### Go to intent

```json
{
  "level": "info",
  "timestamp": "2022-06-15T14:15:30.150Z",
  "kind": "step.buttons",
  "message": {
    "componentName": "buttons",
    "stepID": "628469f0effe73d544505715",
    "intent": "place_order",
    "url": null,
    "path": null
  }
}
```

### URL + go to intent

```json
{
  "level": "info",
  "timestamp": "2022-06-15T14:15:30.150Z",
  "kind": "step.buttons",
  "message": {
    "componentName": "buttons",
    "stepID": "628469f0effe73d544505715",
    "intent": "place_order",
    "url": "https://example.com",
    "path": null
  }
}
```
