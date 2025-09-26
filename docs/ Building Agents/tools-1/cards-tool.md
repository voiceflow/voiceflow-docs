---
title: Cards tool
excerpt: Visually display information on cards.
deprecated: false
hidden: true
metadata:
  robots: index
---
<Image align="center" border={false} src="https://files.readme.io/0cde7195d292887a86adf8d4dbef5cb0e3b44ccf920e00567c19f8dc8bc7a836-Image_11.png" />

<br />

The Cards tool lets your AI agent present information in a card format with a title, image, description, and optional buttons. Cards are helpful when you want to highlight products, services, or key details in a more structured and visual way, rather than only sending plain text.

Many users pull information about products using an [Integration](doc:integrations), then visually display it using cards. The agent step is capable of automatically transforming JSON responses from integration tools into cards automatically, provided it is well-prompted and has enough information to work off.

## Sending cards from inside the Agent step

Inside an [Agent step](doc:agents), enable the **Cards** option on the sidebar. Then, set the **LLM description** to describe to your agent when and how it should use the Cards tool.

We also recommend updating your agent's **Instructions** to also specify when cards should be sent. This will dramatically increase your agent's success rate of sending cards at the correct time.

<br />

## Manually sending cards

You can also manually send buttons to a user using the [Card step](doc:cards-carousels).

<LinkCard type="Doc" title="Card step" description="Manually send cards from outside the Agent step." href="./cards-carousels" />
