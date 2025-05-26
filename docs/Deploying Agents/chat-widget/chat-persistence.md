---
title: Chat persistence
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
In webchat, chat persistence is configured directly in the snippet rather than through the UI. This gives you more control and flexibility over conversation persistence across sessions and browser tabs.

To configure persistence, add the `persistence` property to your assistant configuration:

```javascript
window.voiceflow.chat.load({
  verify: { projectID: 'your-project-id' },
  url: 'your-runtime-url',
  versionID: 'production',
  assistant: {
    persistence: 'localStorage' // Configure persistence here
  }
});
```

Available persistence options:

* `'localStorage'` (default): Conversations persist across page refreshes and browser sessions
* `'sessionStorage'`: Conversations persist across page refreshes but reset when all tabs are closed
* `'memory'`: Conversations reset on each page refresh or new tab
