---
title: Token Top-up
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
If you're looking to learn what tokens are, look [here](https://developer.voiceflow.com/docs/what-are-tokens).

# Purchasing Tokens

Additional tokens can **only be purchased by paid customers**. (Pro, Teams or Enterprise plans).

If you are on a paid plan, follow the instructions below to purchase more tokens. **The price for additional tokens is $5 per 2 Million tokens.**

## Pro & Teams

Hover on the AI icon in your Assistant's sidebar and click on the 'Purchase Tokens' button.

Choose the number of tokens you'd like to purchase and hit confirm purchase.

Once you've confirmed your billing details, complete your purchase.

You'll see your new token balance reflected shortly! (May take up to 1 minute)

**Note: Only the admin of the workspace may purchase tokens.**

## Enterprise

If you are on an enterprise account, please contact your account representative that can facilitate the purchase and add additional tokens to your account.

# Free Token Quota

Each plan has a different free token quota. This quota represents the free monthly tokens that are included with your account. These reset each month.

* Starter Plan: 100,000 Tokens
* Pro Plan: 10,000,000 Tokens
* Teams: 30,000,000 Tokens
* Enterprise: Custom

Additional tokens purchased are in addition to your monthly quota. They are a one time purchase and do not expire or reset. You will see them added to your monthly token quota as in the example below.

# FAQ

**Do I lose tokens that I purchased at the end of the month?**

No, tokens that you have purchased remain on your account forever.

**If I dont use all of my free tokens, do they roll over to the next month?**

No, the free token quota that comes with your account resets every month regardless of it you use it.

**If I'm on a free plan can I purchase more tokens**

No, you cannot purchase more tokens on a free plan. You must upgrade to a paid plan.

***

<br />

# How are tokens calculated?

A token represents a chunk of a word and is used by Large Language Models (LLMs) like GPT 4 to encode words. On average, tokens represent about three letters. It's not an easy-to-understand process, and is defined by encoding models, but if you want to play around with what token to character conversions are you can use [this OpenAI website](https://platform.openai.com/tokenizer) (token encodings will differ between providers).

<Image align="center" width="400px" src="https://files.readme.io/9c4b587-image.png" />

Voiceflow is billed by our LLM providers (OpenAI, Anthropic, Google, etc...) by the tokens at their own prices. We then apply a multiplication factor based on how much more expensive their per token rates are than the rates for the Voiceflow tokens, since no matter which model you're using, it pulls from the same Voiceflow token pool.

For example, if Model A charged us $30 per 1M tokens, and the Voiceflow token price was $2.5 per 1M tokens (this will probably change after the time of writing), then using Model A from inside Voiceflow would be charged at a 15x token multiple. So a prompt (input and output) is total 3000 characters long would be 1000 tokens, it would cost 15000 Voiceflow tokens,  which would cost $0.0375.

Tokens are used by both the input (what is being sent to the AI model) and output (what is being received from the AI model). 

It is important to note, that the "Max Token" slider on the AI steps (shown below) only control the maximum output message. Depending on your agent design, there may be a large amount of information that is sent to the AI model as a part of your prompt, so even if your max tokens are very low, you could still use thousands of tokens.

## What are token multipliers?

Depending on the LLM provider and the cost of each model, there's an associated token multiplier, which represents how “expensive” a model is to use. We're updating token multipliers regularly, so check from inside the Voiceflow platform for the most up-to-date multipliers. You can see them anywhere you can pick a model, like in the Set AI step.

<Image alt="These are the multipliers for some of the models included in Voiceflow as of March 5th, 2025. For the full list of models, look in the product. Up to date models from OpenAI, Anthropic, Google, Deepseek, and Llama are available." align="center" src="https://files.readme.io/d87f3874396a8937e42ea8b34900a01c27678bf1773f3e8088e416331a22cc83-image.png">
  These are the multipliers for some of the models included in Voiceflow as of March 5th, 2025. For the full list of models, look in the product. Up to date models from OpenAI, Anthropic, Google, Deepseek, and Llama are available.
</Image>
