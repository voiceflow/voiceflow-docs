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

| Method                 | Description                                                                                                                                                                                                           |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `load({ config })`     | Initializes the Web Chat widget with the specified config. Required to get the widget running.                                                                                                                        |
| `open()`               | Opens the chat window.                                                                                                                                                                                                |
| `close()`              | Closes the chat window.                                                                                                                                                                                               |
| `show()`               | Displays the chat launcher bubble. If hidden, calling this will show it again.                                                                                                                                        |
| `hide()`               | Hides the chat launcher and the widget if it's open.                                                                                                                                                                  |
| `interact({ action })` | Sends a simulated user action to the Dialog API. Can be used to trigger specific intents or events. See the [interact endpoint documentation](https://developer.voiceflow.com/reference/stateinteract-1) for details. |

<br />

<br />

# Web Chat API

When the Web Chat widget script is loaded, it will register an API as **window\.voiceflow\.chat** with the following methods:

## Load

`load({config})` loads a specific Voiceflow agent on a webpage. See above for the configuration options.

## Open and close

`open()` opens the Web Chat widget window.

`close()` closes the Web Chat widget window.

## Show and hide

`show()` renders the Web Chat launch bubble. If the Web Chat widget was previously closed using `hide()`, a subsequent `show()` will render the Web Chat widget.

`hide()` hides the Web Chat launch bubble. If the Web Chat widget is open, `hide()` will hide the Web Chat widget.

## Interact

`interact({action})` sends a request to the Dialog API and updates the conversation in the widget. See the [interact endpoint documentation](https://developer.voiceflow.com/reference/stateinteract-1) for more detail about the accepted actions.

## Additional example calls

Open the Web Chat widget with after 1s

```javascript
window.voiceflow.chat.load({
  verify: { projectID: "63906a46223f6a0007741929" },
  url: "https://general-runtime.voiceflow.com",
  versionID: "production"
}).then(() => {
  setTimeout(function () {
    window.voiceflow.chat.open();
  }, 1000)
});
```

Open the Web Chat widget and trigger a specific intent

```javascript
window.voiceflow.chat.load({
  verify: { projectID: '63906a46223f6a0007741929' },
  url: 'https://general-runtime.voiceflow.com',
  versionID: 'production'
}).then(() => {
  setTimeout(function () {
    window.voiceflow.chat.open();
  }, 1000);
  setTimeout(function () {
    window.voiceflow.chat.interact({
      type: "intent",
      payload: {
        intent: {
          name: "account_services"
        },
        entities: []
      }
    })
  }, 2000);
});
```

You can insert these custom triggers into the body of the webchat widget.

```javascript
<script type="text/javascript">
  (function(d, t) {
      var v = d.createElement(t), s = d.getElementsByTagName(t)[0];
      v.onload = function() {
        window.voiceflow.chat.load({
          [THEY GO HERE!!]     <---------------------------------------------
        });
      }
      v.src = "https://cdn.voiceflow.com/widget/bundle.mjs"; v.type = "text/javascript"; s.parentNode.insertBefore(v, s);
  })(document, 'script');
</script>
```

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