---
title: Replace Document (file)
excerpt: >-
  Replaces the document and document name in the Knowledge Base, by documentID
  (excluding type "url"). Limit one per call.
api:
  file: knowledge-base-management-apis-8.json
  operationId: put_v1-knowledge-base-docs-documentid-upload
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
        **documentID**\
        (path variable)
      </td>

      <td style={{ textAlign: "left" }}>
        A unique identifier of the document object (a string).\
        To get the list of documentID's, use the **GET Document List** Knowledge Base API.
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
        * greater risk of less accurate answerstype: integer ; **default: 1000**; **Range available is 500-1500 tokens**.\
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
