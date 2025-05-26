---
title: Query
excerpt: >-
  This API endpoint allows you to query the Voiceflow Knowledge Base Preview
  function and retrieve answers to user questions.
api:
  file: knowledge-base-query-api.json
  operationId: post_knowledge-base-query
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

## Example

### Sample Request

```json JSON
{
   "question":"Suggest a woodworking project idea and how it would be built.",
   "chunkLimit":2,
   "tags":{
      "include":{
         "items":[
            "beginner",
            "small_scale"
         ],
         "operator":"and"
      }
   }
}
```

### Sample Response

```json
{
   "output":"A simple step stool is a great woodworking project idea that can be built using an 8-ft. 1×8 clear hardwood board, a 4-ft. 1×3 hardwood board, a power saw to crosscut the boards, and a jigsaw to cut the half-circles in the risers. The step stool requires minimal effort to create a beautiful piece and can be a great gift idea.",
   "chunks":[
      {
         "score":0.823885381,
         "chunkID":"868a1010-5e3a-11ee-ae78-de8d0308bfff",
         "documentID":"6515dccab4bc5400060fbc6a",
         "content":"One 8-ft. 1×8 clear hardwood board (actual width is 7-1/4 in. and actual thickness is 3/4 in.). Oak is a good choice because it’s readily available at home centers. One 4-ft. 1×3 hardwood board (actual width is 2-1/2 in. and actual thickness is 3/4 in.). Cut the 8-ft. board into: Two 22-in. riser boards Two 11-in. riser boards One 14-in. step board One 14-in. seat boardThis DIY step stool is an easy woodworking project which takes minimal effort to create a beautiful piece. Family HandymanHere’s a great gift idea that will draw raves. The joints are accurately made in seconds with a plate jointer, but don’t tell your admirers. You’ll also need a power saw to crosscut the boards and a jigsaw to cut the half-circles in the risers. The lumber you’ll need:",
         "source":{
            "type":"url",
            "name":"familyhandyman.com/article/simple-step-stool/",
            "url":"https://www.familyhandyman.com/article/simple-step-stool/",
            "tags":[
               "beginner",
               "small_scale"
            ]
         }
      },
      {
         "score":0.820069909,
         "chunkID":"868a0f34-5e3a-11ee-ae78-de8d0308bfff",
         "documentID":"6515dccab4bc5400060fbc6a",
         "content":"Here’s a great gift idea that will draw raves. The joints are accurately made in seconds with a plate jointer, but don’t tell your admirers. You’ll also need a power saw to crosscut the boards and a jigsaw to cut the half-circles in the risers. The lumber you’ll need:Simple Step Stool | Family Handyman Skip to main content Watch Free Pro New Homeowners Projects DIY University Shopping Subscribe Best Hot Tubs Home  Skills  Woodworking Simple Step Stool Andrew ZoellnerUpdated: Feb. 25, 2022This DIY step stool is an easy woodworking project which takes minimal effort to create a beautiful piece. Family Handyman",
         "source":{
            "type":"url",
            "name":"familyhandyman.com/article/simple-step-stool/",
            "url":"https://www.familyhandyman.com/article/simple-step-stool/",
            "tags":[
               "beginner",
               "small_scale"
            ]
         }
      }
   ],
   "queryTokens":456,
   "answerTokens":83,
   "totalTokens":539
}
```

## Specific examples on how to use the new [KB Tags](https://developer.voiceflow.com/reference/post_v3alpha-knowledge-base-tags)

Case 1: The user only wants documents with `tag1` :

```json
{
    "tags": {
        "include": {
            "items": ["tag1"],
        },
    }
}
```

Case 2: documents with `tag1` or documents without tags:

```json
{
    "tags": {
        "include": {
            "items": ["tag1"],
        },
        "includeAllNonTagged": True,
    }
}
```

Case 3: only documents with tags:

```json
{
    "tags": {
        "includeAllTagged": True,
    }
}
```

Case 4: only documents with tags, but without `tag1` :

```json
{
    "tags": {
        "exclude": { 
          "items": ["tag1"]
        },
        "includeAllTagged": True,
    }
}
```

Case 5: only documents with `tag1` and `tag2`, excluding those that also share `tag3` and `tag4`

```json
{
"question": "What is a Voiceflow?",
"chunkLimit": 1,
"tags": {
        "include": {
            "items": ["tag1", "tag2"],
            "operator": "and" 
        },
        "exclude": { 
          "items": ["tag3", "tag4"]
        }
    }
}
```