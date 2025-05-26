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
        application/json; charset=utf-8
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
  </tbody>
</Table>

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
