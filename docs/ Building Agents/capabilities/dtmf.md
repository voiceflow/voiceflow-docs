---
title: Keypad input (DTMF)
excerpt: Let your phone agents listen to keypad inputs in real time.
deprecated: false
hidden: true
metadata:
  robots: index
---
<Callout icon="ℹ️" theme="info">
  This feature is only available for Voiceflow’s [phone integration](doc:telephony) and isn’t supported by the [Web chat widget](doc:chat-widget).
</Callout>

<br />

Voiceflow’s DTMF capability allows your agent to automatically detect and respond to keypad inputs during phone calls. For example, if a caller types `676767` on their phone, the agent can interpret that input and use it to drive the conversation flow - like entering an account number, selecting a menu option, or confirming a passcode - all without leaving the call. DTMF is great for handling fiddly numeric inputs during conversations.

<br />

## Setting up keypad input

To use keypad input, it must first be enabled on your project. To enable it, open your project's settings, click **Behaviour**, then open the **Voice** tab. Then, scroll down and set **Keypad input** to **On**. 

**VIDEO**

From here, you can also set the following settings:

* **Timeout** - the number of seconds to wait between the user stopping typing and the input to be sent to your agent. Voiceflow will automatically send multiple numbers entered in quick succession as single message to your agent, allowing things like order numbers and PIN codes to be handled easily.
* **Delimiter** - you can optionally set the pound (`#`) and star (`*`) keys as send buttons. If enabled, when a delimiter key is pressed, the user's keypad input will be immediately sent to the agent.

<br />

Once keypad input is setup, any [Agent step](doc:agents) with **Listen for other triggers** enabled will be able to receive keypad inputs.   

<Image align="center" border={false} src="https://files.readme.io/41893a91f2407cb89d8b2a04402d16eb27b9b01c20eb7a00120a527407d29ff0-Frame_48095788.png" />
