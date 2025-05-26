---
title: Filtering with Metadata
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
# Advanced Query Filtering

Our new query filtering capabilities enable users to perform precise searches within their data using a robust set of operators. You can apply various filters to your data, such as:

* **Equality and Comparison:** `$eq`, `$ne`, `$gt`, `$gte`, `$lt`, `$lte`
* **Array Operations**: `$in`, `$nin`, `$all`
* **Logical Operators**: `$and`, `$or`

This means you can now create complex queries to retrieve exactly what you need, whether it’s finding products under a certain price, filtering by multiple tags, or combining multiple conditions.

## How to Use

### Inserting Metadata to Your Data Sources

Voiceflow supports adding metadata to your data sources through three methods: FILE upload, URL upload, and TABLE upload. Depending on the type of document being uploaded, follow the respective method below:

1. **FILE Upload**

```json
curl --request POST \ 
--url 'https://api.voiceflow.com/v1/knowledge-base/docs/upload?overwrite=true' \ 
--header 'Authorization: YOUR_DM_API_KEY' \
--header 'Content-Type: multipart/form-data' \ 
--header 'User-Agent: insomnia/8.0.0' \  
--form 'file=@/path/to/your/file.pdf' \  
--form 'metadata={"inner": {"text": "some test value", "price": 5, "tags": ["t1", "t2", "t3", "t4"]}}'
```

2. **URL Upload**

```json
curl --request POST  
  --url '<https://api.voiceflow.com/v1/knowledge-base/docs/upload>  
  --header 'Authorization: YOUR_DM_API_KEY'  
  --header 'Content-Type: application/json'  
  --data '{  
    "data": {  
        "type": "url",  
        "url": "<https://example.com/">,  
        "metadata": {"test": 5}  
    }  
}'
```

2. **TABLE Upload**

```json
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

## Practical Query Examples

Here are some practical examples to demonstrate the power of query filtering using the Query API:

* **Match All Specific Tags:** Identify chunks that include every specified tag in the list. (file upload example)

```json
{  
    "filters": {  
        "inner.tags": {  
            "$all": ["t1", "t2"]  
        }  
    }  
}
```

* **Match Any of the Specified Tags:** Find chunks containing any of the tags listed. (file upload example)

```json
{  
    "filters": {  
        "inner.tags": {  
            "$in": ["t1", "t2"]  
        }  
    }  
}
```

* **Exclude Chunks With Certain Metadata**: Filter out chunks that include any of the tags specified. (table example)

```json
{
    "filters": {
        "developer.skills": {
            "$nin": ["Python", "Rust"]
        }
    }
}

```

* **Combination of Conditions:** Search for chunks that either contain a specific tag or match a text value exactly. (file upload example)

```json
{
    "filters": {
        "$or": [
            {
                "inner.tags": {
                    "$in": ["t1"]
                }
            },
            {
                "inner.price": {
                    "$eq": 5
                }
            }
        ]
    }
}

```

<br />

## Example Query Request

```Text JSON
{
  "chunkLimit": 2,
  "synthesis": true,
  "settings": {
    "model": "claude-instant-v1",
    "temperature": 0.1,
    "system": "You are an AI FAQ assistant. Information will be provided to help answer the user's questions. Always summarize your response to be as brief as possible and be extremely concise. Your responses should be fewer than a couple of sentences. Do not reference the material provided in your response."
  },
  "question": "what are some museums I can visit",
  "filters": {
    "Price": {
      "$eq": 5
    }
  }
}
```
