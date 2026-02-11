---
title: Websocket Client Session
excerpt: Interact with your agent using socket.io for a live two way chat.
deprecated: false
hidden: true
metadata:
  robots: index
---
<Callout icon="🚧" theme="warn">
  The `/v4/interact/socket` endpoint is still in beta and potentially subject to minor changes.
</Callout>

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

<Callout icon="📘" theme="info">
  A session is not the same as the socket.io connection. You can disconnect/reconnect multiple times and still continue the same conversation session.
</Callout>

For more information on socket.io lifecycle management, reference [documentation](https://socket.io/docs/v4/client-api/).

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

### Action Lifecycle

Once the session is ready, you can now send actions to the agent and get responses back.

1. send new action with `action.send`, i.e. `{ type: 'text', payload: 'hello' }`
2. get back a status `action.status` either `status: 'accepted' | 'rejected'`
3. if `status: accepted`:
   1. get back agent responses with `action.trace`, display to user
   2. get `action.status` with `status: 'completed'`

This represents the back and forth conversation with the agent.

<Callout icon="📘" theme="info">
  Try to not send a new action while an existing action is running. While this is supported, it can make it harder to debug user state and lead to certain race conditions.

  Instead wait for `status: 'completed'` or `status: 'rejected'` after sending an action.
</Callout>

### Conversation Lifecycle

#### Start

To start the conversation from the beginning, your first action should be:

```typescript
socket.emit('action.send', {
  action: { type: 'launch', payload: {} }
});
```

It is also possible to launch from specific points in the conversation with [events](https://docs.voiceflow.com/docs/introduction-to-events):

```typescript
socket.emit('action.send', {
  action: { type: 'event', payload: { event: { name: 'event_name' } } }
});
```

#### End

The session ending also signals that the conversation has ended. This can also occur because of timeouts.

```typescript
socket.on('session.ended', () => {
  // cleanup code
})
```

# Client events

## `client.start`

Initial Voiceflow metadata and configuration to validate and set up the client. This is aways the first message that the client should send to the server after socket.io successfully connects. Server will respond with `client.started`.

### Payload

`?:` denotes optional properties.

```typescript
interface ClientStartPayload {
  userID: string; // primary user identifier
  projectID: string; // voiceflow projectID

  // (versionID) environment to use, [default: "development"]
  environmentID?: string;

  // session to reconnect to, ignore if new session
  sessionKey?: string | null;

  // voiceflow project API Key (under settings), do not set for public facing clients
  authorization?: string;

  config?: {
    // break up LLM responses into live chunks [default: false]
    completionEvents: boolean;

    // timezone in IANA (tz database) for the vf_user_timezone variable
    userTimezone?: string;

    audioEvents: boolean; // enable TTS audio chunk responses
    audioEncoding?: 'audio/x-mulaw' | 'audio/pcm'; // audio response format
  };
}
```

### Example Call

```typescript
socket.emit('client.start', {
  userID: 'test@test.com',
  projectID: '6939bedf69c7ce5ee7a108ed',

  environmentID: 'production',
  authorization: 'VF.DM...',

  config: {
    completionEvents: true
  };
});
```

<br />

## `session.create`

Creates a new session for the user. Should be sent after `client.started` indicates `newSessionRequired: true`. Server will respond with `session.created`.

#### Example Call

```typescript
socket.emit('session.create', {});
```

<br />

## `action.send`

Sends a user action to the server. A valid session must already exist. Server will respond with `action.status` and `action.trace` events.

[See possible action types in the `action` body of interaction requests.](https://docs.voiceflow.com/reference/stateinteract-1#body-params).

### Payload

```typescript
interface ActionSendPayload {
  action: {
    // request type: "text" | "intent" | "launch" | "event" | "action" | etc.
    type: string;
    
    // action-specific payload
    payload?: string | object;
  };
}
```

#### Example Call

```typescript
socket.emit('action.send', {
  action: {
    type: 'text',
    payload: 'Hello, how are you?'
  }
});
```

<br />

<br />

# Server events

## `client.started`

Server ack to `client.start`,  informs if a new session needs to be created

### Payload

```typescript
interface ClientStartedPayload {
  newSessionRequired: boolean
}
```

#### Example

```typescript
socket.on('client.started', (payload: ClientStartedPayload) => {
  if (payload.newSessionRequired) {
    socket.emit('session.create', {});
  } else {
    // session is now ready for interactions
	}
});
```

<br />

## `session.created`

Confirms that a new session has been created. Client should store the `sessionKey` for future reconnections.

### Payload

```typescript
interface SessionCreatedPayload {
  sessionKey: string; // JWT session key to store and use for reconnections
}
```

#### Example

```typescript
socket.on('session.created', (payload: SessionCreatedPayload) => {
  localStorage.setItem('sessionKey', payload.sessionKey);
  // session is now ready for interactions
});
```

<br />

## `session.ended`

Indicates that the conversation session has ended. Client should close the session and optionally display a workflow to create a new one.

### Payload

```typescript
interface SessionEndedPayload {
  // reason for session ending (e.g., "end_of_diagram", "inactivity_timeout", etc.)
  reason: string;
}
```

<br />

## `action.trace`

Represents agent responses and debugging information for an action. [See possible trace types](https://docs.voiceflow.com/reference/trace-types).

### Payload

```typescript
type ActionTracePayload = {
  // trace object containing agent response data (speak, text, audio, etc.)
  trace: Trace;
  
  // message identifier matching the action.send messageID
  messageID: string;
}
```

#### Example

```typescript
socket.on('action.trace', (payload: ActionTracePayload) => {
  // Handle trace data (speech, text, audio chunks, etc.)
  console.log('Trace received:', payload.trace);
});
```

<br />

## `action.status`

Indicates the status of an action that was sent via `action.send`. This event is sent when an action is accepted, rejected, or completed.

#### Payload

```typescript
interface ActionStatusPayload {
  status: 'accepted' | 'rejected' | 'completed'; // action status
  messageID: string; // message identifier matching the action.send messageID
  reason?: string; // optional reason for rejection or completion
}
```

<br />

## `server.restart`

Server is gracefully shutting down and informing the client to reconnect to a different server instance.

### Payload

```typescript
interface ServerRestartPayload {
  action?: {
    type: string;
    payload?: string | object;
    diagramID?: string;
    time?: number;
  }; // optional action to replay after reconnection
}
```

<br />

## `error`

General error message from the server. May occur at any point during the connection.

### Payload

```typescript
interface ErrorPayload {
  code?: string; // optional error code
  error: string; // error message
}
```
