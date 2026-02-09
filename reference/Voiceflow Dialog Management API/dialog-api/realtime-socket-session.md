---
title: Realtime Socket Session
excerpt: Interact with your agent using socket.io for a live two way chat.
deprecated: false
hidden: true
metadata:
  robots: index
---
### Overview

The Voiceflow WebSocket runtime uses [socket.io](https://socket.io/) to establish persistent, bidirectional connections for real-time conversational AI interactions.

Find the [socket.io client](https://github.com/socketio) in your respective development language. This documentation will use javascript, but the fundamentals remain the same.

### Connection Configuration

```javascript
import { io } from 'socket.io-client';

const socket = io('https://general-runtime.voiceflow.com', {
  path: '/v4/interact/socket',
  timeout: 10000,
  transports: ['websocket', 'polling', 'webtransport'], // optional fallbacks
  reconnection: true,
  tryAllTransports: true,
  reconnectionDelay: 1000,
  reconnectionAttempts: 5,
  reconnectionDelayMax: 5000,
});
```

### Initialization Lifecycle

1. wait for `socket.on('connect')`. This is a socket.io level connection established.
2. send `socket.emit('client.start', metadata)`. Voiceflow level metadata for client initialization.
3. wait for `socket.on('client.created')`. Voiceflow level client handshake

```
// save sessionKey on client side for future reconnections
let sessionKey: string | undefined; 

// socket.io level connection
socket.on('connect', () => { 

  // voiceflow client handshake
  socket.emit('client.start', { ...metadata, sessionKey });
  socket.once('client.started', (payload) => {
    if (payload.newSessionRequired) {
      socket.emit('session.create');	
      socket.once('session.created', (payload) => {
        sessionKey = payload.sessionKey; // ready to send actions }); 
      });
		}
  });
})
```
