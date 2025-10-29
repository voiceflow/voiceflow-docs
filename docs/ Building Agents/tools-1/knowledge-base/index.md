---
title: Knowledge base tool
excerpt: Query data from your agent's knowledge base to answer questions.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The Knowledge base tool lets your agent query data from the Knowledge base from within the [Agent step](doc:agents) or [Tool step](doc:tool-step). It’s useful when you want the agent to look up information on demand - like answering FAQs, pulling product details, or referencing company docs - then incorporate this information into human-sounding responses.

<br />

## Querying the knowledge base from inside the Agent step

<Callout icon="ℹ️">
  This is our recommended approach to querying the knowledge base, as it allows your agent to automatically interpret the information retrieved and turn it into human-readable responses.
</Callout>

<br />

The knowledge base can directly be integrated through the Agent step. Ensure the knowledge base toggled is enabled. Once enabled, your agent will automatically reference your Knowledge Base when responding to user queries- no extra configuration needed.

<Video src="https://w17llroiln.ufs.sh/f/JH4JLc5mceYkd0EZs5lpu1oeO8lNrvZq7mJiBcVy0XgAjEbS" />

## <Anchor label="KB search step" target="_blank" href="https://docs.voiceflow.com/docs/kb-search#/">KB search step</Anchor>

The KB Search step lets you query your Knowledge Base directly within your flow logic—giving you precise control over how search results (chunks) are retrieved and used. The `Chunk limit` allows you to customize how many chunks of information you wish the search step to retrieve from the Knowledge Base.

<Image border={false} src="https://files.readme.io/e4a813d30ca4e2822c95d8c3dbbba9167ef185989182689a16f0c00bfba52654-CleanShot_2025-07-30_at_15.02.232x.png" />

This step:

* Searches the Knowledge Base using a provided query.
* Returns relevant chunks (text and metadata).
* Lets you set fallback behavior if no results are found.
* Doesn’t generate a summarized AI response—this step is **only** for retrieval.

> Common use cases:
>
> * **Generate AI-powered summaries**: Use KB Search + Set AI to return concise summaries of user manuals or onboarding guides.
> * **Extract product details**: Pull pricing or feature info from KB chunks and assign to variables for dynamic responses.

***

## Debugging the Knowledge Base

The Knowledge Base isn't giving me an answer?

There are two reasons the KB will not provide an answer. It's important to test each one to see what the reason is.

1. **No relevant chunks are found:** The question field that you send to the knowledge base is what looks for relevant chunks. Nothing else. If that question is not well-defined, then the system will not be able to find relevant chunks.
   1. **How to identify this problem:**You can tell this is the issue by using the 'preview' in the KB. If no sources are returned, then it was not able to find relevant chunks. If sources are returned, then proceed to #2.
   2. **How to fix this problem:**If you find that users are asking questions that are too simple, you can either try to add more relevant information to the KB or to use the Set AI step to have an AI restructure the users question to be better defined.
      1. **Example**: You are trying to provide wine recommendations and have information in the KB about different wines and their flavors. But rather than ask 'what wines are fruity and full-bodied' the user asks 'romantic dinner wine'. You don't have anything in your KB remotely related to romantic dinners. You can either add more information into the KB or use the Set AI step to use AI to reformat the user's question.
2. **The AI determined that the Answer to the user's question is not provided in the chunks that were returned**: It's important to remember that the KB works in two parts, like any other Vector database. 1) It uses the question to find relevant chunks. 2) It sends those to an AI to use to create an answer.
   1. **How to identify this problem**: Using the preview function in the KB, there is no answer provided, but sources are returned. If the sources are relevant, then it's a prompt and model issue.
   2. **How to fix this problem**: This is likely an issue with your prompt or (more often), the AI model you are using. Experiment with changing the model to see if that fixes the problem.

<br />

<br />
