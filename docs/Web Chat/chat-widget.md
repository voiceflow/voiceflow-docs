---
title: Web Chat
excerpt: >-
  Implement your Voiceflow Web Chat agent using our install code and JavaScript
  API.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: basic
      slug: customization-configuration
      title: Adding Custom Variables
    - type: basic
      slug: embed-customize-styling
      title: Embed & Customize Styling
    - type: basic
      slug: render-custom-widgets-effects
      title: Custom Widgets & Effects (beta)
    - type: basic
      slug: custom-configurations
      title: Modify Configurations
    - type: basic
      slug: web-chat-api
      title: Custom Triggers
---
With the Web Chat integration in Voiceflow it’s easy to implement and push your <<glossary:agent>> to production. Our Web Chat widget and JavaScript API allows you to customize the appearance UI elements, specify between development and production versions of your design, pass data upon launch, programmatically show and hide the widget, and more.

# Installation Code

The **Web Chat** integration page in the Creator Tool provides code snippet you can use in your website / web app to start sharing your <<glossary:agent>> with users.

![](https://files.readme.io/81e1edd-Untitled.png)

Within this page, you can set general settings like chat persistence but also customize the appearance of the chat widget.

![](https://files.readme.io/f6fe044-Untitled_2.png)

![](https://files.readme.io/b41c6ef-Untitled_3.png)

## Supported HTML elements (in the text step)

All of the below tags are supported when used in the text step on Web Chat. 

```
['a','audio','b','blockquote','br','code','dd','del','details','div','dl','dt','em','h1','h2','h3','h4','h5','h6','hr','i','img','input','ins','kbd','li','ol','p','picture','pre','q','rp','rt','ruby','s','samp','section','source','span','strike','strong','sub','summary','sup','table','tbody','td','tfoot','th','thead','tr','tt','ul','var','video']
```

**Note: ** By default, dangerous HTML elements such as Iframe require additional configuration.

### Enabling dangerous HTML elements

**Disclaimer:** Enabling dangerous HTML elements enables cross-site scripting vulnerabilities (XSS). This means that if you are using someone else's code, it may provide them full access to your private information. Do this at your own risk and **only use your own code**. You can read more on XSS vulnerabilities and how to prevent them [here](https://security.snyk.io/vuln/SNYK-PYTHON-MARKDOWNEDITOR-559226).

To enable dangerous HTML elements such as Iframe's, set the following configuration to true on your Web Chat installation code. By default this value is false.

```
window.voiceflow.chat.load({
  ...
  allowDangerousHTML: true
});
```

# In your own code

You can go a bit further and use your own front-end code to interact with the Web Chat widget as you might also want to populate a specific user ID and/or use the available API to do the following actions:

- Load a specific <<glossary:agent>>
- Set configuration settings when the Web Chat widget loads
- Open or close the Web Chat widget
- Show or hide the Web Chat widget launch bubble
- Interact with the Dialog Manager API and show the result within the Chat Widget
- Show or clear proactive text messages above your widget launch bubble