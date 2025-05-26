---
title: Modify configurations
excerpt: >-
  This allows you to point to different versions of your web chat, different
  agents, or a different runtime if you are on a private cloud environment
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Customization and configuration

As you can see in the default snippet code available in your Web Chat agent's integration page,  we use the **chat.load()** function to load a <Glossary>agent</Glossary> by setting the **project ID**, the **runtime URL** and a **version ID**.

Below is an example of the default code snippet.

```javascript
<script type="text/javascript">
  (function(d, t) {
      var v = d.createElement(t), s = d.getElementsByTagName(t)[0];
      v.onload = function() {
        window.voiceflow.chat.load({
          verify: { projectID: 'YOUR_PROJECT_ID' },
          url: 'https://general-runtime.voiceflow.com',
          versionID: 'production'
        });
      }
      v.src = "https://cdn.voiceflow.com/widget/bundle.mjs"; v.type = "text/javascript"; s.parentNode.insertBefore(v, s);
  })(document, 'script');
</script>
```

You can add additional settings on top of the above configuration to further customize the Web Chat experience for your users.

# Pass a version ID value or alias (optional)

By default, version ID is set to ***development*** but if you use the code snippet in the Web Chat integration page, this is set to ***production***. You can also use this to force a specific agent's project ID. 

Setting version ID to ***development*** is useful when you want to test a dev version of your <Glossary>agent</Glossary> or make changes to your Voiceflow project without impacting your actual agent on production. To see any changes you make in the Creator Tool in your Web Chat widget, click the "Run" button or use the `R` keyboard shortcut in the Creator Tool, so the updates get populated.

Note: If the version ID is set to ***production*** before you publish your agent, the Web Chat widget will not render any system messages.

```javascript
/**
* [optional] the versionID of your agent, defaults to 'development'
* can be a 'development' or 'production' alias or a specific versionID
*/

versionID: "string"
```

# Pass a URL (required for Private Cloud customers)

The `url` setting is for **Enterprises** on **Private Clouds** as they need to use their dedicated runtime endpoint.

```javascript
/**
* [optional] voiceflow dialog management runtime endpoint
* defaults to https://general-runtime.voiceflow.com
*/

url: "string"
```
