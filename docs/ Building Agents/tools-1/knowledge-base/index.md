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

<Callout icon="ℹ️" theme="info">
  This is our recommended approach to querying the knowledge base, as it allows your agent to automatically interpret the information retrieved and turn it into human-readable responses.
</Callout>

<br />

To enable querying the knowledge base from inside an [Agent step](doc:agents), open your Agent step then turn on the **Knowledge base** toggle on the sidebar of the Agent popup.

<Video src="https://w17llroiln.ufs.sh/f/JH4JLc5mceYkd0EZs5lpu1oeO8lNrvZq7mJiBcVy0XgAjEbS" />

Once enabled, you can also choose to set the tool's LLM description. This tells your agent when to query the knowledge base. If you're using the knowledge base to store a specialized type of data - such as product information - we recommend updating the default instructions to be more specific.

The following advanced query settings are also available:

* **Query** - by default, Voiceflow will use the user's last message as the query used to search the knowledge base. You can override this behaviour by providing a custom query. Please note that the **exact** query entered into this box will be used - this isn't an input where you should enter a prompt!
* **Chunk limit** - this determines the maximum number of chunks that can be returned by the knowledge base. By default, three chunks will be returned.
* **Metadata filtering** - if you set custom metadata when [importing data to your knowledge base](doc:importing-data-to-the-knowledge-base), you can filter your agent's querying using this option. To do so, press the plus button and select a metadata key that exists in your imported data. Then, either enter a default value (to force a specific value to be used), or set the LLM description (to allow the agent to dynamically set this value).

<br />

<br />

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
