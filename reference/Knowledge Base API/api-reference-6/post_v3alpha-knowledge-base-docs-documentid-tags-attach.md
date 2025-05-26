---
title: Attaches KB tags to a document.
excerpt: Attaches existing KB tags to a document (documentID).
api:
  file: knowledge-base-tags.json
  operationId: post_v3alpha-knowledge-base-docs-documentid-tags-attach
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
> 🚧 
> 
> The Tags API is a legacy API. We recommend adding tags at metadata to your documents moving forward.
> 
> Future features will not be compatible with the Tags API.

## Example

### Request

```json
{
	"data": {
		"tags": [
			"advanced",
			"big_scale"
		]
	}
}
```

### Response

Successful response will be blank.