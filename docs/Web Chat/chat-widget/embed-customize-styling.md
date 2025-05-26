---
title: Embed & Customize Styling
excerpt: Modify the CSS of your web chat and embed it within a page
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Customization & Configuration

As you can see in the default snippet code available in your Web Chat agent's integration page,  we use the **chat.load()** function to load a <<glossary:agent>> by setting the **project ID**, the **runtime URL** and a **version ID**.

Below is an example of the default code snippet.

```javascript
window.voiceflow.chat.load({
  verify: {
    projectID: "<ID>"
  },
  url: "https://general-runtime.voiceflow.com",
  versionID: "production"
});
```

You can add additional settings on top of the above configuration to further customize the Web Chat experience for your users.



# Embed the Webchat in a Page

To embed the Webchat within a section of your page rather than the default overlay mode, you can add the following to the webchat installation code.

**Important:**You must indicate the HTML element ID that the embedded webchat should attach too. If you do not specify an element, it will look for and attach to any element with the ID `voiceflow-chat-frame`. If no element with that ID is found, then the widget will revert back into the default overlay mode.

- `render.mode` can be set to `overlay` or `embedded`. When in `overlay` mode, chat will ignore any target passed. Otherwise, the chat will mount into the target via Shadow DOM treating target element as a host.
- `render.target` should be a valid `HTMLElement` which will be the host element of the chat (aka the chat tree will be mounted into the target treating it as a container. If no target was provided, the chat will try to find a valid HTML element with `voiceflow-chat-frame id` to attach itself to it.
- `autostart`: defaults to `true` in `render.mode: 'embedded'` and to `false` in `render.mode: 'bubble'.` Unless the session has been previously started and can be retrieved from your storage of choice, a new session will not be started if `autostart: false`.

```javascript
/**
* [optional] Embed webchat within a section of your page
*/

render: {
	mode: 'embedded',
	target: document.getElementById('flat-chat'),
},
autostart: false,
```

Known Issue: when you refresh the page, if `autostart:false` the session will be still active.

**Example**

```javascript
/**
* [optional] Embed webchat within a section of your page
*/


window.voiceflow.chat.load({
  verify: {
    projectID: "<ID>"
  },
  url: "https://general-runtime.voiceflow.com",
  versionID: "production",
  render: {
		mode: 'embedded',
		target: document.getElementById('flat-chat'),
	},
	autostart: false
});
```



# Custom CSS: Override <<glossary:agent>> settings and styles

The below can be used to override the listed agent configuration settings. You can also add a link to your self-hosted stylesheet.

If you use custom CSS to style your Web Chat, target elements that begin with `.vfrc`. You can find the [list of classes in our react-chat repository on GitHub](https://github.com/voiceflow/react-chat/blob/master/packages/react-chat/src/styles.css).

```javascript
/**
* [optional] override configured agent definitions on integrations tab
*/

assistant: {
  title: "string",
  description: "string",
  image: "string",
  // color: "string",
  stylesheet: "string" //link to your self-hosted stylesheet
}
```

**Example**

```javascript
/**
* [optional] override configured agent definitions on integrations tab
*/

window.voiceflow.chat.load({
  verify: {
    projectID: "<ID>"
  },
  url: "https://general-runtime.voiceflow.com",
  versionID: "production",
	assistant: {
  	title: "string",
  	description: "string",
  	image: "string",
  	// color: "string",
  	stylesheet: "string" //link to your self-hosted stylesheet
	}
});


```



# Proactive text message bubbles

Create custom proactive text messages to draw attention to your Web Chat agent.

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

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4d24d40-proactive_message_bubble_demo.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


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