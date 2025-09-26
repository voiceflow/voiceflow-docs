---
title: Carousels tool
excerpt: Send multiple visual cards to the user at once.
deprecated: false
hidden: false
metadata:
  robots: index
---
<Image align="center" border={false} src="https://files.readme.io/b457530f3ffc2759341045ae7e056ab0b165d36aec9a7b709869cba0543505d3-Image_14.png" />

<br />

The Carousels tool lets your AI agent present several cards together in a scrollable format. Each card can include a title, image, description, and optional buttons. Carousels are useful when you want to showcase multiple products, options, or pieces of information side by side, giving users an easy way to browse and choose.

Many users pull information about products using an [Integration](doc:integrations), then visually display it using a carousel. The agent step is capable of automatically transforming JSON responses from integration tools into a carousel automatically, provided it is well-prompted and has enough information to work off.

<br />

## Sending carousels from inside the Agent step

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NS0dLObqY2PgpkOf8RGh2YzjZUvq461wulWrJQ" />

Inside an [Agent step](doc:agents), enable the **Carousels** option on the sidebar. Then, set the **LLM description** to describe to your agent when and how it should use the Carousels tool.

We also recommend updating your agent's **Instructions** to also specify when a carousel should be sent. This will dramatically increase your agent's success rate of sending carousels at the correct time.

<br />

## Manually sending carousels

You can also manually send buttons to a user using the [Carousels step](doc:cards-carousels).

<LinkCard type="Doc" title="Card step" description="Manually send carousels from outside the Agent step." href="./cards-carousels" />
