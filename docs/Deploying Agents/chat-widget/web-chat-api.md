---
title: Custom triggers
excerpt: Programatically show, hide, and interact with the web chat widget.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Voiceflow’s web chat API gives you full programmatic control over how the chat widget behaves on your site. You can open or close the chat, show or hide the launcher, and even trigger specific conversation intents - all using JavaScript.

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSlgC6H96094EsumPty2pBL3kDrzTnQ6SWYIVN" />

<br />

## Web chat API methods

Once the widget script is loaded, it registers the API as `window.voiceflow.chat`. Here are the main methods you can use:

| Method                 | Description                                                                                                                                                                                                                                                                |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `load({ config })`     | Initializes the web chat widget with the specified config. From this config, you can enable [proactive messages](doc:proactive-messages), [pass in custom CSS](doc:advanced-styling), [use a specific agent version with the widget](doc:custom-configurations), and more. |
| `open()`               | Opens the chat window.                                                                                                                                                                                                                                                     |
| `close()`              | Closes the chat window.                                                                                                                                                                                                                                                    |
| `show()`               | Displays the chat launcher bubble. If hidden, calling this will show it again.                                                                                                                                                                                             |
| `hide()`               | Hides the chat launcher and the widget if it's open.                                                                                                                                                                                                                       |
| `interact({ action })` | Sends a simulated user action to the Dialog API. Can be used to trigger specific intents or events. See the [interact endpoint documentation](https://developer.voiceflow.com/reference/stateinteract-1) for details.                                                      |

<br />

### Examples

<TutorialTile emoji="🦉" slug="automatically-open-web-chat-after-3-seconds" title="Automatically open web chat after 3 seconds" />

<TutorialTile emoji="🦉" slug="trigger-an-intent-after-opening-the-web-chat-widget" title="Trigger an intent after opening the web chat widget" />

<br />

## Events

The Web Chat widget can also emit events that you can listen to using the message event listener.

```javascript
window.addEventListener('message', (event) => {
  console.log(event);
}, false);
```

Note: If the event is triggered by Voiceflow, it will be a stringified JSON object with a type beginning in `voiceflow:`. Useful events include:

| Event type               | Description                                                   |
| ------------------------ | ------------------------------------------------------------- |
| `voiceflow:open`         | The widget was opened                                         |
| `voiceflow:close`        | The widget was minimized or closed                            |
| `voiceflow:interact`     | The assistant responded to an interaction                     |
| `voiceflow:save_session` | A save event occurred to cache the current conversation state |