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
        **JSON script**\
        (body, raw)
      </td>

      <td style={{ textAlign: "left" }}>
        Format Example:\
        \{\
            "data": \{\
                "type": "url",\
                "url": "[https://voiceflow.com/"](https://voiceflow.com/")\
            }\
        }
      </td>
    </tr>
  </tbody>
</Table>

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
