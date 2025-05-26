---
title: step.api
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
  "kind": "step.api",
  "message": {
    "componentName": "api",
    "stepID": "628469f0effe73d544505715",
    "request": {
      "method": "POST",
      "url": "https://example.com/",
      "body": null,
      "bodyType": null,
      "headers": null,
      "query": null
    },
    "response": {
      "statusCode": 200,
      "statusText": "OK",
      "body": null,
      "headers": null
    }
  }
}
```

### Verbose success

```json
{
  "level": "verbose",
  "timestamp": "2022-06-15T14:15:30.150Z",
  "kind": "step.api",
  "message": {
    "componentName": "api",
    "stepID": "628469f0effe73d544505715",
    "request": {
      "method": "POST",
      "url": "https://example.com/?foo=bar",
      "body": "{\"foo\": \"bar\"}",
      "bodyType": "rawInput",
      "headers": {
        "Content-Type": "application/json"
      },
      "query": {
        "foo": "bar"
      }
    },
    "response": {
      "statusCode": 200,
      "statusText": "OK",
      "body": "{\"foo\": \"bar\"}",
      "headers": {
        "Content-Type": "application/json"
      }
    }
  }
}
```

### Error

```json
{
  "level": "error",
  "timestamp": "2022-06-15T14:15:30.150Z",
  "kind": "step.api",
  "message": {
    "componentName": "api",
    "stepID": "628469f0effe73d544505715",
    "request": {
      "method": "POST",
      "url": "https://example.com/",
      "body": null,
      "bodyType": null,
      "headers": null,
      "query": null
    },
    "response": {
      "statusCode": 500,
      "statusText": "Internal Server Error",
      "body": null,
      "headers": null
    }
  }
}
```

### Verbose error

```json
{
  "level": "verbose",
  "timestamp": "2022-06-15T14:15:30.150Z",
  "kind": "step.api",
  "message": {
    "componentName": "api",
    "stepID": "628469f0effe73d544505715",
    "request": {
      "method": "POST",
      "url": "https://example.com/?foo=bar",
      "body": "{\"foo\":\"bar\"}",
      "bodyType": "rawInput",
      "headers": {
        "Content-Type": "application/json"
      },
      "query": {
        "foo": "bar"
      }
    },
    "response": {
      "statusCode": 500,
      "statusText": "Internal Server Error",
      "body": "{\"foo\":\"bar\"}",
      "headers": {
        "Content-Type": "application/json"
      }
    }
  }
}
```
