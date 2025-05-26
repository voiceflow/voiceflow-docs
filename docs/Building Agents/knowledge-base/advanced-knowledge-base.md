---
title: Advanced Knowledge Base
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
This article is a logical continuation of the previous [Knowledge Base](https://developer.voiceflow.com/v2.0/docs/knowledge-base) guide and goes over more advanced uses of the knowledge base. 

# Advanced Use of the Knowledge Base

If you want full control over your responses, you can use the KB Query API directly and retrieve the chunks themselves. This is especially valuable if you are dealing with sensitive information or want to provide an extremely high degree of accuracy to users when you have complex questions.

The video below shows an example of Pete from our team using this advanced method to prevent hallucinations for a bank. **Start at the 12:32 Timestamp.**

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FBHxhFd1vqkg%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DBHxhFd1vqkg&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FBHxhFd1vqkg%2Fhqdefault.jpg&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=BHxhFd1vqkg",
  "title": "Removing Hallucinations for a Wells Fargo Customer Support Banking Agent | Making Bots",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/BHxhFd1vqkg/hqdefault.jpg",
  "provider": "https://www.youtube.com/",
  "href": "https://www.youtube.com/watch?v=BHxhFd1vqkg",
  "typeOfEmbed": "youtube"
}
[/block]


# KB Query API

