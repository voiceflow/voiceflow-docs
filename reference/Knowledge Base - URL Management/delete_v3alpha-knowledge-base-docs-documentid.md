---
title: Delete Document
excerpt: Deletes a specific Knowledge Base document by documentID.
api:
  file: knowledge-base-management-apis.json
  operationId: delete_v3alpha-knowledge-base-docs-documentid
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
        **documentID**
        (path variable)
      </td>

      <td style={{ textAlign: "left" }}>
        A unique identifier of the document object (a string).\
        To get the list of documentID's, use the **GET Document List** Knowledge Base API.
      </td>
    </tr>
  </tbody>
</Table>

## Sample Response

Successful response will be blank.
