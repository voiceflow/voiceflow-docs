---
title: End step
excerpt: Finish your agent's conversation with a user.
deprecated: false
hidden: false
metadata:
  robots: index
---
<Image align="center" src="https://files.readme.io/1bb4dd44c6fd25d45e3f6932a75bf4247299612528d7638a2e8ac20540969157-Image_5.png" />

The End step allows your agent to finish a conversation. In the real world, this means hanging up if using Voiceflow's [Voice (phone number)](doc:telephony) integration, or ending a chat session if using our [web chat widget](doc:chat-widget).

<br />

## Basic usage

To use the End step, drag it onto the canvas and connect it to the point where you want the conversation to stop. The End step does not have any settings.

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NS5HT0yhkJkKd0Il9TFbCLjpMzB2tW61uiXDRU" />

Please note that any steps placed after the End step will not be executed or shown to the user.