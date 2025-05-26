---
title: Query
excerpt: ''
api:
  file: knowledge-base-query-api-1.json
  operationId: post_knowledge-base-query
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
This API endpoint allows you to query the Voiceflow Knowledge Base and retrieve answers to user questions. Use this endpoint to send a question and receive a synthesized answer or relevant document chunks from the Knowledge Base.

## Available Models

* gpt-3.5-turbo
* gpt-4-turbo
* gpt-4
* claude-instant-v1
* claude-v1
* claude-v2
* claude-3-haiku
* claude-3-sonnet
* claude-3.5-sonnet
* claude-3-opus
* gemini-pro-1.5

## Examples

### Sample Request

```json
{  
  "question": "What are the benefits of AI?",  
  "settings": {  
    "model": "gpt-4-turbo",  
    "temperature": 0.2  
  }  
}
```

```json
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

<br />

### Sample Response

```json
{  
   "output":"A simple step stool is a great woodworking project idea that can be built using an 8-ft. 1×8 clear hardwood board, a 4-ft. 1×3 hardwood board, a power saw to crosscut the boards, and a jigsaw to cut the half-circles in the risers. The step stool requires minimal effort to create a beautiful piece and can be a great gift idea.",  
   "chunks":\[  
      {  
         "score":0.823885381,  
         "chunkID":"868a1010-5e3a-11ee-ae78-de8d0308bfff",  
         "documentID":"6515dccab4bc5400060fbc6a",  
         "content":"One 8-ft. 1×8 clear hardwood board (actual width is 7-1/4 in. and actual thickness is 3/4 in.). Oak is a good choice because it’s readily available at home centers. One 4-ft. 1×3 hardwood board (actual width is 2-1/2 in. and actual thickness is 3/4 in.). Cut the 8-ft. board into: Two 22-in. riser boards Two 11-in. riser boards One 14-in. step board One 14-in. seat boardThis DIY step stool is an easy woodworking project which takes minimal effort to create a beautiful piece. Family HandymanHere’s a great gift idea that will draw raves. The joints are accurately made in seconds with a plate jointer, but don’t tell your admirers. You’ll also need a power saw to crosscut the boards and a jigsaw to cut the half-circles in the risers. The lumber you’ll need:",  
         "source":{  
            "type":"url",  
            "name":"familyhandyman.com/article/simple-step-stool/",  
            "url":"<https://www.familyhandyman.com/article/simple-step-stool/">,  
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
            "url":"<https://www.familyhandyman.com/article/simple-step-stool/">,  
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
