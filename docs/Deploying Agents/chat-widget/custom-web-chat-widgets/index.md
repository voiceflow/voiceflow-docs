---
title: Custom forms and extensions
excerpt: Render custom widgets like file upload, date pickers, and more!
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Voiceflow's extensions feature lets you add advanced functionality to your web chat experience. Extensions allow your assistant to render custom widgets or trigger custom effects directly on your website.

<Image align="center" src="https://files.readme.io/d4bdbf6-extensions.gif" />

<br />

There are two types of extensions:

* **Response extensions**: these render interactive widgets inside the web chat window like file uploads, calendar pickers, or payment modals.
* **Effect extensions**: these don’t render a UI element but can trigger changes elsewhere on your site, such as updating a status icon, deep-linking a user, or running custom scripts.

<br />

> 📘
>
> Want to jump into code? [Find examples on GitHub](https://github.com/voiceflow-gallagan/vf-extensions-demo/tree/c7a5eda8116dc915f0b85cf9014baeefe92a22c5).

<br />

## How extensions work

Extensions are triggered by a [Custom action step](doc:custom-actions) or a [Function step](doc:function-step) in your Voiceflow assistant. You define them in your site’s code and register them in the [web chat snippet](https://docs.voiceflow.com/docs/chat-widget#how-to-add-your-agents-widget-to-your-website).

An extension follows the pattern below:

### Response Extension

```javascript
interface ResponseExtension {
	name: string,
	type: "response",
	match: (args: { trace: Trace }) => boolean,
	render?: (args: { trace: Trace, element: HTMLDivElement }) => (() => void) | void
}
```

### Effects Extension

```javascript
interface EffectExtension {
	name: string,
	type: "effect",
	match: (args: { trace: Trace }) => boolean,
	effect?: (args: { trace: Trace }) => Promise<void> | void
}
```

### Registering extensions in the web chat widget

Once you've defined your extensions, register them using the `assistant.extensions` property in your `chat.load()` script:

```javascript
window.voiceflow.chat.load({
  verify: { projectID: 'YOUR_PROJECT_ID' },
  url: 'https://general-runtime.voiceflow.com',
  versionID: 'production',
  assistant: {
    extensions: [extension1, extension2, extension3] // your extension's name goes here
  }
});
```

There’s no limit to the number of extensions you can include.

<br />

## Examples

We recommend starting with an example extension before building your own. Our simplest example is a form input extension. Find out how to build it in the doc below.

<LinkCard type="Doc" title="Building a form input extension" description="Build your first extension in just a couple of minutes." href="https://docs.voiceflow.com/docs/example-extension-form-input#/" imageSrc="https://files.readme.io/5114eba7d58c54d312d092e4236d1eadf35c5c86bac38d5b9944c08beef07aa2-Credits_2.png" />

When you're ready to start experimenting with other types of extensions, visit our sample extensions repo, which has a bunch of different examples for you to try out.

<LinkCard type="Repo" title="Sample extensions repo" description="Disable/enable the input field, embed videos and maps, accept input via a form, and trigger a confetti animation with these sample extensions." href="https://github.com/voiceflow-gallagan/vf-extensions-demo/" imageSrc="https://files.readme.io/a3380247509557ff965053f21f3769a5ff94b262b7f65e5f59051738a1d3fbd0-Agent_Step_Course.png" />