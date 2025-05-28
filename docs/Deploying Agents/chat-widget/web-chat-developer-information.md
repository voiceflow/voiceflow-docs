---
title: Web chat developer information
deprecated: false
hidden: false
metadata:
  robots: index
---
## Supported HTML elements (in the text step)

All the tags below are supported when used in the text step on Web Chat.

```
['a','audio','b','blockquote','br','code','dd','del','details','div','dl','dt','em','h1','h2','h3','h4','h5','h6','hr','i','img','input','ins','kbd','li','ol','p','picture','pre','q','rp','rt','ruby','s','samp','section','source','span','strike','strong','sub','summary','sup','table','tbody','td','tfoot','th','thead','tr','tt','ul','var','video']
```

**Note:** By default, dangerous HTML elements such as Iframe require additional configuration.

### Enabling dangerous HTML elements

**Disclaimer:** Enabling dangerous HTML elements enables cross-site scripting vulnerabilities (XSS). This means that if you are using someone else's code, it may provide them full access to your private information. Do this at your own risk and **only use your own code**. You can read more on XSS vulnerabilities and how to prevent them [here](https://security.snyk.io/vuln/SNYK-PYTHON-MARKDOWNEDITOR-559226).

To enable dangerous HTML elements such as Iframe's, set the following configuration to true on your Web Chat installation code. By default, this value is false.

```
window.voiceflow.chat.load({
  ...
  allowDangerousHTML: true
});
```

# In your own code

You can go a bit further and use your own front-end code to interact with the Webchat widget as you might also want to populate a specific user ID and/or use the available API to do the following actions:

* Load a specific <Glossary>agent</Glossary>
* Set configuration settings when the Webchat widget loads
* Open or close the Webchat widget
* Show or hide the Webchat widget launch bubble
* Interact with the Dialog Manager API and show the result within the Chat Widget
* Show or clear proactive text messages above your widget launch bubble