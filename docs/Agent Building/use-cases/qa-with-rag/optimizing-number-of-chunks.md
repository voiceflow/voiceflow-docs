---
title: Optimizing the number of chunks
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
## Configuring via the Knowledge Base settings

Within the Knowledge Base CMS settings you can set the number of chunks to retrieve. Fetching more chunks will provide more context to your RAG solution, using fewer will save on tokens. We've found that most applications work well with a default of 3 chunks, but it's important to experiment for your use case!

![](https://files.readme.io/86f9402-CleanShot_2024-05-12_at_16.20.482x.png)

<br />

## Using the KB Api

You can also use the [KB API](https://developer.voiceflow.com/reference/post_knowledge-base-query) to fetch a number of chunks.

```
{
  "question": "{last_utterance}",
  "chunkLimit": 3,
  "synthesis": false,
  "tags": {
    "includeAllTagged": true,
    "includeAllNonTagged": true
  }
}
```

<br />

For more details checkout the cookbook recipe _[Advanced Rag Filtering and Tagging](https://dash.readme.com/project/voiceflow-developer/v1.2/docs/advanced-rag-filtering-and-tagging)_