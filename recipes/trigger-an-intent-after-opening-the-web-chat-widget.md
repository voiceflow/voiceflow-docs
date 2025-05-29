---
title: 'Web chat: trigger an intent after opening the web chat widget'
description: This example waits for 2 seconds, then automatically triggers an intent.
hidden: false
recipe:
  color: '#018FF4'
  icon: 🪄
---
```javascript JavaScript
<script type="text/javascript">
  (function(d, t) {
  var v = d.createElement(t), s = d.getElementsByTagName(t)[0];
  v.onload = function() {
    window.voiceflow.chat.load({
      verify: { projectID: 'YOUR_PROJECT_ID_HERE' },
      url: 'https://general-runtime.voiceflow.com',
      versionID: 'production',
      voice: {
        url: "https://runtime-api.voiceflow.com"
      }
    }).then(() => {
      setTimeout(() => {
        window.voiceflow.chat.interact({
          type: 'intent',
          payload: {
            intent: { name: 'account_services' },
            entities: []
          }
        });
      }, 2000);
    });
  }
  v.src = "https://cdn.voiceflow.com/widget-next/bundle.mjs"; v.type = "text/javascript"; s.parentNode.insertBefore(v, s);
})(document, 'script');
</script>
```

# Add the default web chat widget to your page

<!-- javascript@1-11,23-26 -->

You can find this code from the Interfaces tab inside Voiceflow's editor.

# Automatically send an interact event

<!-- javascript@12-22 -->

This interact event will be triggered after 2 seconds, and will trigger the "account_services" intent.