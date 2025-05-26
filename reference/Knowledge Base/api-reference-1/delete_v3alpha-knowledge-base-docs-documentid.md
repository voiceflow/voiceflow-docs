---
title: Delete Document
excerpt: Deletes a specific Knowledge Base document by documentID.
api:
  file: knowledge-base-management-apis.json
  operationId: delete_v3alpha-knowledge-base-docs-documentid
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

[block:parameters]
{
  "data": {
    "h-0": "Property",
    "h-1": "Description & Example",
    "0-0": "**Authorization**  \n(header)",
    "0-1": "**Dialog Manager API Key**",
    "1-0": "**documentID**  \n(path variable)",
    "1-1": "A unique identifier of the document object (a string).  \nTo get the list of documentID's, use the **GET Document List** Knowledge Base API."
  },
  "cols": 2,
  "rows": 2,
  "align": [
    "left",
    "left"
  ]
}
[/block]


## Sample Response

Successful response will be blank.