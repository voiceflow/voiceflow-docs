---
title: Realtime Socket Session
excerpt: Interact with your agent using socket.io for a live two way chat.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

The Voiceflow WebSocket runtime uses [socket.io](https://socket.io/) to establish persistent, bidirectional connections for real-time conversational AI interactions.

Find the [socket.io client](https://github.com/socketio) in your respective development language. This documentation will use javascript, but the fundamentals remain the same.

### Connection configuration

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

# Lifecycle

### Initialization sequence

1. Wait for `connect`. This is a socket.io level connection established.
2. Send `client.start`. Send voiceflow project metadata/config + optional `sessionKey`.
3. Wait for `client.started`. Client handshake, confirms configuration.
4. If `client.started` specifies `newSessionRequired`:
   1. Send `session.create`.
   2. Wait for `session.created`. Save returned `sessionKey` for future use.
5. Agent is now ready for interactions

```typescript
// save sessionKey on client side for future reconnections
let sessionKey: string | undefined; 

// socket.io level connection
socket.on('connect', () => { 

  // voiceflow client handshake
  socket.emit('client.start', { sessionKey, ...metadata });
  socket.once('client.started', (payload: { newSessionRequired: boolean }) => {
    if (payload.newSessionRequired === false) {
			return ready();
    }
    
		// session create handshake
    socket.emit('session.create', {});	
    socket.once('session.created', (payload: { sessionKey: string }) => {
      sessionKey = payload.sessionKey;
      ready();
    });
  });
})
```

<br />

# Client events

# Server events

<br />
