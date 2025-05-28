---
title: Send a proactive message when the user visits a certain page
description: >-
  Learn how to clear existing proactive messages and send a new one, but only on
  certain pages.
hidden: true
recipe:
  color: '#018FF4'
  icon: 🥾
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
      if (window.location.href.includes('https://example.com/category/shoes')) {
        window.voiceflow.chat.proactive.clear();
        window.voiceflow.chat.proactive.push(
          { type: 'text', payload: { message: 'Chat with me for 20% off shoes' } }
        );
      }
    });
  }
  v.src = "https://cdn.voiceflow.com/widget-next/bundle.mjs"; v.type = "text/javascript"; s.parentNode.insertBefore(v, s);
})(document, 'script');
</script>
```

```json Response Example
{"success":true}
```

# Add the default web chat widget to your page

<!-- javascript@1-11,19-23 -->

You can find this code from the Interfaces tab inside Voiceflow's editor.


# Detect when the web chat has loaded

<!-- javascript@12,19 -->

We don't want to run any actions before our web chat widget is ready to receive them.

# Detect which page the user is on

<!-- javascript@13,18 -->

We only want to run this code if the user is currently browsing the shoes category.

# Clear existing messages and send a new one

<!-- javascript@14-18 -->

If we don't clear our messages first, we might end up with a bunch!