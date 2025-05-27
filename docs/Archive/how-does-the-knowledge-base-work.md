---
title: How does the Knowledge Base work
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
This article is for anyone interested in learning more about the inner workings of Voiceflow, giving you more context on the behavior of your agents. You don't need to know all this information to use the [Knowledge Base](https://developer.voiceflow.com/v2.0/docs/knowledge-base).

Our Knowledge Base (KB) has two unique services that make it function:

1. A **parser** - triggered when you upload a KB document.
2. A **retriever** - triggered when your user asks a question that hits the KB.

## Step-by-Step

### You upload a KB Document to the parser service

![](https://files.readme.io/884cf7f-image.png)

1. The KB doc is uploaded via Voiceflow UI (aka "Creator App" or "Creator Tool") or API.
2. The KB doc is securely stored.
3. The Parser service reads the KB doc from storage and "chunks" the content using different techniques (Note: with the KB Upload APIs you can use maxChunkSize to moderate how big the chunks are, but you cannot dictate how many chunks are parsed within a document today).
4. An embedding model is used to convert each chunk into a vector (aka “embedding”) that looks like \[1.243, 5.1342, ...] and represents its “meaning.”
   1. Computer programs don’t ‘understand’ spoken/written language as humans can. There needs to be a numerical representation of words to help programs understand. Each chunk from a KB doc is converted into a numerical representation (vector, aka “embedding”) of the MEANING behind the words in the chunk. More on why this is necessary in the Retriever section.\
      *Note*: Embedding models cost money to use, usually per token. The more files you upload, the more you are charged for embedding tokens.\
      In Voiceflow, we don't charge for the upload or embedding process.
5. The vector is placed in a vector db.

   1. You can think of this vector as a specific 'point” in “space.” All these points are some “distance” from each other, and the distance between two of these points (vectors) is how similar in meaning different chunks of text are.

      ![](https://files.readme.io/5914dff-image.png)

### User asks a question that hits the KB through the retriever service

![](https://files.readme.io/3693da9-image.png)

1. The retriever service gets the `question` and turns it into a vector.
2. The question vector is searched against the `vectorDB` by a similarity score, returning the most similar number of chunks (`Chunk Limit` defines how many chunks) in descending order by similarity score.
   1. **Similarity score?**\
      The similarity score is determined by something called semantic search. This goes beyond keyword matching and refers to contextual similarity in meaning between words and phrases. (i.e. “The dog is a nightmare to train.” and “The puppy is stubborn and does not listen to commands” do not share keywords. However, they have high similarity semantically.) So the question can be semantically compared to the KB doc chunks that exist. The “closest” vectors to the question are those with the highest similarity. The retriever will return a number of chunks (Chunk Limit in KB Settings) based on this vector proximity.
   2. **Chunk Limit?**\
      `Chunk Limit` is the KB setting that controls the amount of chunks are retrieved from the vector db and used to synthesize the response. This setting aims to provide flexibility to increase the accuracy of responses in line with certain use cases.\
      **How does the number of chunks retrieved affect the accuracy of the KB?**\
      In theory, the more chunks retrieved - the more accurate the response, and the more tokens consumed. In reality, the "accuracy" tied to chunks is strongly associated with how the KB data sources are curated.\
      If the KB data sources are curated so that topics are grouped together, this should be more than enough to accurately answer the question. However, if information is scattered throughout many different KB data sources, then likely more chunks of smaller size will increase the accuracy of the response.\
      You can control the max chunk size of your data sources with the Upload/Replace KB doc APIs, using the query parameter: maxChunkSize.\
      **Ultimately, in order to provide the best KB response 'accuracy' while optimizing token consumption, we recommend to limit the number of data sources and group topics inside those data sources.**

### Runtime Service:

1. We take the:
   1. returned chunks +
   2. Knowledge Base Settings inputs +
   3. question)

...and ask the LLM to give us an answer.

This step is called **answer synthesis**.

The internal prompts we use to iterate over time but are along the lines of, “using conversation history and user-provided instructions, answer the question sourcing information only found in Knowledge Base.”

**This LLM request has`query and answer tokens` that you are charged for**. You can see these token totals in a response citation while testing in Debug mode on Voiceflow:

![](https://files.readme.io/6951e4c-image.png)

2. VF outputs the response to the user.
   1. See the overview of the KB instances below to understand how a response appears when KB cannot answer.
