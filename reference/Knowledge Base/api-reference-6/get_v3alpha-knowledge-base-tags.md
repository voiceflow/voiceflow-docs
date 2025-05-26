---
title: KB tag list
excerpt: Retrieves a list of all the Knowledge Base tags created for a project.
api:
  file: knowledge-base-tags.json
  operationId: get_v3alpha-knowledge-base-tags
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

### Response

```json
{
	"total": 5,
	"data": [
		{
			"label": "beginner",
			"tagID": "651de121f5827c2435475fdb"
		},
		{
			"label": "advanced",
			"tagID": "651de4a8f5827c2435475fdd"
		},
		{
			"label": "small_scale",
			"tagID": "651de513f5827c2435475fde"
		},
		{
			"label": "large_scale",
			"tagID": "651de51cf5827c2435475fdf"
		},
		{
			"label": "technical",
			"tagID": "651ebb247770e893e3768507"
		}
	]
}
```
