---
title: Buttons tool
excerpt: Let users select from pre-defined choices using buttons.
deprecated: false
hidden: false
metadata:
  robots: index
---
<Image align="center" border={false} src="https://files.readme.io/c24f64adc5d751560e618f86c13a1792b92ac9f1ef85fc08a9f1bae471fb88e1-Image_10.png" />

<br />

The Buttons tool lets your AI agent send up to five buttons at once, giving users a clear set of choices to click on. This is useful when you want to guide the conversation with specific options instead of relying only on free-text input. When a user clicks a button, the text on that button is sent back to the agent as if the user had typed it.

<br />

## Sending buttons from inside the Agent step

Inside an [Agent step](doc:agents), enable the **Buttons** option on the sidebar. Then, set the **LLM description** to describe to your agent when and how it should use the Buttons tool.

We also recommend updating your agent's **Instructions** to also specify when buttons should be sent. This will dramatically increase your agent's success rate of sending buttons at the correct time.

<br />

## Manually sending buttons

You can also manually send buttons to a user using the [Button step](doc:buttons-v2).

<LinkCard type="Doc" title="Button step" description="Allow the user to choose from buttons outside the Agent step." href="./buttons-v2" />