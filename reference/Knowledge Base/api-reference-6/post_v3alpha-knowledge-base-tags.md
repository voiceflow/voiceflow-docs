---
title: Create KB tag
excerpt: >-
  Create tags that can be attached to Knowledge Base documents to filter and
  organize them (improving query response accuracy).
api:
  file: knowledge-base-tags.json
  operationId: post_v3alpha-knowledge-base-tags
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Example

### Request

```json
{
	"data": {
		"label": "technical"
	}
}
```

### Response

```json
{
	"data": {
		"label": "technical",
		"tagID": "651ebb247770e893e3768507"
	}
}
```
