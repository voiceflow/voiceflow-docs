---
title: Send multiple proactive messages
description: >-
  Send messages before a user opens the web chat widget, without incurring
  credit fees.
hidden: false
recipe:
  color: '#018FF4'
  icon: 💬
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
      window.voiceflow.chat.proactive.push(  
        { type: 'text', payload: { message: 'Hey, we sell lots of hats!' } },  
        { type: 'text', payload: { message: 'Want recommendations?' } }  
      )
    });
  }
  v.src = "https://cdn.voiceflow.com/widget-next/bundle.mjs"; v.type = "text/javascript"; s.parentNode.insertBefore(v, s);
})(document, 'script');
</script>
```

# Add the default web chat widget to your page

<!-- javascript@1-11,17-21 -->

You can find this code from the Interfaces tab inside Voiceflow's editor.

# Add a hook to send proactive messages

<!-- javascript@12-17 -->

By using .then(), we trigger the messages once the widget is loaded.