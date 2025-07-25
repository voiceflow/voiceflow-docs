---
title: Upload Document (url)
excerpt: >-
  Uploads a document of type "url" to the Knowledge Base. Limit is one url per
  call.
api:
  file: knowledge-base-url-management-2.json
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
        **overwrite**
        (query parameter)
      </td>

      <td style={{ textAlign: "left" }}>
        Optional - Specify whether to overwrite existing data (optional).
        "True" means you want to overwrite.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **maxChunkSize**
        (query parameter)
      </td>

      <td style={{ textAlign: "left" }}>
        Optional - Determine how granularly each document is broken up.
        Max chunk size affects the total amount of chunks parsed from a document.
        (i.e. larger chunks means less chunks retrieved)

        *Smaller chunk size means:*

        * narrower context
        * faster response
        * less tokens consumed
        * greater risk of less accurate answerstype: integer ; **default: 1000**; **Range available is 500-1500 tokens**.
          Once uploaded, you can view the chunks using the GET **Document Chunk Retrieval** Knowledge Base API.
      </td>
    </tr>
  </tbody>
</Table>

> 👨‍💻 Tags API has been deprecated
>
> Tags API stills offers legacy support, subject to change. For the latest tag functionality, you can now use file metadata when uploading files.
>
> <Image align="center" className="border" border={true} src="https://files.readme.io/8c376a1b4c22854fcaca831ade806d8f6645f69b96adce85d499fca0c4801d56-image.png" />

## Example

### Sample Request

```json
{
	"data": {
		"type": "url",
    "url": "https://www.familyhandyman.com/article/simple-step-stool/",
    "metadata":
    {
      "website_name": "family handman",
      "info_type": "article"
		}
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