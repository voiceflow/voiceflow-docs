---
title: Update KB tag label
excerpt: Update the label/name of KB tags by tagID.
api:
  file: knowledge-base-tags.json
  operationId: patch_v3alpha-knowledge-base-tags-tagid
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
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
	"label": "advanced"
}
```

### Response

```json
{
	"data": {
		"label": "advanced",
		"tagID": "651dc969f5827c2435475fda"
	}
}
```