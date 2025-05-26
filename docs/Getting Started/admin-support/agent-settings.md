---
title: Important Agent Settings
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
# Private Mode

The Private Agent toggle determines the accessibility of your agent. By default, it is enabled, requiring an API key for external access to the agent. To make the agent accessible—via a shareable prototype link or an embeddable widget—disable this toggle.

**If this is turned on, the chat widget and shareable prototype will be disabled**

![](https://files.readme.io/06949ac489cfac01c361c4c01728c47ab22754c59761ff35e8547cc9ef9a353d-CleanShot_2024-12-11_at_13.15.042x.png)

# Language

The language setting it determined on agent create. This setting **only impacts intent recognition**. This setting is determined once you create the agent and cannot be changed once the agent has been created. 

![](https://files.readme.io/59942d2e5006683d9286585a8f2337e60ca771b8e429c889aee84c14dff5f46e-CleanShot_2024-12-11_at_13.17.182x.png)

# Global Logic

* **Message delay**: This dictates the minimum time between messages appearing on the chat widget. You can increase this to have a longer delay between sequential messages.
* **TTS**: This dictates which model will be used for Text to Speech when using the Voice capabilities within Voiceflow.
* **Global No Match**: If the agent cannot match to any intents on your canvas, this is the message that it will respond with. You can override this manually by adding the 'none' intent to the canvas. In that scenario, if the agent cannot match a message to an intent, it will match it to the 'none' intent.
* **Global No Reply**: This initiates a response if the user does not provide an input within a certain amount of time. This is utilized in Voice experiences.\*

![](https://files.readme.io/db93dc6c01d2c00352976c8b6cc3b7fac2f6eba4141c7b8d9ec910611b47046f-CleanShot_2024-12-11_at_13.19.042x.png)
