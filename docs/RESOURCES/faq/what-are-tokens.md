---
title: What are Tokens?
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
## What is a token?

A token is determined by the AI model you use. For example, OpenAI (GPT models) and Anthropic (Claude models) considered a token as around 3-4 characters. To read more on how tokens are calculated you can read the documentation from either AI provider below.

- [Open AI Token Documentation](https://help.openai.com/en/articles/4936856-what-are-tokens-and-how-to-count-them)
- [Anthropic Token Documentation](https://docs.anthropic.com/en/docs/resources/glossary#tokens)

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FgZ3kBE8_AMk%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DgZ3kBE8_AMk&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FgZ3kBE8_AMk%2Fhqdefault.jpg&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=gZ3kBE8_AMk",
  "title": "Explained: AI Tokens & Optimizing AI Costs",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/gZ3kBE8_AMk/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=gZ3kBE8_AMk",
  "typeOfEmbed": "youtube"
}
[/block]


## How are tokens calculated?

A token represents a chunk of a word and is used by Large Language Models (LLMs) like GPT 4 to encode words. On average, tokens represent about three letters. It's not an easy-to-understand process, and is defined by encoding models, but if you want to play around with what token to character conversions are you can use [this OpenAI website](https://platform.openai.com/tokenizer) (token encodings will differ between providers).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9c4b587-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "400px"
    }
  ]
}
[/block]


Voiceflow is billed by our LLM providers (OpenAI, Anthropic, Google, etc...) by the tokens at their own prices. We then apply a multiplication factor based on how much more expensive their per token rates are than the rates for the Voiceflow tokens, since no matter which model you're using, it pulls from the same Voiceflow token pool.

For example, if Model A charged us $30 per 1M tokens, and the Voiceflow token price was $2.5 per 1M tokens (this will probably change after the time of writing), then using Model A from inside Voiceflow would be charged at a 15x token multiple. So a prompt (input and output) is total 3000 characters long would be 1000 tokens, it would cost 15000 Voiceflow tokens,  which would cost $0.0375.

Tokens are used by both the input (what is being sent to the AI model) and output (what is being received from the AI model). 

It is important to note, that the "Max Token" slider on the AI steps (shown below) only control the maximum output message. Depending on your agent design, there may be a large amount of information that is sent to the AI model as a part of your prompt, so even if your max tokens are very low, you could still use thousands of tokens.

## What are token multipliers?

Depending on the LLM provider and the cost of each model, there's an associated token multiplier, which represents how “expensive” a model is to use. We're updating token multipliers regularly, so check from inside the Voiceflow platform for the most up-to-date multipliers. You can see them anywhere you can pick a model, like in the Set AI step.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/262c4ae-image.png",
        null,
        "The token multipliers in-token as of July 19, 2024."
      ],
      "align": "center",
      "sizing": "300px",
      "caption": "The token multipliers in-token as of July 19, 2024."
    }
  ]
}
[/block]


## How many tokens do different features use in Voiceflow?

- **Knowledge Base**: A question and answer will use anywhere from 800-1500 tokens depending on the size of question and answer. This is because the Knowledge base passes in relevant information from your documentation to the AI model alongside your prompt.
- **Response AI Step (With Memory):** A question and answer when using the Response AI step **_with_** Memory will use anywhere from 150-2000 tokens. Voiceflow saves the last 3 conversation turns and passes those to your AI model to provide context for your answer.
- **Response AI Step (Without Memory):** A question and answer when using the Response AI step _**without**_, memory will use roughly 150-300 tokens.

_You can turn memory on or off via the setting on the Set AI and Response AI step below._

![](https://files.readme.io/76e422c-image.png)