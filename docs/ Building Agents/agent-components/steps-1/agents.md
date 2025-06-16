---
title: Agent step
excerpt: >-
  Handle user input, search the knowledge base, call tools, and follow paths —
  all in one step
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<Image align="center" src="https://files.readme.io/96eec3b6b1ff9caa0bd5f670d8bfe0fa144af6b3fab6328228fd0851346ed182-Image_11.png" />

The Agent step is a flexible all-in-one tool that lets your assistant interpret user input using AI, access your knowledge base, route the conversation based on intent, and run external functions — all within a single step.

Use it when you want the agent to handle an open-ended request without needing to manually define each path ahead of time.

<br />

<Embed url="https://www.google.com/sorry/index?continue=https://www.youtube.com/watch%3Fv%3DwkN04Nr7KSs%26feature%3Dyoutu.be&q=EhAmAB8YEA2fMapQNsg0Abi8GJ6C7L4GIjCBRmY8MAlUO6LKCM_7TzAyZE7E6JtV-ytVuh10NQkUt-9TRNkWivXPK6iMbWgpu00yAnJSWgFD" href="https://www.google.com/sorry/index?continue=https://www.youtube.com/watch%3Fv%3DwkN04Nr7KSs%26feature%3Dyoutu.be&q=EhAmAB8YEA2fMapQNsg0Abi8GJ6C7L4GIjCBRmY8MAlUO6LKCM_7TzAyZE7E6JtV-ytVuh10NQkUt-9TRNkWivXPK6iMbWgpu00yAnJSWgFD" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Furl%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DwkN04Nr7KSs%26type%3Dtext%252Fhtml%26schema%3Dgoogle%26display_name%3DYouTube%26src%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FwkN04Nr7KSs%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## Introduction to the Agent step

The Agent step provides a comprehensive solution for creating AI agents that can:

* Intelligently respond to user queries
* Search knowledge base for relevant information
* Follow specific conversation paths based on user intent
* Execute functions to interact with external services

**To add an Agent step to your canvas:**

1. Look for the "Agent" option in the top left corner of the Voiceflow canvas
2. Drag this step onto your canvas
3. Choose an existing agent, create a new agent or search for community-created agents

