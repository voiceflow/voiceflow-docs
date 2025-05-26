---
title: Web Chat (Basic)
excerpt: Get started with building your webchat Assistant.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
  pages:
    - type: basic
      slug: advanced-webchat
      title: Web Chat (Advanced)
---
With the new Web Chat integration in Voiceflow it’s now very easy to push your assistant to production. Not only this but the Chat Widget library give you access to some features / functions that you might want to implement in your custom code.

# In the Creator tool

The **Web Chat** integration page give you a code snippet you can use in your website / webapp to start sharing your assistant with users.

![](https://files.readme.io/81e1edd-Untitled.png)

Within this page, you can set general settings like chat persistence but also customize the appearance of the chat widget.

![](https://files.readme.io/f6fe044-Untitled_2.png)

![](https://files.readme.io/b41c6ef-Untitled_3.png)

# In your own code

You can go a bit further and use your own front-end code to interact with the Web Chat widget as you might also want to populate a specific user ID and/or use the available API to do the following actions:

* Load a specific project
* Set configuration settings when the Web Chat widget loads
* Open or close the Web Chat widget
* Show or hide the Web Chat widget launch bubble
* Interact with the Dialog Manager API and show the result within the Chat Widget
* Show or clear proactive text messages above your widget launch bubble

# Configuration

As you can see in the default snippet code available in your Web Chat assistant's integration page,  we use the **chat.load()** function to load a project by setting the **project ID**, the **runtime URL** and a **version ID**.

Below is an example of the default code snippet.

```javascript
window.voiceflow.chat.load({
  verify: {
    projectID: "63906a46223f6a0007741929"
  },
  url: "https://general-runtime.voiceflow.com",
  versionID: "production"
});
```

You can add additional settings on top of the above configuration to further customize the Web Chat experience for your users.

## Pass a userID (optional)

Below is an handy way to identify the user and share that info with your assistant. If you pass a `userID`, the value will be set as the built-in \{user\_id} variable in your Voiceflow project.

```javascript
/**
* [optional] userID to track users and persist/continue sessions
*/

userID: "string"
```

## Pass user info for the Transcripts view (optional)

Here you can set a name and an image that will be used in the transcripts linked to that user. Note: this will not populate any variables or entities in your assistant.

```javascript
/**
* [optional] user metadata for transcripts
*/

user: {
  name: "string",
  image: "string"
};
```

## Pass default variable values (optional)

You can pass values to the `last_event` system variable upon `load()`. Use the JavaScript Code step to validate the payload values and set variables with default val at the start of each new conversation.

Note: the `last_event` variable is set upon each new user event in the conversation (e.g. widget loaded, intent triggered, button clicked). If you want to set variables with default values, set them immediately after the Start intent in your design in the Creator tool.

```javascript
/**
* [optional] pass data to set variables with default values upon load()
*/

launch: {
  event: {
    type: "launch",
    payload: {
      // key-value pairs such as
      user_name: "Mary",
      user_email: "mary@test.com"
    }
  }
};
```

<Image align="center" src="https://files.readme.io/12eca38-Screenshot_2023-11-09_at_3.03.02_PM.png" />

## Pass a versionID value or alias (optional)

By default, versionID is set to ***development*** but if you use the code snippet in the Web Chat integration page, this is set to ***production***. You can also use this to force a specific project id. This is handy when you want to test a dev version of your assistant and/or make changes to your Voiceflow project without impacting your actual assistant on production. (Note: If the versionID is set to ***production*** before you publish your assistant, the Web Chat widget will not render any system messages.)

```javascript
/**
* [optional] the version ID of your project, defaults to 'development'
* can be a 'development' or 'production' alias or a specific versionID
*/

versionID: "string"
```

## Pass a url (required for for Private Cloud customers)

The `url` setting is for **Enterprises** on **Private Clouds** as they need to use their dedicated runtime endpoint.

```javascript
/**
* [optional] voiceflow dialog management runtime endpoint
* defaults to https://general-runtime.voiceflow.com
*/

url: "string"
```

## Override assistant settings and styles (optional)

The below can be used to override the listed assistant configuration settings. You can also add a link to your self-hosted stylesheet.

If you use custom CSS to style your Web Chat, target elements that begin with `.vfrc`. You can find the [list of classes in our react-chat repository on GitHub](https://github.com/voiceflow/react-chat/blob/master/packages/react-chat/src/styles.css).

```javascript
/**
* [optional] override configured assistant definitions on integrations tab
*/

assistant: {
  title: "string",
  description: "string",
  image: "string",
  // color: "string",
  stylesheet: "string" //link to your self-hosted stylesheet
};
```

## Example configuration

With all this in mind, you can now customize the snippet code or your front-end code to launch a specific assistant / version with the options you need.

Here is an example of the **chat.load()** call we are using in our own assistant in the Creator Tool.

```javascript
window.voiceflow.chat.load({
  verify: { projectID: `${vfa_projectID}` },
  versionID: `${vfa_version}`,
  userID: `${vfa_userID}`,
  user: {
    name: `${vfa_userName}`,
    image: "https://support.voiceflow.fr/assets/logouser.png",
  },
})
```

# Web Chat API

When the Web Chat widget script is loaded it will register an API as **window\.voiceflow\.chat** with the following methods:

## load

`load({config})` loads a specific Voiceflow assistant on a webpage. See above for the configuration options.

## open and close

`open()` opens the Web Chat widget window.

`close()` closes the Web Chat widget window.

## show and hide

`show()` renders the Web Chat launch bubble. If the Web Chat widget was previously closed using `hide()`, a subsequent `show()` will render the Web Chat widget.

`hide()` hides the Web Chat launch bubble. If the Web Chat widget is open, `hide()` will hide the Web Chat widget.

## interact

`interact({action})` sends a request to the Dialog API and updates the conversation in the widget. See the [interact endpoint documentation](https://developer.voiceflow.com/reference/stateinteract-1) for more detail about the accepted actions.

## Proactive text message bubbles

Create custom proactive text messages to draw attention to your Web Chat assistant.

`proactive.clear()` clears any previous proactive messages.

`proactive.push(...messages)` renders one or more proactive text messages:

```javascript
// one message  
window.voiceflow.chat.proactive  
  .push({ type: 'text', payload: { message: 'hello world' } })

// multiple messages  
window.voiceflow.chat.proactive  
  .push(  
    { type: 'text', payload: { message: '1!' } },  
    { type: 'text', payload: { message: '2!' } }  
  )
```

For example, you can render a proactive message bubble when your customer reaches a particular page on your website:

<Image align="center" src="https://files.readme.io/4d24d40-proactive_message_bubble_demo.png" />

```html
<script>
...
  window.voiceflow.chat.load({ ... }).then(() => {
    if (window.location.href.includes('https://store.com/products/fire_sneakers') {
      window.voiceflow.chat.proactive.clear(); // clear all previous messages
      window.voiceflow.chat.proactive.push({ 
        type: 'text', 
        payload: { message: 'Are you interested in some 🔥🔥🔥 sneakers?' }
      }, { 
        type: 'text', 
        payload: { message: 'Click on the chat to learn more!' }
      })
    }
  })
...
</script>
```

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
> **voiceflow:save\_session** - message is sent by the user
>
> **voiceflow:close** - widget is minimized or closed
