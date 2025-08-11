---
title: Agent step
excerpt: >-
  Handle user input, search the knowledge base, call tools, and follow exit
  conditions — all in one step
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

## Basic usage

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

## Prompting Your Agent

Effective prompting is the foundation of a successful agent. The instructions you provide serve as the agent's "brain" and determine how it will interact with users:

* **Clear Directives**: Be specific about your agent's role and how it should respond in different scenarios
* **Personality Design**: Define your agent's tone, level of formality, and communication style
* **Knowledge Parameters**: Indicate what domain knowledge your agent should rely on and when it should search external resources
* **Context Awareness**: Include instructions for handling sensitive topics or escalating to human support when necessary

> 👍 Create an effective prompt.
>
> Learn more about crafting great prompts [here](https://docs.voiceflow.com/docs/crafting-great-prompts)

Good prompting helps your agent understand what information to prioritize, when to use the knowledge base, and how to respond to user queries in a consistent manner. Taking time to craft detailed, thoughtful instructions will dramatically improve your agent's performance and reduce the need for additional steps in your flow.

For example, instead of simply saying "This is a support agent," you might specify: "You are a friendly e-commerce support agent that helps customers with order tracking, returns, and account issues. Maintain a positive tone, offer proactive suggestions, and provide specific details when available."

## <Anchor label="Integrations" target="_blank" href="https://docs.voiceflow.com/docs/integrations#/">Integrations</Anchor>

Integrations are native connections to popular third-party platforms. These require minimal setup and expose helpful, opinionated actions specific to each tool.

### Supported Integrations & Common Use Cases:

| Integration   | Use case                                                    |
| :------------ | :---------------------------------------------------------- |
| Zendesk       | Look up or create support tickets, fetch user info.         |
| Shopify       | Get contact, lead, or opportunity data, update CRM records. |
| Google Sheets | Check orders, fetch product details, initiate returns.      |
| Gmail         | Send transactional or templated emails.                     |
| Airtable      | Query tables, update or add records, track interactions.    |
| Make.com      | Trigger custom workflows, connect to 1000+ apps.            |
| Twilio        | Send SMS or make calls with custom logic.                   |
| Hubspot       | Create or update CRM contacts, log conversation outcomes.   |

![](https://files.readme.io/1ba143caec56c024d2dc331bedc2e4aee95dca847705d6213b80d9943fddefb2-CleanShot_2025-07-29_at_14.44.212x.png)

## Functions

Functions allow your agent to connect with external services and retrieve or update data. Based on the UI screenshot, configuring a function in an Agent Step involves several important components:

### Function Configuration:

1. **Select Function**: Choose from available functions in the dropdown menu
2. **LLM Description**: This is critical - you need to tell the LLM when and how to use this function

![](https://files.readme.io/24eac212512d887b57d7475185ec621172dad9ffc4ab27ddac69d91c71397a73-CleanShot_2025-07-29_at_15.12.312x.png)

### LLM Description:

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

> #### Order Lookup Function (Example)
>
> **Function Name**: Get Order by ID\
> **LLM Description**: "Use this function to retrieve a customer's order details from Shopify when they ask about their order status, delivery date, shipping address, or tracking information. The function requires a valid order ID to proceed."
>
> **Input Variable Name**: orderID\
> **LLM Variable Description**: "The customer's order ID. This should be a 10-digit number that starts with 'ORD-'. Ask the customer to provide this number if they haven't already."

## Exit conditions

Exit conditions allow your agent to handle specific conversation flows and take appropriate actions:

* **Automatic Routing**: The agent detects user intent and automatically routes to the appropriate path
* **Variable Collection**: You can require specific data to be collected before entering a path
* **Seamless Integration**: Paths work within natural conversation, without requiring specific commands

<Video src="https://w17llroiln.ufs.sh/f/JH4JLc5mceYks8l3KfGlT9yobAZqe36tMHzS78D0muRx2fLJ" />

### Exit condition examples:

> **Exit condition name**: Process Order Return\
> **Description**: "Trigger this path when the user wants to return an item they purchased, expresses dissatisfaction with their order, mentions that an item is defective, or asks about the return policy. The user might use phrases like 'I want to return', 'how do I send this back', 'my product is broken', or 'does this have a warranty'."
>
> **Required Variable**: orderID\
> **LLM Variable Description**: "This variable should contain the order ID that the customer wants to return. Valid order IDs are 10-digit numbers. If the user doesn't provide their order ID initially, ask them for it. Make sure to verify that the provided ID matches the expected format before proceeding with the return pr

## Knowledge Base

When you enable knowledge base integration, your agent can automatically search for information it doesn't know:

* **Automatic Queries**: Your agent will search the knowledge base without requiring a separate search step
* **Contextual Responses**: The agent intelligently combines its built-in knowledge with information from your knowledge base
* **Knowledge Weighting**: You can adjust how much the agent relies on its built-in knowledge versus your knowledge base through the instructions

For example, if a user asks about a password reset but that information isn't in your knowledge base, the agent can provide general guidance. But when asked about email confirmation—which is in your knowledge base—it can provide specific, accurate information from your documentation.

![](https://files.readme.io/690a1fde9e1a9df1786ef65aa0fd4862b4d6ecbe6793df7d2d3646d323bb0749-CleanShot_2025-07-29_at_15.26.252x.png)

> 📘 Ensure knowledge base is toggled on!
>
> Your agent can only have access to your knowledge base if the tool is toggled on the agent step.

## Agent-generated components

The Agent step in Voiceflow allows agents to **dynamically** generate components in real time during a conversation. These components- **Buttons, Cards, and Carousel**- can be toggled on to let the agent include them in its replies. Once enabled, the agent will reference your prompt to determine how and when to use them.

<Callout icon="👀" theme="default">
  **Important**: These components will only be generated if you explicitly instruct the agent to use them in the prompt. The more specific you are, the better. **Only chat interface agents** using the Agent step can dynamically generate these components.
</Callout>

<Callout icon="🚧">
  *For best results* with agent-generated components, we advise you use the latest **Anthropic models**(e.g. Claude 4, Claude 4 Opus, Claude 3.7 Sonnet). Through rigorous testing, OpenAI models have performed poorly with agent-generated components.
</Callout>

\<Tabs>
&#x20; \<Tab title="Buttons">
&#x20;   \<h3>Button step\</h3>

&#x20;   Buttons allow your agent to offer \*\*clickable response options\*\* to the user. When a user clicks a button, it's treated as if they typed the button label as a message—triggering the next appropriate step in the flow.

&#x20;   \*\*Use case\*\*: Great for quick selections, confirming decisions, or giving a few directions without overloading the user with text.

&#x20;   \*\*Example prompt:\*\*

&#x20;   \`\`\`
&#x20;   Offer the user three clear options after they describe their issue. Display buttons labeled "Speak to support", "Check order status", and "Return a product". When the user clicks one, treat it as if they typed it, and respond accordingly with follow-up questions or solutions based on their selection.
&#x20;   \`\`\`

&#x20;   !\[]\(https\://files.readme.io/cea9cb4921ad883e8ec018bdf0bed2ec92ef988d99c3f759106d95efbace173c-CleanShot\_2025-08-05\_at\_14.24.382x.png)
&#x20; \</Tab>

&#x20; \<Tab title="Cards">
&#x20;   \<h3>Card step\</h3>

&#x20;   Cards are useful for showcasing \*\*visual content along with links\*\*. Each card can include a title, description, image, and link. They are especially helpful when referencing external resources, product listings, or support documents.

&#x20;   \<Callout icon="👀" theme="default">
&#x20;     \### Cards provide redirect urls.

&#x20;     Cards should \*\*only\*\* be used if you're embedding the assistant in a web environment—links will open in a new tab.
&#x20;   \</Callout>

&#x20;   \*\*Use case\*\*: Best used for surfacing relevant articles, support pages, or featured products with click-throughs.

&#x20;   \*\*Example prompt:\*\*

&#x20;   \`\`\`
&#x20;   If the user mentions needing help with setup, provide a card titled "Device Setup Guide" with a short description and a link to https\://example.com/setup. Include a relevant image. If they mention troubleshooting, show a card for "Troubleshooting Hub" with a link to https\://example.com/troubleshoot.
&#x20;   \`\`\`


<br />

## Advanced Usage

For even more powerful implementations:

* **Multiple Agent steps**: Chain several Agent steps together for complex workflows
* **Custom Functions**: Develop your own functions to connect with any service your business uses
* **Prompt Refinement**: Continuously refine your agent's instructions based on conversation logs and user feedback