Instead of only interacting with the Knowledge Base from inside your agent, you can use the KB Query API to query the knowledge base, and can change more settings like the number of chunks returned or disabling synthesis, allowing you to do your own processing on the chunks retrieved. Learn more about the [API](https://developer.voiceflow.com/reference/post_knowledge-base-query), that can be called either using the API step in VF or called outside Voiceflow.

**KB Answer Not Found**: `null`

# Filter with metadata

You can refine your Knowledge Base search [queries](https://developer.voiceflow.com/reference/post_knowledge-base-query) using metadata. Voiceflow enables you to associate key-value pairs as metadata with documents and define filter expressions for your queries.

When you use metadata filters, the searches precisely retrieve the number of results that match the specified criteria. Typically, these filtered searches have even lower latency compared to searches without filters.

## Metadata Types and Structure

### Supported Types

- **String**: For textual data.
- **Number**: For numeric values.
- **Boolean**: True or false values.
- **Arrays**: Arrays containing any other supported type.
- **Objects**: Nested JSON objects for hierarchical data structures.

### Metadata Size Limitations

The system supports up to 10kb of metadata per chunk, allowing for detailed and extensive metadata without compromising performance.

### Example Metadata Payloads

```json
{
    "developer": {
        "name": "Jane Doe",
        "skills": ["Python", "JavaScript"],
      	"tags": ["t1", "t2", "t3", "t4"],
         "languages": [
              {
                  "name": "Russian"
              },
              {
                  "name": "German"
              }
          ]
    },
    "project": {
        "name": "AI Development",
        "deadline": "2024-12-31",
      	"price": 100
    }
}

```

## Metadata Query Language

> 📘 
> 
> Voiceflow's filtering query language is based on [MongoDB’s query and projection operators](https://docs.mongodb.com/manual/reference/operator/query/).

Voiceflow's query language for chunkDB is inspired by MongoDB, designed specifically for conversational metadata and supports a variety of operators for both straightforward and complex queries.

### Supported Operators

- **Equality and Comparison**
  - `$eq`: Equal to
  - `$ne`: Not equal to
  - `$gt`: Greater than
  - `$gte`: Greater than or equal to
  - `$lt`: Less than
  - `$lte`: Less than or equal to
- **Array Operations**
  - `$in`: Matches any of the values specified in an array
  - `$nin`: Does not match any of the values specified in an array
  - `$all`: Matches all values specified in an array
- **Logical Operators**
  - `$and`: Logical AND that combines multiple conditions
  - `$or`: Logical OR that combines multiple conditions

### Querying Nested Objects

Use dot notation to specify the path to nested fields, enabling precise queries on hierarchical data.

## More examples

### Case 1: Match All Specific Tags

**Objective**: Identify chunks that include every specified tag in the list.

```json
{
    "filters": {
        "developer.tags": {
            "$all": ["t1", "t2"]
        }
    }
}

```

### Case 2: Match Any of the Specified Tags

**Objective**: Find chunks containing any of the tags listed.

```json
{
    "filters": {
        "developer.tags": {
            "$in": ["t1", "t2"]
        }
    }
}

```

### Case 3: Exclude Chunks With Certain Tags

**Objective**: Filter out chunks that include any of the tags specified.

```json
{
    "filters": {
        "developer.tags": {
            "$nin": ["t1", "t2"]
        }
    }
}

```

### Case 4: Exact Match on Text Field

**Objective**: Retrieve chunks where the text field exactly matches a specified value.

```json
{
    "filters": {
        "developer.name": {
            "$eq": "Jane Doe"
        }
    }
}

```

### Case 5: Combination of Conditions

**Objective**: Search for chunks that either contain a specific tag or match a text value exactly.

```json
{
    "filters": {
        "$or": [
            {
                "developer.tags": {
                    "$in": ["t1"]
                }
            },
            {
                "developer.name": {
                    "$eq": "Jane Doe"
                }
            }
        ]
    }
}

```

### Case 6: Numeric Range and Specific Element in Array

**Objective**: Locate chunks priced within a certain range and containing a specific language.

```json
{
    "filters": {
        "project.price": {
            "$gte": 5,
            "$lt": 100
        },
        "developer.languages[].name": {
            "$eq": "Russian"
        }
    }
}

```

### Case 7: Querying Nested Object Attributes

**Objective**: Find chunks where the developer has specific attributes and the project meets certain deadlines.

```json
{
    "filters": {
        "$and": [
            {
                "developer.name": {
                    "$eq": "Jane Doe"
                }
            },
            {
                "developer.skills": {
                    "$in": ["JavaScript"]
                }
            },
            {
                "project.deadline": {
                    "$eq": "2024-12-31"
                }
            }
        ]
    }
}

```

## Inserting metadata to data sources

All supported data sources in the Knowledge Base support adding metadata which is then propagated to the relevant chunks that are extracted from the uploaded data. Depending on the type, follow the respective method below:

### 1. FILE Upload

[For uploading .txt, .docx or .pdf](https://docs.voiceflow.com/reference/post_v1-knowledge-base-docs-upload):

```curl
curl --request POST \\
  --url '<https://api.voiceflow.com/v1/knowledge-base/docs/upload?overwrite=true>' 
  --header 'Authorization: YOUR_DM_API_KEY' 
  --header 'Content-Type: multipart/form-data' 
  --form 'file=@/path/to/your/file.pdf' 
  --form 'metadata={"inner": {"text": "some test value", "price": 5, "tags": ["t1", "t2", "t3", "t4"]}}'

```

### 2. URL Upload

[To upload a URL:](https://docs.voiceflow.com/reference/post_v3alpha-knowledge-base-docs-upload-1)

```curl
curl --request POST \\
  --url '<https://api.voiceflow.com/v1/knowledge-base/docs/upload?maxChunkSize=1000&overwrite=true>'
  --header 'Authorization: YOUR_DM_API_KEY' 
  --header 'Content-Type: application/json' 
  --data '{
    "data": {
        "type": "url",
        "url": "<https://example.com/>",
        "metadata": {"test": 5}
    }
}'

```

### 3. TABLE Upload

To [upload table data](https://docs.voiceflow.com/reference/post_v1-knowledge-base-docs-upload-table) with metadata, structure your data as follows:

```curl
curl --request POST \
  --url 'https://api.voiceflow.com/v1/knowledge-base/docs/upload/table' \
  --header 'Authorization: YOUR_DM_API_KEY' \
  --header 'Content-Type: application/json' \
  --data '{
    "data": {
        "name": "products",
        "schema": {
            "searchableFields": ["name", "description"],
            "metadataFields": ["developer", "project"]
        },
        "items": [
            {
                "name": "example_name",
                "description": "example_description",
                "developer": {
                    "name": "Jane Doe",
                    "level": "senior",
                    "skills": ["Python", "JavaScript"],
                    "languages": [
                        {
                            "name": "Russian"
                        },
                        {
                            "name": "German"
                        }
                    ]
                },
                "project": {
                    "name": "AI Development",
                    "deadline": "2024-12-31"
                }
            }
        ]
    }
}'
```

By following these methods, you can ensure your data sources are enriched with metadata, enhancing the capability of your Voiceflow Knowledge Base to provide precise and contextually relevant search results.