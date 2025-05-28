---
title: Web chat widget
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
The quickest way to launch your agent is using our web chat widget. Web chat can be deployed to production in minutes, and is ideal for customer support or lead capture. Web chat supports three different interfaces: widget, popover, and embedded.

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSm0VVMS3vgzMhu7msD2nISacpBK5UHfikJy9X" />

<Image align="center" src="https://files.readme.io/f4966820cb32bd854c7a29b3d35283288039843a79cf8ec0bfac8a3912ec82cf-Frame_48095750_1.png" />

<br />

## How to add your agent's widget to your website

Before you can add your agent to your website, you'll need to [publish a production version of it](doc:publishing-agents). Once your agent is published, head over to interfaces section of your agent's settings, select widget, then copy-paste the code into your website's codebase. If you're not a developer and aren't sure where to add this code, we recommend asking ChatGPT "*How can I add custom JavaScript to a \[your website platform here] website?*".

![](https://files.readme.io/23dc2430f1efa289c8cb2de3b694c932b907f2e72143322b075b60918cb7f433-CleanShot_2025-05-27_at_21.23.212x.png)

<br />

## Customizing your widget

Your agent should fit your brand, so we provide a variety of customization options. From the widget settings page, scroll down and you'll be able to set your agent's brand colours, icons, launcher type, and the interface you'd like to use. You can also optionally add placeholder and privacy policy links.

<Image align="center" src="https://files.readme.io/dafdecf7bb148515422a3217daee20e2c298ca1ac6f90f56d3adc0bc4fa1452d-Frame_48095751.png" />

Paid users can also disable Voiceflow branding from this page.

<br />

## Setting your widget's security settings

Three security settings are available at the bottom of the widget settings page. These are:

* **Approved domains** - if you'd like to restrict your widget so it only works on specified websites, you can manage the whitelist here.
* **Legal disclaimer** - certain company policies or local regulations may require a legal disclaimer to be shown and accepted before the agent is used. This can be enabled and customized using this setting.
* **Chat transcript saving** - if disabled, conversations with the agent via the chat widget won't be saved as a [transcript](doc:transcripts). This can be useful when sensitive information is being processed.

<br />

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