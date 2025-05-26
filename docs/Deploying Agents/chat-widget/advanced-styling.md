---
title: Custom styling
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
# Custom CSS: Override <<glossary:agent>> settings and styles

The below can be used to override the listed agent configuration settings. You can also add a link to your self-hosted stylesheet.

If you use custom CSS to style your Web Chat, target elements that begin with `.vfrc`. You can find the [list of classes in our react-chat repository on GitHub](https://github.com/voiceflow/react-chat/blob/master/packages/react-chat/src/styles.css).

```javascript
/**
* [optional] override configured agent definitions on integrations tab
*/

window.voiceflow.chat.load({
  verify: {
    projectID: "<ID>"
  },
  url: "https://general-runtime.voiceflow.com",
  versionID: "production",
  assistant: {
    type: 'chat'
    renderMode: 'embed' | 'widget' | 'popover',

    // Widget header
    header: {
      hideImage: true | false,
      imageUrl: 'https://company_domain.com/custom_image.jpg',
      title: 'My Assistant'
    },
  
    // Welcome message
    banner: {
      hide: true | false,
      title: 'Welcome',
      description: 'How can I help you today?',
      imageUrl: 'https://company_domain.com/custom_image.jpg'
    },

    // Agent avatar
    avatar: {
      hide: true | false,
      imageUrl: 'https://company_domain.com/custom_image.jpg'
    },
  
    // input
    inputPlaceholder: 'Message...'
    // color: "string",
    stylesheet: "string" //link to your self-hosted stylesheet
  }
});


```

If you don't want to host your css stylesheet, you can also convert your CSS into a data URL. Here is an example of a full widget using that method. This CSS turns the agent messages black.

```
<script type="text/javascript">
  (function(d, t) {
      var v = d.createElement(t), s = d.getElementsByTagName(t)[0];
      v.onload = function() {
        window.voiceflow.chat.load({
          verify: { projectID: 'PROJECT_ID' },
          url: 'https://general-runtime.voiceflow.com',
          versionID: 'production',
          assistant: {
            stylesheet: "data:text/css;base64,LnZmcmMtc3lzdGVtLXJlc3BvbnNlIC52ZnJjLW1lc3NhZ2UgeyBiYWNrZ3JvdW5kLWNvbG9yOiAjMDAwMDAwOyBjb2xvcjogI0ZGRkZGRjsgfQ==" // link to your self-hosted stylesheet
          }
        });
      };
      v.src = "https://cdn.voiceflow.com/widget/bundle.mjs"; 
      v.type = "text/javascript"; 
      s.parentNode.insertBefore(v, s);
  })(document, 'script');
</script>
```