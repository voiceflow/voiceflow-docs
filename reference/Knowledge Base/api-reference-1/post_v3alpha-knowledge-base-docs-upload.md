---
title: Upload Document (non-url)
excerpt: >-
  Uploads a document to the Knowledge Base (excluding type "url"). Limit is one
  file per call.
api:
  file: knowledge-base-management-apis.json
  operationId: post_v3alpha-knowledge-base-docs-upload
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

## Request Fields

[block:parameters]
{
  "data": {
    "h-0": "Property",
    "h-1": "Description & Example",
    "0-0": "**Authorization**  \n(header)",
    "0-1": "**Dialog Manager API Key**",
    "1-0": "**Content-Type**  \n(header)",
    "1-1": "multipart/form-data",
    "2-0": "**overwrite**  \n(query parameter)",
    "2-1": "Optional - Specify whether to overwrite existing data (optional).  \n\"True\" means you want to overwrite.",
    "3-0": "**maxChunkSize**  \n(query parameter)",
    "3-1": "Optional - Determine how granularly each document is broken up.  \nMax chunk size affects the total amount of chunks parsed from a document.  \n(i.e. larger chunks means less chunks retrieved)  \n  \n_Smaller chunk size means:_  \n- narrower context  \n- faster response  \n- less tokens consumed  \n- greater risk of less accurate answers  \n  \ntype: integer ; **default: 1000**; **Range available is 500-1500 tokens**.  \nOnce uploaded, you can view the chunks using the GET **Document Chunk Retrieval** Knowledge Base API.",
    "4-0": "**file**  \n(body, form-data)",
    "4-1": "Accepted source document types for this endpoint are:  \n**pdf**, **text**, or **docx**."
  },
  "cols": 2,
  "rows": 5,
  "align": [
    "left",
    "left"
  ]
}
[/block]


## Example

### Sample Route with query parameters:

`https://api.voiceflow.com/v3alpha/knowledge-base/docs/upload?tags=["beginner"]`

### Sample Response

```json JSON
{
  	"data": {
			"documentID": "6515dccab4bc5400060fbc6a",
			"data": {
				"type": "pdf",
				"name": "Learn-to-Sail.pdf"
			},
			"updatedAt": "2023-09-28T20:06:34.049Z",
			"status": {
				"type": "PENDING"
			},
			"tags": [
				"beginner"
			]
		}
}
```