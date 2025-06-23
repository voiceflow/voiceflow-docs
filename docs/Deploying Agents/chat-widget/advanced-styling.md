---
title: Custom web chat styling
excerpt: Customize the web chat widget to fully fit your brand.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
For most use cases, the built-in widget customization options are more than enough. But if you're an advanced user looking for more visual control, you can customize the widget’s appearance with your own CSS.

<br />

## Styling methods

There are two primary ways to style the web chat widget:

1. Use the built-in configuration fields (e.g. header image, colors, input placeholder)
2. Override the widget’s CSS using your own stylesheet (either hosted or embedded)

<br />

## Method 1: Built-in styling options

Voiceflow lets you control the widget’s appearance directly in your `chat.load()` configuration using the assistant object. Here’s an example with optional styling parameters:

```javascript
window.voiceflow.chat.load({
  verify: { projectID: '<your-project-id>' },
  url: 'https://general-runtime.voiceflow.com',
  versionID: 'production',
  assistant: {
    type: 'chat',
    renderMode: 'widget', // also accepts 'embed' or 'popover'

    header: {
      hideImage: false,
      imageUrl: 'https://yourdomain.com/logo.png',
      title: 'Chat with Support'
    },

    banner: {
      hide: false,
      title: 'Welcome!',
      description: 'How can I help you today?',
      imageUrl: 'https://yourdomain.com/banner.jpg'
    },

    avatar: {
      hide: false,
      imageUrl: 'https://yourdomain.com/avatar.png'
    },

    inputPlaceholder: 'Type your message here...',
    
    // Optional external stylesheet
    stylesheet: 'https://yourdomain.com/styles.css'
  }
});
```

<br />

## Method 2: Custom CSS styling

To go beyond basic styling, you can use your own CSS rules to override the default widget styles.

<br />

### How to target web chat elements

Voiceflow's web chat elements use class names prefixed with `.vfrc`. To customize these, create CSS rules targeting those classes.

\<Accordion title="View the full list of supported classes" icon="fa-code">
&#x20; \`\`\`\\\*
&#x20; PAGE CONTENTS

&#x20; Customize the page that the chat bubble lives on
&#x20; \\\*/

&#x20; /\\\* .voiceflow-chat \{} \\\*/

&#x20; /\\\* .vfrc-launcher \{} \\\*/

&#x20; /\\\* .vfrc-chat--overlay \{} \\\*/

&#x20; /\\\* .vfrc-prompt \{} \\\*/

&#x20; /\\\*
&#x20; CHAT WIDGET HEADER

&#x20; Customize the content, controls and styling included in your chat widget header, including the Assistant Information.
&#x20; Note that changes to the assistant information here will be shared across other elements that consume this styling.
&#x20; \\\*/

&#x20; /\\\* .vfrc-header \{} \\\*/

&#x20; /\\\* .vfrc-assistant-info \{} \\\*/

&#x20; /\\\* .vfrc-assistant-info--title \{} \\\*/

&#x20; /\\\* .vfrc-assistant-info--description \{} \\\*/

&#x20; /\\\* .vfrc-avatar \{} \\\*/

&#x20; /\\\* .vfrc-icon \{} \\\*/

&#x20; /\\\*
&#x20; CHAT MESSAGE BODY

&#x20; Customize the layout and display of the chat body, and the conversation's metadata
&#x20; \\\*/

&#x20; /\\\* .vfrc-chat \{} \\\*/

&#x20; /\\\* .vfrc-chat--dialog \{} \\\*/

&#x20; /\\\* .vfrc-chat--spacer \{} \\\*/

&#x20; /\\\* .vfrc-chat--session-time \{} \\\*/

&#x20; /\\\* .vfrc-chat--status \{} \\\*/

&#x20; /\\\* .vfrc-message \{} \\\*/

&#x20; /\\\* .vfrc-timestamp \{} \\\*/

&#x20; /\\\*
&#x20; ASSISTANT RESPONSES

&#x20; Customize the style and layout of assistant response messages.
&#x20; \\\*/

&#x20; /\\\* .vfrc-system-response--indicator \{} \\\*/

&#x20; /\\\* .vfrc-system-response \{} \\\*/

&#x20; /\\\* .vfrc-system-response--controls \{} \\\*/

&#x20; /\\\* .vfrc-system-response--list \{} \\\*/

&#x20; /\\\* .vfrc-system-response--actions \{} \\\*/

&#x20; /\\\* .vfrc-button \{} \\\*/

&#x20; /\\\* .vfrc-image \{} \\\*/

&#x20; /\\\* .vfrc-image--background \{} \\\*/

&#x20; /\\\* .vfrc-card--content \{} \\\*/

&#x20; /\\\* .vfrc-card--header \{} \\\*/

&#x20; /\\\* .vfrc-card--description \{} \\\*/

&#x20; /\\\* .vfrc-carousel \{} \\\*/

&#x20; /\\\* .vfrc-carousel--button \{} \\\*/

&#x20; /\\\* Targeted styling for just the Assistant messages. \*/
&#x20; /\* .vfrc-system-response .vfrc-message \{} \\\*/

&#x20; /\\\* Targeted styling for just the Assistant buttons. \*/
&#x20; /\* .vfrc-system-response .vfrc-button \{} \\\*/

&#x20; /\\\*
&#x20; USER RESPONSES

&#x20; Customize the style and layout of users response messages.
&#x20; \\\*/

&#x20; /\\\* .vfrc-user-response \{} \\\*/

&#x20; /\\\* Targeted styling for just the User messages \*/
&#x20; /\* .vfrc-user-response .vfrc-message \{} \\\*/

&#x20; /\\\*
&#x20; FOOTER

&#x20; Customize the layout and appearance of the message input field and the VF Branding
&#x20; \\\*/

&#x20; /\\\* .vf-footer \{} \\\*/

&#x20; /\\\* .vfrc-input \{} \\\*/

&#x20; /\\\* .vfrc-chat-input--button \{} \\\*/

&#x20; /\\\* .vfrc-footer--watermark \{} \\\*/\`\`\`
\</Accordion>

<br />

For example, you could change the background of agent messages like this:

```javascript
.vfrc-system-response .vfrc-message {
  background-color: #000000;
  color: #FFFFFF;
}
```

Once you've written your CSS, there's two ways to pass it into your widget.

<br />

### Option A: Link a self-hosted stylesheet

You can host your CSS file and provide the link in the `assistant.stylesheet` property:

```javascript
assistant: {
  stylesheet: 'https://yourdomain.com/custom-styles.css'
}
```

<br />

### Option B: Embed CSS via data URL

If you don’t want to host a CSS file externally, you can encode your CSS as a base64 data URL and include it inline:

```javascript
<script type="text/javascript">
  (function(d, t) {
    var v = d.createElement(t), s = d.getElementsByTagName(t)[0];
    v.onload = function() {
      window.voiceflow.chat.load({
        verify: { projectID: 'PROJECT_ID' },
        url: 'https://general-runtime.voiceflow.com',
        versionID: 'production',
        assistant: {
          stylesheet: 'data:text/css;base64,LnZmcmMtc3lzdGVtLXJlc3BvbnNlIC52ZnJjLW1lc3NhZ2UgeyBiYWNrZ3JvdW5kLWNvbG9yOiAjMDAwMDAwOyBjb2xvcjogI0ZGRkZGRjsgfQ==' // the base64-encoded data URL containing your stylesheet
        }
      });
    };
    v.src = 'https://cdn.voiceflow.com/widget/bundle.mjs';
    v.type = 'text/javascript';
    s.parentNode.insertBefore(v, s);
  })(document, 'script');
</script>

```