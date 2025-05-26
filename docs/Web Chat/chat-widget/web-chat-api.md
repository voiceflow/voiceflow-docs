---
title: Custom Triggers
excerpt: >-
  Using the Web Chat API you can do actions like open, close, show, hide and
  much more with the Web Chat programatically.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The Web Chat API allows you to open, close and do much more with the Webchat. This also allows you to trigger the Web Chat to start from a specific intent on your canvas.

# Web Chat API

When the Web Chat widget script is loaded it will register an API as **window.voiceflow.chat** with the following methods:

## load

`load({config})` loads a specific Voiceflow agent on a webpage. See above for the configuration options.

## open and close

`open()` opens the Web Chat widget window.

`close()` closes the Web Chat widget window.

## show and hide

`show()` renders the Web Chat launch bubble. If the Web Chat widget was previously closed using `hide()`, a subsequent `show()` will render the Web Chat widget.

`hide()` hides the Web Chat launch bubble. If the Web Chat widget is open, `hide()` will hide the Web Chat widget.

## interact

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

# Events

Once loaded, the Web Chat widget also send messages (events) you can monitor to trigger a specific action in your front-end code.

```javascript
window.addEventListener('message', (event) => {
  console.log(event);
}, false);
```

Note: the event.data value is a JSON string if it contains a `voiceflow:*` event type (e.g. `data: '{"type":"voiceflow:open"}'`).

`event.data` type `voiceflow:*` values that may be useful include:

> **voiceflow:open** - widget is opened
>
> **voiceflow:save_session** - a save event is triggered to cache the conversation state/history
>
> **voiceflow:interact** - the user sent an action and got a response from the server
>
> **voiceflow:close** - widget is minimized or closed