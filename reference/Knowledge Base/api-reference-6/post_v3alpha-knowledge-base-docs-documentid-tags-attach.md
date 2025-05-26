---
title: Attaches KB tags to a document.
excerpt: Attaches existing KB tags to a document (documentID).
api:
  file: knowledge-base-tags.json
  operationId: post_v3alpha-knowledge-base-docs-documentid-tags-attach
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
> 📘 All requests to any Knowledge Base APIs require a Dialog Manager API Key.
> 
> To obtain this key, go to the Integration tab on the project you uploaded data sources to and click the "Copy API key" button.
> 
> ![](https://files.readme.io/cbc3534-CleanShot_2023-10-05_at_09.02.272x.png)

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