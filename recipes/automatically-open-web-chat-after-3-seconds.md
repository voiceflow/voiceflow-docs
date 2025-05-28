---
title: Automatically open web chat after 3 seconds
description: Programatically open the web chat widget on a webpage.
hidden: false
recipe:
  color: '#018FF4'
  icon: 🕒
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
        window.voiceflow.chat.open();
      }, 3000);
    });
  }
  v.src = "https://cdn.voiceflow.com/widget-next/bundle.mjs"; v.type = "text/javascript"; s.parentNode.insertBefore(v, s);
})(document, 'script');
</script>
```

# Add the default web chat widget to your page

<!-- javascript@1-11,17-20 -->

You can find this code from the Interfaces tab inside Voiceflow's editor.

# Wait three seconds then open the web chat popup

<!-- javascript@ -->

We use .then() so that widget won't try to open before its loaded.