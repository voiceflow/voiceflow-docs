---
title: Allowing dangerous HTML elements
excerpt: >-
  Our default settings keep you safe. You can opt-out, but we don't recommend
  it.
deprecated: false
hidden: false
metadata:
  robots: index
---
By default, the following HTML elements can be used by the message step when interfacing with the web chat widget:

```
['a','audio','b','blockquote','br','code','dd','del','details','div','dl','dt','em','h1','h2','h3','h4','h5','h6','hr','i','img','input','ins','kbd','li','ol','p','picture','pre','q','rp','rt','ruby','s','samp','section','source','span','strike','strong','sub','summary','sup','table','tbody','td','tfoot','th','thead','tr','tt','ul','var','video']
```

<br />

Certain elements, such as `<script>` and `<iframe>` tags are blocked by default. You can optionally enable them, however, **you do so at your own risk**.

## Enabling dangerous HTML elements

> ❗️ You should only allow dangerous HTML elements if you understand the implications.
>
> Enabling dangerous HTML elements enables cross-site scripting vulnerabilities (XSS). This means that if you are using someone else's code, it may provide them full access to your private information. Do this at your own risk and **only use your own code**. You can read more on XSS vulnerabilities and how to prevent them [here](https://security.snyk.io/vuln/SNYK-PYTHON-MARKDOWNEDITOR-559226).
>
> **If you are not a developer and do not understand what an XSS vulnerability is, do not enable dangerous HTML elements**.

<br />

To enable dangerous HTML elements such as `<iframe>`, set the following configuration to true on your web chat installation code. By default, this value is false.

```
window.voiceflow.chat.load({
  ...
  allowDangerousHTML: true
});
```