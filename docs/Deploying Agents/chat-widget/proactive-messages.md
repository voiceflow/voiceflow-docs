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

<TutorialTile emoji="🦉" slug="send-multiple-proactive-messages" title="Send multiple proactive messages" />

<br />

## Clearing messages

You can use the `window.voiceflow.chat.proactive.clear()` method to hide all the proactive messages that have been sent to a user.

<br />

## Triggering proactive messages when certain things happen

One great use-case for proactive messages is to trigger them when the user does a specific action. For example, you could offer a promo code if the user navigates away from the checkout page, or suggest product recommendations if the user is clicking on lots of similar products.

Here's an example of clearing existing messages and showing a new one if the user visits a certain page.

<TutorialTile emoji="🦉" slug="send-a-proactive-message-when-the-user-visits-a-certain-page" title="Send a proactive message when the user visits a certain page" />