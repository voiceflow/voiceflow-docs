---
title: Buttons tool
excerpt: Let users select from pre-defined choices using buttons.
deprecated: false
hidden: false
metadata:
  robots: index
---
<Image align="center" border={false} src="https://files.readme.io/7e9ce6a57212c33bbe12039979889830398dcf860290e63b9bd18873193b6ebd-Image_12.png" />

<br />

The Buttons tool lets your AI agent send up to five buttons at once, giving users a clear set of choices to click on. This is useful when you want to guide the conversation with specific options instead of relying only on free-text input. When a user clicks a button, the text on that button is sent back to the agent as if the user had typed it.

<br />

## Sending buttons from inside the Agent step

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NShTQdst7RAecUY5SiGX3h7ots6mNzP01FZfr4" />

Inside an [Agent step](doc:agents), enable the **Buttons** option on the sidebar. Then, set the **LLM description** to describe to your agent when and how it should use the Buttons tool.

We also recommend updating your agent's **Instructions** to also specify when buttons should be sent. This will dramatically increase your agent's success rate of sending buttons at the correct time.

<br />

## Manually sending buttons

You can also manually send buttons to a user using the [Button step](doc:buttons-v2).

<LinkCard type="Doc" title="Button step" description="Allow the user to choose from buttons outside the Agent step." href="./buttons-v2" />
