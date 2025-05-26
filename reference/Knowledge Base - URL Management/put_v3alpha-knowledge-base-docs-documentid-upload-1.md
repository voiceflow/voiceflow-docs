---
title: Replace Document (url)
excerpt: >-
  Replaces the document and document name in the Knowledge Base, by documentID
  (of type "url" only). Limit one per call.
api:
  file: knowledge-base-url-management.json
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
    "0-1": "application/json; charset=utf-8",
    "1-0": "**documentID**  \n(path variable)",
    "1-1": "A unique identifier of the document object (a string).  \nTo get the list of documentID's, use the **GET Document List** Knowledge Base API.",
    "2-0": "**maxChunkSize**  \n(query parameter)",
    "2-1": "Optional - Determine how granularly each document is broken up.  \nMax chunk size affects the total amount of chunks parsed from a document.  \n(i.e. larger chunks means less chunks retrieved)  \n  \n_Smaller chunk size means:_  \n  \n- narrower context\n- faster response\n- less tokens consumed\n- greater risk of less accurate answerstype: integer ; **default: 1000**; **Range available is 500-1500 tokens**.  \nOnce uploaded, you can view the chunks using the GET **Document Chunk Retrieval** Knowledge Base API.",
    "3-0": "**JSON script**  \n(body, raw)",
    "3-1": "Format Example:  \n{  \n    \"data\": {  \n        \"type\": \"url\",  \n        \"url\": \"<https://voiceflow.com/\">  \n    }  \n}"
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
    "status": {
        "type": "PENDING"
    },
    "data": {
        "type": "url",
        "name": "voiceflow.com/",
        "url": "https://voiceflow.com/"
    },
    "updatedAt": "2023-08-09T21:20:29.706Z",
    "documentID": "64ca6b5e89cc410007bad5cd"
}
```