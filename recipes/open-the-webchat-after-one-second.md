---
title: Open the webchat after one second
description: A simple example of hooking into the webchat widget and performing an action
hidden: false
recipe:
  color: '#018FF4'
  icon: 💬
---
```javascript JavaScript
window.voiceflow.chat.load({
  verify: {
    projectID: "YOUR_PROJECT_ID_HERE"
  },
  url: "https://general-runtime.voiceflow.com",
  versionID: "production"
}).then(() => {
  setTimeout(function () {
    window.voiceflow.chat.open();
  }, 1000)
});
```

```json Response Example
{"success":true}
```

# Load the widget

<!-- javascript@1-7 -->

The default webchat code will load the chat widget.

# Set the timeout

<!-- javascript@7-11 -->

Our custom code will automatically open the chat widget after one second.