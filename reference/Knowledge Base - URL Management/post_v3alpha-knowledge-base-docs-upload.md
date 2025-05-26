---
title: Upload Document (non-url)
excerpt: >-
  Uploads a document to the Knowledge Base (excluding type "url"). Limit is one
  file per call.
api:
  file: knowledge-base-management-apis.json
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

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Property
      </th>

      <th style={{ textAlign: "left" }}>
        Description & Example
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        **Content-Type**
        (header)
      </td>

      <td style={{ textAlign: "left" }}>
        multipart/form-data
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **overwrite**\
        (query parameter)
      </td>

      <td style={{ textAlign: "left" }}>
        Optional - Specify whether to overwrite existing data (optional).\
        "True" means you want to overwrite.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **maxChunkSize**\
        (query parameter)
      </td>

      <td style={{ textAlign: "left" }}>
        Optional - Determine how granularly each document is broken up.\
        Max chunk size affects the total amount of chunks parsed from a document.\
        (i.e. larger chunks means less chunks retrieved)  

        *Smaller chunk size means:*  

        * narrower context  
        * faster response  
        * less tokens consumed  
        * greater risk of less accurate answers  

        type: integer ; **default: 1000**; **Range available is 500-1500 tokens**.\
        Once uploaded, you can view the chunks using the GET **Document Chunk Retrieval** Knowledge Base API.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **file**\
        (body, form-data)
      </td>

      <td style={{ textAlign: "left" }}>
        Accepted source document types for this endpoint are:  

        * \*pd&#x66;**,**&#x74;ex&#x74;**, or**docx\*\*.
      </td>
    </tr>
  </tbody>
</Table>

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
