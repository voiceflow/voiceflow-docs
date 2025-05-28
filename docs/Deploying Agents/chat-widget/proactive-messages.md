---
title: Proactive messages
excerpt: Send messages to the user before they start chatting.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Proactive messages allow you to send messages to the user before they open the chat widget. These messages do not appear in transcripts, and do not consume credits. You can add and remove proactive messages to your web chat widget using the `window.voiceflow.chat.proactive` method.

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSnzvO3ayLLDzbg1qhkwJW5SmtN92ciaEe8MjI" />

<br />

## Sending proactive messages

To send a proactive message to the user, use the `window.voiceflow.chat.proactive.push()` method. You can send one or more messages to the user at the same time.

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

<br />

<br />

Create custom proactive text messages to draw attention to your Web Chat agent.

`proactive.clear()` clears any previous proactive messages.

`proactive.push(...messages)` renders one or more proactive text messages:

<Image align="center" src="https://files.readme.io/4d24d40-proactive_message_bubble_demo.png" />

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