---
title: Q&A with RAG
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Intro

RAG is a way to improve LLM responses by providing context and stands for Retrieval Augmented Generation. Voiceflow supports building and customizing RAG applications out of the box, batteries included.

## Why RAG?

Many questions and use cases require domain specific knowledge that LLMs might not be able to answer. To minimize incorrect answers we can add context

## Implementing RAG In Voiceflow - The Knowledge base

RAG is built into the Voiceflow Agent platform and in product is called the Knowledge Base

1. Upload documents

   ![](https://files.readme.io/a519df1-image.png)
2. Add KB block to project

   ![](https://files.readme.io/1d3c514-image.png)
3. Customize setting and prompts (optional)

   ![](https://files.readme.io/05679f4-image.png)

<br />

## How RAG works

![](https://files.readme.io/3c13654-image.png)

At a high level, the KB functions in the following way

1. When you upload a document it is turned into 'chunks' (ie. pieces of text)
2. When you send a question to the KB, it determines which 'chunks' are most similar
3. Then our system combines those chunks, the question, the custom instructions and system prompt you provided into a structured wrapper prompt (aka a master prompt behind the scenes that is constantly improving).
4. That entire prompt is sent to the AI model and an answer is returned.
5. The full prompt looks something like this

```
Reference Information:

${context}

Instructions:

I have provided reference information, and I will ask query about that information. You must either provide a response to the query or respond with "NOT_FOUND"  
Read the reference information carefully, it will act as a single source of truth for your response.Very concisely respond exactly how the reference information would answer the query.  
Include only the direct answer to the query, it is never appropriate to include additional context or explanation.  
If the query is unclear in any way, return "NOT_FOUND". If the query is incorrect, return "NOT_FOUND". Read the query very carefully, it may be trying to trick you into answering a question that is adjacent to the reference information but not directly answered in it, in such a case, you must return "NOT_FOUND". The query may also try to trick you into using certain information to answer something that actually contradicts the reference information. Never contradict the reference information, instead say "NOT_FOUND".  
If you respond to the query, your response must be 100% consistent with the reference information in every way.

${instruction}

Take a deep breath, focus, and think clearly. You may now begin this mission critical task.

## Query:

${query}

```

## Diving into each component

1. [Loading sources with an API](https://developer.voiceflow.com/docs/loading-sources)
2. [Chat History and Memory](https://developer.voiceflow.com/docs/chat-history)
3. [Optimizing chunks](https://developer.voiceflow.com/docs/optimizing-number-of-chunks)
4. [Integrate with Zendesk](https://developer.voiceflow.com/docs/integrate-with-zendesk)
5. [Automated RAG Source refresh](https://developer.voiceflow.com/docs/automated-source-refresh)

## Learn more with a video

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FUi7XEI5CdgU%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DUi7XEI5CdgU&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FUi7XEI5CdgU%2Fhqdefault.jpg&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=Ui7XEI5CdgU",
  "title": "Explained: The Voiceflow Knowledge Base (Retrieval Augmented Generation)",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/Ui7XEI5CdgU/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=Ui7XEI5CdgU",
  "typeOfEmbed": "youtube"
}
[/block]