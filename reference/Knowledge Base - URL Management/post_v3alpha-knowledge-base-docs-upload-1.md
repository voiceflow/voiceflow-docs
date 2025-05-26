---
title: Upload Document (url)
excerpt: >-
  Uploads a document of type "url" to the Knowledge Base. Limit is one url per
  call.
api:
  file: knowledge-base-url-management.json
  operationId: post_v3alpha-knowledge-base-docs-upload
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Request Fields

[block:parameters]
{
  "data": {
    "h-0": "Property",
    "h-1": "Description & Example",
    "0-0": "**Content-Type**  \n(header)",
    "0-1": "application/json; charset=utf-8",
    "1-0": "**overwrite**  \n(query parameter)",
    "1-1": "Optional - Specify whether to overwrite existing data (optional).  \n\"True\" means you want to overwrite.",
    "2-0": "**maxChunkSize**  \n(query parameter)",
    "2-1": "Optional - Determine how granularly each document is broken up.  \nMax chunk size affects the total amount of chunks parsed from a document.  \n(i.e. larger chunks means less chunks retrieved)  \n  \n_Smaller chunk size means:_  \n- narrower context  \n- faster response  \n- less tokens consumed  \n- greater risk of less accurate answers  \n  \ntype: integer ; **default: 1000**; **Range available is 500-1500 tokens**.  \nOnce uploaded, you can view the chunks using the GET **Document Chunk Retrieval** Knowledge Base API."
  },
  "cols": 2,
  "rows": 3,
  "align": [
    "left",
    "left"
  ]
}
[/block]


## Example

### Sample Route with query parameters:

`https://api.voiceflow.com/v3alpha/knowledge-base/docs/upload?tags=["beginner","small_scale"]`

### Sample Request

```json
{
	"data": {
		"type": "url",
		"url": "https://www.familyhandyman.com/article/simple-step-stool/"
	}
}
```

### Sample Response

```json JSON
{
  	"data": {
			"documentID": "6515dccab4bc5400060fbc6a",
			"data": {
				"type": "url",
				"name": "familyhandyman.com/article/simple-step-stool/"
			},
			"updatedAt": "2023-09-28T20:06:34.049Z",
			"status": {
				"type": "PENDING"
			},
			"tags": [
				"beginner",
				"small_scale"
			]
		}
}
```