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

## Examples

<TutorialTile emoji="🦉" slug="automatically-open-web-chat-after-3-seconds" title="Automatically open web chat after 3 seconds" />

<TutorialTile emoji="🦉" slug="trigger-an-intent-after-opening-the-web-chat-widget" title="Trigger an intent after opening the web chat widget" />

<br />

# Events

Once loaded, the Web Chat widget also send messages (events) you can monitor to trigger a specific action in your front-end code.

```javascript
window.addEventListener('message', (event) => {
  console.log(event);
}, false);
```

Note: the `event.data` value is a JSON string if it contains a `voiceflow:*` event type (e.g. `data: '{"type":"voiceflow:open"}'`).

`event.data` type `voiceflow:*` values that may be useful include:

> **voiceflow:open** - widget is opened
>
> **voiceflow:save\_session** - a save event is triggered to cache the conversation state/history
>
> **voiceflow:interact** - the user sent an action and got a response from the server
>
> **voiceflow:close** - widget is minimized or closed