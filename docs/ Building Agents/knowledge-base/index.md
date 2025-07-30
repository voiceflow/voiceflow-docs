---
title: Knowledge base
excerpt: >-
  The Knowledge Base lets your Voiceflow Assistant retrieve and summarize
  answers from your own data. 
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

![](https://files.readme.io/822b2438fabe08c6db61c31b93d4c23ec6eb5ad2817d0305776510e61c0e5c9f-CleanShot_2025-07-30_at_13.52.292x.png)

# How it works

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

# Using the Knowledge Base

* The Knowledge Base (KB) provides a response in the following way
  1. It uses the question provided to search the Knowledge Base and receive relevant pieces of information. If the question does not have an answer in the KB, it will say that it cannot find an answer. *It is important that you pass a well-defined question to the Knowledge Base.*
  2. It sends those pieces of information along with your custom instructions and prompt settings to an AI model to summarize the answer. If the AI model determines that the answer to the question is not in the relevant information, it will say that it cannot find an answer.
* Responses from the knowledge base can use the Agent step or the Knowledge Base Query API directly.

To learn how to import data into your Knowledge Base, read the <Anchor label="docs" target="_blank" href="https://docs.voiceflow.com/docs/importing-data-to-the-knowledge-base#/">docs</Anchor>.

## Agent step

The knowledge base can directly be integrated through the Agent step. Ensure the knowledge base toggled is enabled.

![](https://files.readme.io/19b0ee3386ee4854b46ae3c637c25ba7c62408bbd71a3448e1e8b27d78833702-CleanShot_2025-07-30_at_14.17.322x.png)

## KB search step

<br />

The Knowledge Base is a vector-powered system that lets your Voiceflow Assistant retrieve and summarize answers from your own documents and website data.

Ask ChatGPT

The Knowledge Base is a vector-powered system that lets your Voiceflow Assistant retrieve and summarize answers from your own documents and website data.

Ask ChatGPT

## Debugging the Knowledge Base

The Knowledge Base isn't giving me an answer?

There are two reasons the KB will not provide an answer. It's important to test each one to see what the reason is.

1. **No relevant chunks are found:** The question field that you send to the knowledge base is what looks for relevant chunks. Nothing else. If that question is not well-defined, then the system will not be able to find relevant chunks.
   1. \*\*How to identify this problem:\*\*You can tell this is the issue by using the 'preview' in the KB. If no sources are returned, then it was not able to find relevant chunks. If sources are returned, then proceed to #2.
   2. \*\*How to fix this problem:\*\*If you find that users are asking questions that are too simple, you can either try to add more relevant information to the KB or to use the Set AI step to have an AI restructure the users question to be better defined.
      1. **Example**: You are trying to provide wine recommendations and have information in the KB about different wines and their flavors. But rather than ask 'what wines are fruity and full-bodied' the user asks 'romantic dinner wine'. You don't have anything in your KB remotely related to romantic dinners. You can either add more information into the KB or use the Set AI step to use AI to reformat the user's question.
2. **The AI determined that the Answer to the user's question is not provided in the chunks that were returned**: It's important to remember that the KB works in two parts, like any other Vector database. 1) It uses the question to find relevant chunks. 2) It sends those to an AI to use to create an answer.
   1. **How to identify this problem**: Using the preview function in the KB, there is no answer provided, but sources are returned. If the sources are relevant, then it's a prompt and model issue.
   2. **How to fix this problem**: This is likely an issue with your prompt or (more often), the AI model you are using. Experiment with changing the model to see if that fixes the problem.

## Advanced Knowledge Base usage

To learn more about advanced ways of using the Knowledge Base, read this next guide.

<LinkCard type="Doc" title="Advanced Knowledge Base usage" description="Learn how to supercharge your knowledge base with file metadata to ensure your agent delivers more accurate, relevant, and context-aware responses." href="https://docs.voiceflow.com/docs/advanced-knowledge-base#/" />