---
title: Document List
excerpt: Retrieves a list of all documents within a given project's Knowledge Base.
api:
  file: knowledge-base-management-apis.json
  operationId: get_v3alpha-knowledge-base-docs
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
### Pagination

[block:parameters]
{
  "data": {
    "h-0": "Property",
    "h-1": "Description & Example",
    "0-0": "**page**  \n(query parameter)",
    "0-1": "Optional pagination parameter - The page number to retrieve, defaults to 1 (which is the minimum). Order is by the date updated, descending.",
    "1-0": "**limit**  \n(query parameter)",
    "1-1": "Optional pagination parameter- The number of documents to return per page.  \nDefaults to 10, range is 1-100.",
    "2-0": "**documentType**  \n(query parameter)",
    "2-1": "Optional pagination parameter - Filter the document list by type (url, pdf, text, docx).  \nDefaults to all."
  },
  "cols": 2,
  "rows": 3,
  "align": [
    "left",
    "left"
  ]
}
[/block]


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