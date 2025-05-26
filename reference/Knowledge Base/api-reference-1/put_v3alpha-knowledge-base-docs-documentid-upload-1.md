---
title: Replace Document (url)
excerpt: >-
  Replaces the document and document name in the Knowledge Base, by documentID
  (of type "url" only). Limit one per call.
api:
  file: knowledge-base-url-management.json
  operationId: put_v3alpha-knowledge-base-docs-documentid-upload
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
        application/json; charset=utf-8
      </td>
    </tr>

    <tr>
      <td>
        **documentID**\
        (path variable)
      </td>

      <td>
        A unique identifier of the document object (a string).\
        To get the list of documentID's, use the **GET Document List** Knowledge Base API.
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
        **JSON script**\
        (body, raw)
      </td>

      <td>
        Format Example:\
        \{\
            "data": \{\
                "type": "url",\
                "name": "[https://voiceflow.com/"](https://voiceflow.com/"),\
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
