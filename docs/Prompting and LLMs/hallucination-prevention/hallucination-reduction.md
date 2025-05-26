---
title: Hallucination reduction
excerpt: Learn how to reduce hallucinations when working with LLMs.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## How to mitigate Hallucinations

While it's challenging to completely eliminate hallucinations, there are several key strategies to reduce their occurrence:

- **Grounding to a source of truth:** Provide the LLM with verified, factual information. This can be done through:  
  In-prompt grounding: Include relevant facts directly in the prompt.
- **Retrieval-Augmented Generation (RAG):** Retrieve information from a curated knowledge base before generating a response.
- **Fine-tuning on domain-specific data:** For specialized applications, train the model on high-quality, relevant data.
- **Prompt engineering:** Carefully craft prompts to guide the model towards accurate responses, including instructions to avoid speculation or indicate uncertainty.
- **Output filtering:** Implement post-processing to filter out likely hallucinations, such as fact-checking against a database.
- **Human-in-the-loop:** For critical applications, incorporate human review and verification of LLM outputs.

By combining these strategies and continuously refining your approach, you can significantly reduce the occurrence and impact of hallucinations in LLM applications.  
A framework to reduce hallucinations

## Hallucination mitigation framework example

At Voiceflow, we've developed a sophisticated framework that significantly reduces hallucinations in LLM responses. Our approach combines multiple models and strategic checks to achieve an optimal balance of speed, cost, and accuracy. 

Here's how it works:

### Step 1: RAG optimized query

Instead of simply passing the user's utterance directly to our knowledge base, we first reformulate the user's question to optimize it for our knowledge base. This step ensures we're asking the right question to get the most relevant information.

We do so with this prompt:

```
Based on the conversation history:

{vf_memory}

And the user's last response:

{last_utterance}

Generate a question that's ideal for retrieval augmented generation.
```

 This step allows us to more accurately query our knowledge base based on the user's question. We are using variable injection, adding context to the prompt using Voiceflow's variable system. 

Here, we use smaller, cost-effective LLMs (e.g., Haiku or GPT-4-mini) to optimize for speed and cost.

For this framework, we use two core mitigation techniques:

- Prompt engineering: Crafting the input to extract the most relevant informatio
- Grounding: Preparing to link the response to a verified source of truth

### Step 2: Knowledge Base Query

Next, we store the response from Step 1 in a variable and send that refined query our Knowledge Base.

The Knowledge Base then returns chunks of relevant information, each with an associated relevance score. 

This approach allows us to ground the LLM to a source of truth, the returned chunks of relevant information, from our Knowledge Base.

### Step 3: Chunk score filtering

Next, we evaluate the relevance of the retrieved information based on chunk scores. If the top chunk score is below a set threshold (we typically use 80%), we don't proceed with answering.

### Step 4: Clarification Check

Next, we analyze the chunks for vagueness or conflicts in the user's question. If necessary, we generate a clarifying question and refine our knowledge base query.

For this section, as it requires more advanced reasoning, we use more powerful models like Claude 3.5 Sonnet or GPT-4.

### Step 5: Response Generation

Next, we generate a response to the user's question using the retrieved and verified information chunks. 

For this section we go back to using smaller models (e.g., Haiku or GPT-4-mini) for speed and cost-efficiency.

### Step 6: Consistency Check

Next, we verify the consistency between the retrieved information and the generated answer.

Here, we use more powerful models (e.g., Claude 3.5 Sonnet or GPT-4) as they have better reasoning abilities for the consistency check.

### Step 7: Inconsistency Resolution

If the models find inconsistencies in the generated response relative to the provided chunks, we attempt to rewrite the response, escalating to more powerful models if needed, and redo the above 3 steps. If the process is unsuccessful again, we return a response to the user that states we cannot complete the request, instead of returning a hallucination.

For this step, we first use smaller models (e.g., Haiku or GPT-4-mini), and then upgrade to larger models for the second attempt (e.g., Claude 3.5 Sonnet or GPT-4).

### Hallucination reduction framework summary

This framework ensures that responses are grounded in verified information, reduces the likelihood of hallucinations, and maintains a balance between accuracy, speed, and cost-effectiveness. While we don't directly incorporate human-in-the-loop verification for each interaction, our multi-stage checking process serves a similar function, ensuring that responses are accurate, relevant, and consistent with our verified information. Additionally, by sending events to a business insights tool, you could monitor where the model might be hallucinating and understand why. This data-driven approach would enable you to continuously improve the documentation in your knowledge base, refine your prompts, and tweak the overall system, to lead to an ever-more reliable experience.

Watch below to see the framework in action:

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FK-WDEKex6gM%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DK-WDEKex6gM&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FK-WDEKex6gM%2Fhqdefault.jpg&key=02466f963b9b4bb8845a05b53d3235d7&type=text%2Fhtml&schema=youtube\" width=\"640\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/embed/K-WDEKex6gM?si=eua7NJt4_2xVcA9W",
  "title": "Hallucination Mitigation Framework",
  "favicon": "https://www.youtube.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/K-WDEKex6gM/hqdefault.jpg",
  "provider": "https://www.youtube.com/",
  "href": "https://www.youtube.com/embed/K-WDEKex6gM?si=eua7NJt4_2xVcA9W",
  "typeOfEmbed": "youtube"
}
[/block]