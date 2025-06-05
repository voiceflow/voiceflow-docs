---
title: Knowledge base
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

<Embed url="https://www.youtube.com/watch?v=iQJ9ecSwHxg" title="Getting Accurate AI Answers in Voiceflow" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/iQJ9ecSwHxg/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=iQJ9ecSwHxg" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FiQJ9ecSwHxg%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DiQJ9ecSwHxg%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FiQJ9ecSwHxg%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

To learn more about how the Knowledge Base works, read [this](https://developer.voiceflow.com/v2.0/docs/how-does-the-knowledge-base-work) guide.

# Using the Knowledge Base

* The Knowledge Base (KB) provides a response in the following way
  1. It uses the question provided to search the Knowledge Base and receive relevant pieces of information. If the question does not have an answer in the KB, it will say that it cannot find an answer. *It is important that you pass a well-defined question to the Knowledge Base.*
  2. It sends those pieces of information along with your custom instructions and prompt settings to an AI model to summarize the answer. If the AI model determines that the answer to the question is not in the relevant information, it will say that it cannot find an answer.
* Responses from the knowledge base can use the Response AI step or the Knowledge Base Query API directly. The Response AI step is the simplified version, while using the KB Query API will give you access to the raw information behind the response for further processing. Many advanced customers prefer to do this so they can do things like check for hallucinations or further customize the responses.

> 📘 Advanced Use
>
> We recommend using the Response AI step to start, then migrating to using the KB Query API through the API step when you wish to have more control over your responses.
>
> Below is an example of how you can use the Query API directly to provide additional information with your AI response.
>
> <Embed url="https://www.youtube.com/watch?v=JotMkrO9INg" title="Create an advanced AI FAQ chatbot that recommends sources" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/JotMkrO9INg/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=JotMkrO9INg" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FJotMkrO9INg%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DJotMkrO9INg%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FJotMkrO9INg%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22640%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## AI Steps in KB Mode

**Initiated when:**

* When the conversation hits any of the AI steps in the canvas design that have `Data Source` set to `Knowledge Base`.

  ![](https://files.readme.io/b2aeb52-image.png)

**KB Answer Not Found:**

* If the “Not found path” toggle is enabled and a KB Answer is not found, the user will be routed through the “Not found” path in your design.

![](https://files.readme.io/df13ae8-image.png)

* If the “Not found path” toggle is disabled and a KB Answer is not found, the user will be sent a “Unable to find relevant answer” message.

<br />

* `Global No Match` response initiated (either Static or Generative depending on Settings):

<Image align="center" width="600px" src="https://files.readme.io/30a4d0d-image.png" />

## KB Preview

Initiated when you try to query the KB from the Knowledge Base CMS rather than from an AI step using KB.

![](https://files.readme.io/2975bfb-CleanShot_2024-07-02_at_08.58.402x.png)

**KB Answer Not Found:**

* `“[not found] Unable to find relevant answer.”`

## Advanced Knowledge Base usage

To learn more about advanced ways of using the Knowledge Base, read this next guide.

## Debugging the Knowledge Base

The Knowledge Base isn't giving me an answer?

There are two reasons the KB will not provide an answer. It's important to test each one to see what the reason is.

1. **No relevant chunks are found:** The question field that you send to the knowledge base is what looks for relevant chunks. Nothing else. If that question is not well-defined, then the system will not be able to find relevant chunks. 
   1. **How to identify this problem:**&#x59;ou can tell this is the issue by using the 'preview' in the KB. If no sources are returned, then it was not able to find relevant chunks. If sources are returned, then proceed to #2.
   2. **How to fix this problem:**&#x49;f you find that users are asking questions that are too simple, you can either try to add more relevant information to the KB or to use the Set AI step to have an AI restructure the users question to be better defined.
      1. **Example**: You are trying to provide wine recommendations and have information in the KB about different wines and their flavors. But rather than ask 'what wines are fruity and full-bodied' the user asks 'romantic dinner wine'. You don't have anything in your KB remotely related to romantic dinners. You can either add more information into the KB or use the Set AI step to use AI to reformat the user's question.
2. **The AI determined that the Answer to the user's question is not provided in the chunks that were returned**: It's important to remember that the KB works in two parts, like any other Vector database. 1) It uses the question to find relevant chunks. 2) It sends those to an AI to use to create an answer.
   1. **How to identify this problem**: Using the preview function in the KB, there is no answer provided, but sources are returned. If the sources are relevant, then it's a prompt and model issue. 
   2. **How to fix this problem**: This is likely an issue with your prompt or (more often), the AI model you are using. Experiment with changing the model to see if that fixes the problem.