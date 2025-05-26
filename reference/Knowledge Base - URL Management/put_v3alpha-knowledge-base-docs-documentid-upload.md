---
title: Replace Document (non-url)
excerpt: >-
  Replaces the document and document name in the Knowledge Base, by documentID
  (excluding type "url"). Limit one per call.
api:
  file: knowledge-base-management-apis.json
  operationId: put_v3alpha-knowledge-base-docs-documentid-upload
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
    "0-1": "multipart/form-data",
    "1-0": "**documentID**  \n(path variable)",
    "1-1": "A unique identifier of the document object (a string).  \nTo get the list of documentID's, use the **GET Document List** Knowledge Base API.",
    "2-0": "**maxChunkSize**  \n(query parameter)",
    "2-1": "Optional - Determine how granularly each document is broken up.  \nMax chunk size affects the total amount of chunks parsed from a document.  \n(i.e. larger chunks means less chunks retrieved)  \n  \n_Smaller chunk size means:_  \n- narrower context  \n- faster response  \n- less tokens consumed  \n- greater risk of less accurate answers  \n  \ntype: integer ; **default: 1000**; **Range available is 500-1500 tokens**.  \nOnce uploaded, you can view the chunks using the GET **Document Chunk Retrieval** Knowledge Base API.",
    "3-0": "**file**  \n(body, form-data)",
    "3-1": "Accepted source document types for this endpoint are:  \n**pdf**, **text**, or **docx**."
  },
  "cols": 2,
  "rows": 4,
  "align": [
    "left",
    "left"
  ]
}
[/block]


## Sample Response

```json JSON
{
	"data": {
		"documentID": "6532663e91552f00079ad153",
		"data": {
			"type": "pdf",
			"name": "Learn-to-Sail.pdf"
		},
		"updatedAt": "2023-10-20T11:36:30.040Z",
		"status": {
			"type": "PENDING"
		},
		"tags": []
	}
}
```