---
title: Upload Document (file)
excerpt: >-
  Uploads a document to the Knowledge Base (excluding type "url"). Limit is one
  file per call.
api:
  file: knowledge-base-management-apis-4.json
  operationId: post_v1-knowledge-base-docs-upload
deprecated: false
hidden: false
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
    "1-0": "**overwrite**  \n(query parameter)",
    "1-1": "Optional - Specify whether to overwrite existing data (optional).  \n\"True\" means you want to overwrite.",
    "2-0": "**maxChunkSize**  \n(query parameter)",
    "2-1": "Optional - Determine how granularly each document is broken up.  \nMax chunk size affects the total amount of chunks parsed from a document.  \n(i.e. larger chunks means less chunks retrieved)  \n  \n_Smaller chunk size means:_  \n  \n- narrower context\n- faster response\n- less tokens consumed\n- greater risk of less accurate answerstype: integer ; **default: 1000**; **Range available is 500-1500 tokens**.  \n  Once uploaded, you can view the chunks using the GET **Document Chunk Retrieval** Knowledge Base API.",
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