---
title: Document List
excerpt: Retrieves a list of all documents within a given project's Knowledge Base.
api:
  file: knowledge-base-management-apis.json
  operationId: get_v3alpha-knowledge-base-docs
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
  </tbody>
</Table>

### Pagination

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
        **page**
        (query parameter)
      </td>

      <td>
        Optional pagination parameter - The page number to retrieve, defaults to 1 (which is the minimum). Order is by the date updated, descending.
      </td>
    </tr>

    <tr>
      <td>
        **limit**\
        (query parameter)
      </td>

      <td>
        Optional pagination parameter- The number of documents to return per page.\
        Defaults to 10, range is 1-100.
      </td>
    </tr>

    <tr>
      <td>
        **documentType**\
        (query parameter)
      </td>

      <td>
        Optional pagination parameter - Filter the document list by type (url, pdf, text, docx).\
        Defaults to all.
      </td>
    </tr>
  </tbody>
</Table>

## Filtering KB doc list by KB tags using query parameters:

Case 1: User wants a list of KB documents that have tags `beginner` or `small_scale` attached, and also does not have the tag `advanced` attached: 

`/docs?includeTags=["beginner","small_scale"]&excludeTags=["advanced"]`

Case 2: User wants a list of KB documents that don't have any KB tags attached:

`/docs?includeAllNonTagged=true`

Case 3: User wants a list of KB documents that have any KB tag attached:

`/docs?includeAllTagged=true`

***

## Sample Response

```json JSON
{
	"total": 7,
	"data": [
		{
			"documentID": "65170285b4bc5400060fcf32",
			"data": {
				"type": "url",
				"name": "en.wikipedia.org/wiki/Woodworking",
				"url": "https://en.wikipedia.org/wiki/Woodworking"
			},
			"updatedAt": "2023-09-29T16:59:49.414Z",
			"status": {
				"type": "SUCCESS"
			},
			"tags": []
		},
		{
			"documentID": "6515dcceb4bc5400060fbc6e",
			"data": {
				"type": "url",
				"name": "familyhandyman.com/project/how-to-build-a-chessboard/",
				"url": "https://www.familyhandyman.com/project/how-to-build-a-chessboard/"
			},
			"updatedAt": "2023-09-28T20:06:38.212Z",
			"status": {
				"type": "SUCCESS"
			},
			"tags": [
				"small_scale",
				"advanced"
			]
		},
		{
			"documentID": "6515dccab4bc5400060fbc6d",
			"data": {
				"type": "url",
				"name": "familyhandyman.com/project/partition-any-living-space-to-make-a-private-room/",
				"url": "https://www.familyhandyman.com/project/partition-any-living-space-to-make-a-private-room/"
			},
			"updatedAt": "2023-09-28T20:06:34.088Z",
			"status": {
				"type": "SUCCESS"
			},
			"tags": [
				"advanced",
				"big_scale"
			]
		},
		{
			"documentID": "6515dccab4bc5400060fbc6c",
			"data": {
				"type": "url",
				"name": "familyhandyman.com/project/how-to-build-a-cedar-potting-bench/",
				"url": "https://www.familyhandyman.com/project/how-to-build-a-cedar-potting-bench/"
			},
			"updatedAt": "2023-09-28T20:06:34.084Z",
			"status": {
				"type": "SUCCESS"
			},
			"tags": [
				"beginner",
				"big_scale"
			]
		},
		{
			"documentID": "6515dccab4bc5400060fbc6b",
			"data": {
				"type": "url",
				"name": "yorksaw.com/beginners-guide-to-must-have-tools-for-woodworking/",
				"url": "https://www.yorksaw.com/beginners-guide-to-must-have-tools-for-woodworking/"
			},
			"updatedAt": "2023-09-28T20:06:34.078Z",
			"status": {
				"type": "SUCCESS"
			},
			"tags": []
		},
		{
			"documentID": "6515dccab4bc5400060fbc6a",
			"data": {
				"type": "url",
				"name": "familyhandyman.com/article/simple-step-stool/",
				"url": "https://www.familyhandyman.com/article/simple-step-stool/"
			},
			"updatedAt": "2023-09-28T20:06:34.049Z",
			"status": {
				"type": "SUCCESS"
			},
			"tags": [
				"beginner",
				"small_scale"
			]
		},
		{
			"documentID": "6515dccab4bc5400060fbc69",
			"data": {
				"type": "url",
				"name": "familyhandyman.com/project/schoolhouse-storage-shed/",
				"url": "https://www.familyhandyman.com/project/schoolhouse-storage-shed/"
			},
			"updatedAt": "2023-09-28T20:06:34.033Z",
			"status": {
				"type": "SUCCESS"
			},
			"tags": [
				"advanced",
				"big_scale"
			]
		}
	]
}
```
