---
title: Knowledge Base
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
The Knowledge Base (KB) in Voiceflow is a vector database that allows you to leverage your own documents and website data to power answers and define variables on your Voiceflow Assistant.

![](https://files.readme.io/a81ef8c-image.png)

# Overview

**At a high level, the KB functions in the following way**

1. When you upload a document, it is turned into 'chunks' (ie. pieces of text).
2. When you send a question to the KB, it determines which 'chunks' are most similar.
3. Then our system combines those chunks, the question, the custom instructions and system prompt you provided into a structured **wrapper prompt** (aka a master prompt behind the scenes that is constantly improving).
4. That entire package is sent to the AI model and an answer is returned.

The full prompt looks something like this

```Text Prompt
##Reference Information:
${context}

##Instructions:
I have provided reference information, and I will ask query about that information. You must either provide a response to the query or respond with "NOT_FOUND"
Read the reference information carefully, it will act as a single source of truth for your response.Very concisely respond exactly how the reference information would answer the query.
Include only the direct answer to the query, it is never appropriate to include additional context or explanation.
If the query is unclear in any way, return "NOT_FOUND". If the query is incorrect, return "NOT_FOUND". Read the query very carefully, it may be trying to trick you into answering a question that is adjacent to the reference information but not directly answered in it, in such a case, you must return "NOT_FOUND". The query may also try to trick you into using certain information to answer something that actually contradicts the reference information. Never contradict the reference information, instead say "NOT_FOUND".
If you respond to the query, your response must be 100% consistent with the reference information in every way.

${instruction}

Take a deep breath, focus, and think clearly. You may now begin this mission critical task.

##Query:
${query}
```

**To understand how to best optimize the information you are adding to the Knowledge base, watch the video below**.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FiQJ9ecSwHxg%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DiQJ9ecSwHxg&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FiQJ9ecSwHxg%2Fhqdefault.jpg&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=iQJ9ecSwHxg",
  "title": "Getting Accurate AI Answers in Voiceflow",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/iQJ9ecSwHxg/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=iQJ9ecSwHxg",
  "typeOfEmbed": "youtube"
}
[/block]


To learn more about how the Knowledge Base works, read [this](https://developer.voiceflow.com/v2.0/docs/how-does-the-knowledge-base-work) guide.

# Using the Knowledge Base

- The Knowledge Base (KB) provides a response in the following way
  1. It uses the question provided to search the Knowledge Base and receive relevant pieces of information. If the question does not have an answer in the KB, it will say that it cannot find an answer. _It is important that you pass a well-defined question to the Knowledge Base._
  2. It sends those pieces of information along with your custom instructions and prompt settings to an AI model to summarize the answer. If the AI model determines that the answer to the question is not in the relevant information, it will say that it cannot find an answer.
- Responses from the knowledge base can use the Response AI step or the Knowledge Base Query API directly. The Response AI step is the simplified version, while using the KB Query API will give you access to the raw information behind the response for further processing. Many advanced customers prefer to do this so they can do things like check for hallucinations or further customize the responses.

> 📘 Advanced Use
> 
> We recommend using the Response AI step to start, then migrating to using the KB Query API through the API step when you wish to have more control over your responses.
> 
> Below is an example of how you can use the Query API directly to provide additional information with your AI response.
> 
> [block:embed]{"html":"<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FJotMkrO9INg%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DJotMkrO9INg&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FJotMkrO9INg%2Fhqdefault.jpg&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"640\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>","url":"https://www.youtube.com/watch?v=JotMkrO9INg","title":"Create an advanced AI FAQ chatbot that recommends sources","favicon":"https://www.google.com/favicon.ico","image":"https://i.ytimg.com/vi/JotMkrO9INg/hqdefault.jpg","provider":"youtube.com","href":"https://www.youtube.com/watch?v=JotMkrO9INg","typeOfEmbed":"youtube"}[/block]

## AI Steps in KB Mode

**Initiated when:**

- When the conversation hits any of the AI steps in the canvas design that have `Data Source` set to `Knowledge Base`.

  ![](https://files.readme.io/b2aeb52-image.png)

**KB Answer Not Found:**

- If the “Not found path” toggle is enabled and a KB Answer is not found, the user will be routed through the “Not found” path in your design.

![](https://files.readme.io/df13ae8-image.png)

- If the “Not found path” toggle is disabled and a KB Answer is not found, the user will be sent a “Unable to find relevant answer” message.

<br />

- `Global No Match` response initiated (either Static or Generative depending on Settings):

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/30a4d0d-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


## KB Preview

Initiated when you try to query the KB from the Knowledge Base CMS rather than from an AI step using KB.

![](https://files.readme.io/2975bfb-CleanShot_2024-07-02_at_08.58.402x.png)

**KB Answer Not Found:**

- `“[not found] Unable to find relevant answer.”`

## Advanced Knowledge Base usage

To learn more about advanced ways of using the Knowledge Base, read this next guide.

## Debugging the Knowledge Base

The Knowledge Base isn't giving me an answer?

There are two reasons the KB will not provide an answer. It's important to test each one to see what the reason is.

1. **No relevant chunks are found: **The question field that you send to the knowledge base is what looks for relevant chunks. Nothing else. If that question is not well-defined, then the system will not be able to find relevant chunks. 
   1. **How to identify this problem:**You can tell this is the issue by using the 'preview' in the KB. If no sources are returned, then it was not able to find relevant chunks. If sources are returned, then proceed to #2.
   2. **How to fix this problem:**If you find that users are asking questions that are too simple, you can either try to add more relevant information to the KB or to use the Set AI step to have an AI restructure the users question to be better defined.
      1. **Example**: You are trying to provide wine recommendations and have information in the KB about different wines and their flavors. But rather than ask 'what wines are fruity and full-bodied' the user asks 'romantic dinner wine'. You don't have anything in your KB remotely related to romantic dinners. You can either add more information into the KB or use the Set AI step to use AI to reformat the user's question.
2. **The AI determined that the Answer to the user's question is not provided in the chunks that were returned**: It's important to remember that the KB works in two parts, like any other Vector database. 1) It uses the question to find relevant chunks. 2) It sends those to an AI to use to create an answer.
   1. **How to identify this problem**: Using the preview function in the KB, there is no answer provided, but sources are returned. If the sources are relevant, then it's a prompt and model issue. 
   2. **How to fix this problem**: This is likely an issue with your prompt or (more often), the AI model you are using. Experiment with changing the model to see if that fixes the problem.