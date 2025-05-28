---
title: Chat persistence
excerpt: Choose how conversations are stored.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
When using Voiceflow’s webchat, you control chat persistence (how conversations are remembered) directly within the JavaScript snippet - not through the Voiceflow UI. This allows for more flexibility based on how you want your users' conversations to persist across sessions and browser tabs.

## What is chat persistence?

Chat persistence determines whether users will return to an ongoing conversation or start fresh when they reload a page, open a new tab, or come back later. You can choose between different persistence strategies to match your desired user experience.

## How to configure persistence

To set your preferred persistence behavior, add the persistence property inside the assistant object in your webchat snippet:

```
window.voiceflow.chat.load({  
  verify: { projectID: 'your-project-id' },
  url: 'your-runtime-url',
  versionID: 'production',
  assistant: {
    persistence: 'localStorage' // Set your preferred persistence option here
  }
});
```

Voiceflow supports three persistence options: `localStorage`, `sessionStorage`, and `memory`.

| Option             | Behavior                                                                                                       |
| ------------------ | -------------------------------------------------------------------------------------------------------------- |
| `'localStorage'`   | **Default.** Conversations persist across page reloads and browser sessions. Useful for returning users.       |
| `'sessionStorage'` | Conversations persist across page reloads within a single browser session, but reset when all tabs are closed. |
| `'memory'`         | Conversations reset on every page reload or new tab. Best for ephemeral or private sessions.                   |