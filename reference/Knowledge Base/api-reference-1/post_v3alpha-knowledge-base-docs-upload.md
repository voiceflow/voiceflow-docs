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

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Property
      </th>

      <th>
        Description & Example
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Authorization**
        (header)
      </td>

      <td>
        **Dialog Manager API Key**
      </td>
    </tr>

    <tr>
      <td>
        **Content-Type**\
        (header)
      </td>

      <td>
        multipart/form-data
      </td>
    </tr>

    <tr>
      <td>
        **overwrite**\
        (query parameter)
      </td>

      <td>
        Optional - Specify whether to overwrite existing data (optional).\
        "True" means you want to overwrite.
      </td>
    </tr>

    <tr>
      <td>
        **maxChunkSize**\
        (query parameter)
      </td>

      <td>
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
      <td>
        **file**\
        (body, form-data)
      </td>

      <td>
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
