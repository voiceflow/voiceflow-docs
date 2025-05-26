---
title: Proactive messages
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


For example, you can render a proactive message bubble when your customer reaches a particular page on your website:

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