![](https://files.readme.io/adfaf1c2820e8e63a106e7e83877947ab5fe9f56bb23f28e14385453b67fdd62-CleanShot_2025-03-19_at_13.42.312x.png)

## Prompting Your Agent

Effective prompting is the foundation of a successful agent. The instructions you provide serve as the agent's "brain" and determine how it will interact with users:

* **Clear Directives**: Be specific about your agent's role and how it should respond in different scenarios
* **Personality Design**: Define your agent's tone, level of formality, and communication style
* **Knowledge Parameters**: Indicate what domain knowledge your agent should rely on and when it should search external resources
* **Context Awareness**: Include instructions for handling sensitive topics or escalating to human support when necessary

> 📘
>
> Learn more about crafting great prompts [here](https://docs.voiceflow.com/docs/crafting-great-prompts)

Good prompting helps your agent understand what information to prioritize, when to use the knowledge base, and how to respond to user queries in a consistent manner. Taking time to craft detailed, thoughtful instructions will dramatically improve your agent's performance and reduce the need for additional steps in your flow.

For example, instead of simply saying "This is a support agent," you might specify: "You are a friendly e-commerce support agent that helps customers with order tracking, returns, and account issues. Maintain a positive tone, offer proactive suggestions, and provide specific details when available."

## Functions

Functions allow your agent to connect with external services and retrieve or update data. Based on the UI screenshot, configuring a function in an Agent Step involves several important components:

### Function Configuration:

1. **Select Function**: Choose from available functions in the dropdown menu
2. **LLM Description**: This is critical - you need to tell the LLM when and how to use this function

![](https://files.readme.io/2709b2956ffdad0d4b4d20cb460c494e892616aa91c9dc7687d61fb40129e3b1-CleanShot_2025-03-19_at_14.26.162x.png)

### Function Description:

The `LLM Description` field is where you provide detailed instructions that help the LLM understand:

* When to call this function
* What the function does
* What information is needed to use it

For example, for an order lookup function:

> **LLM Description**: "Use this function to retrieve a customer's order details from Shopify when they ask about their order status, delivery date, shipping address, or tracking information. This function requires a valid order ID to proceed. Only call this function when the customer explicitly mentions needing information about a specific order they've placed."

### Input Variable Configuration:

For each input variable your function requires:

1. **Variable Name**: Set a clear, descriptive name (shown as "orderID" in the UI example)
2. **Variable Description**: Explain what this variable represents and how to collect it
3. **Default Value**: Optionally provide a default value

### Variable Description:

The description for each input variable helps the LLM understand:

* What information to collect
* How to validate it
* When to request it from the user

For example, for an Order ID variable:

**LLM Variable Description**: "This variable should contain the customer's order ID. Valid order IDs are 10-digit numbers that start with 'ORD-'. If the customer doesn't provide their order ID initially, ask them for it. If they don't know their order ID, ask if they have a confirmation email where they can find it."

**Default Value**: You can optionally set a default value, but for user-specific information like order IDs, this field is typically left empty.

### Function Examples:

#### Order Lookup Function

> **Function Name**: Get Order by ID\
> **LLM Description**: "Use this function to retrieve a customer's order details from Shopify when they ask about their order status, delivery date, shipping address, or tracking information. The function requires a valid order ID to proceed."
>
> **Input Variable Name**: orderID\
> **LLM Variable Description**: "The customer's order ID. This should be a 10-digit number that starts with 'ORD-'. Ask the customer to provide this number if they haven't already."

#### Inventory Check Function

> **Function Name**: Check Product Availability\
> **LLM Description**: "Use this function when a customer asks if a product is in stock, available in a specific size or color, or when it might be back in stock. This function requires a product ID or SKU number to check availability."
>
> **Input Variable Name**: productSKU\
> **LLM Variable Description**: "The SKU or product ID of the item the customer is inquiring about. Valid SKUs are alphanumeric codes that typically start with 'P-' followed by numbers. If the customer mentions a product name but not the SKU, ask them for more specific information about which product they're interested in."

## Paths

Paths allow your agent to handle specific conversation flows and take appropriate actions:

* **Automatic Routing**: The agent detects user intent and automatically routes to the appropriate path
* **Variable Collection**: You can require specific data to be collected before entering a path
* **Seamless Integration**: Paths work within natural conversation, without requiring specific commands

**To create a path:**

1. Open your Agent step editor
2. Add a new path with a descriptive name
3. Define a description that explains when this path should be triggered
4. Optionally add required variables that must be collected
5. Connect the path to subsequent steps in your flow

![](https://files.readme.io/428bab7644952d89f2e2db6835e628de0df20a1f67e54c51807293368b5b3ffb-CleanShot_2025-03-19_at_14.10.082x.png)

### Path Examples:

#### Order Return Path

> **Path Name**: Process Order Return\
> **LLM Description**: "Trigger this path when the user wants to return an item they purchased, expresses dissatisfaction with their order, mentions that an item is defective, or asks about the return policy. The user might use phrases like 'I want to return', 'how do I send this back', 'my product is broken', or 'does this have a warranty'."
>
> **Required Variable**: orderID\
> **LLM Variable Description**: "This variable should contain the order ID that the customer wants to return. Valid order IDs are 10-digit numbers. If the user doesn't provide their order ID initially, ask them for it. Make sure to verify that the provided ID matches the expected format before proceeding with the return pr

This description helps the LLM understand exactly when to trigger the return process. It includes both direct mentions of returns and indirect signals of return intent, providing a comprehensive set of triggers for the path. The variable description ensures the agent knows how to collect and validate the required information before proceeding.

#### Promo Code Path

> **Path Name**: Get a Promo Code\
> **Description**: "Trigger this path when the user asks for a promo code or a discount, or says things are too expensive. Look for phrases like 'do you have any discounts', 'that's too much money', 'any coupon codes', or 'how can I save on my order'."
>
> **Required Variable**: email\
> **Variable Description**: "The user's email address where we'll send promotional materials. Only accept inputs that follow a valid email format (contains @ symbol and appropriate domain extension). If the user is hesitant, explain that we need their email to deliver the promo code and track usage. Do not proceed with providing the discount code until a valid email is collected."

This description helps the LLM recognize when a user is seeking a discount, either directly or indirectly. The required variable description provides clear guidance on what constitutes a valid email address and how to handle user hesitation, ensuring you collect quality customer data before providing them with the promotional code.

## Knowledge Base

When you enable knowledge base integration, your agent can automatically search for information it doesn't know:

* **Automatic Queries**: Your agent will search the knowledge base without requiring a separate search step
* **Contextual Responses**: The agent intelligently combines its built-in knowledge with information from your knowledge base
* **Knowledge Weighting**: You can adjust how much the agent relies on its built-in knowledge versus your knowledge base through the instructions

For example, if a user asks about a password reset but that information isn't in your knowledge base, the agent can provide general guidance. But when asked about email confirmation—which is in your knowledge base—it can provide specific, accurate information from your documentation.

The UI shows a toggle for "Access to knowledge base" which you can enable to give your agent the ability to search your knowledge base when needed, with option to update LLM description for more custom prompting.

![](https://files.readme.io/d276421e36f6c24fa1c355d2a375c3cda69059a4d0df59e6512385310f671ee5-CleanShot_2025-03-19_at_14.06.322x.png)

## Advanced Usage

For even more powerful implementations:

* **Multiple Agent steps**: Chain several Agent steps together for complex workflows
* **Custom Functions**: Develop your own functions to connect with any service your business uses
* **Prompt Refinement**: Continuously refine your agent's instructions based on conversation logs and user feedback