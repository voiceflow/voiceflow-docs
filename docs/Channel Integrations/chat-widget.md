---
title: Chat Widget
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
With the new Web Chat integration in Voiceflow it’s now very easy to push your assistant to production. Not only this but the Chat Widget library give you access to some features / functions that you might want to implement in your custom code.

## In the Creator tool

The **Web Chat** integration page give you a code snippet you can use in your website / webapp to start sharing your assistant with users.

![](https://files.readme.io/81e1edd-Untitled.png)

Within this page, you can set general settings like chat persistence but also customize the appearance of the chat widget.

![](https://files.readme.io/f6fe044-Untitled_2.png)

![](https://files.readme.io/b41c6ef-Untitled_3.png)

## In your own code

You can go a bit further and use your own front-end code to interact with the Chat Widget as you might also want to populate a specific user ID and/or use the available APIs to do the following actions:

* Load a specific project
* Set configuration settings
* Open the Chat Widget
* Close the Chat Widget
* Hide the Chat Widget bubble
* Show the Chat Widget bubble
* Interact with the Dialog Manager API and show the result within the Chat Widget

### Configuration

The configuration is what you will need to load you assistant in the Chat Widget and set some options.

As you can see in the default snippet code available in the Web Chat integration page,  we use the **chat.load()** function to load a project by setting the **project ID**, the **runtime URL** and a **version ID**.

Here is an example of the default code snippet but you can add more info on top of this.

```jsx
window.voiceflow.chat.load({
	verify: { 
		projectID: "63906a46223f6a0007741929"
	},
	url: "https://general-runtime.voiceflow.com",
	versionID: "production"
});
```

```jsx
/**
* [optional] userID to track users and persist/continue sessions
*/

userID: "string"
```

This is an handy way to identify the user and share that info with your assistant as the built-in \{user\_id} variable in your Voiceflow project with be populated with that value.

```jsx
/**
* [optional] user metadata for transcripts
*/

user: {
    name: "string",
    image: "string"
};
```

Here you can set a name and an image that will be used in the transcripts linked to that user.

```jsx
/**
* [optional] the version ID of your project, defaults to 'development'
* can be a 'development' or 'production' alias or a specific versionID
*/

versionID: "string"
```

By default, versionID is set to ***development*** but if you use the code snippet in the Web Chat integration page, this is set to ***production*** instead. You can also use this to force a specific project id. This become handy when you want to test a dev version of your assistant and/or make changes to your Voiceflow project without impacting your actual assistant on prod.

```jsx
/**
* [optional] voiceflow dialog management runtime endpoint
* defaults to https://general-runtime.voiceflow.com
*/

url: "string"
```

This setting is for **Enterprises** on **Private Clouds** as they need to use their dedicated runtime endpoint.

```jsx
/**
* [optional] override configured assistant definitions on integrations tab
*/

assistant: {
	title: "string",
  description: "string",
  image: "string",
  color: "string"
};
```

This last one is to override the actual assistant configuration.

Will all this in mind, you can now customize the snippet code or your front-end code to launch a specific assistant / version with the options you need.

Here is an example of the **chat.load()** call we are using in our own assistant on Creator.

```jsx
window.voiceflow.chat.load({
	verify: { projectID: `${vfa_projectID}` },
	versionID: `${vfa_version}`,
	userID: `${vfa_userID}`,
	user: {
		name: `${vfa_userName}`,
		image: "https://support.voiceflow.fr/assets/logouser.png",
	},
})
```

### APIs

Whenever the Chat Widget script is loaded it will register an API as **window\.voiceflow\.chat** with the following functions:

```jsx
load({config})
open()
close()
show()
hide()
interact({action})
```

> **load()** is what we’ve seen previously
>
> **open()** and **close()** allow you to **open** or **close** the widget window
>
> **show()** and **hide()** allow you to show or hide the chat bubble (*and the widget window if opened*)
>
> **interact()** allow you to call the DM API interact endpoint to send a request and update the actual conversation in the widget. See doc here: [https://developer.voiceflow.com/reference/stateinteract-1](https://developer.voiceflow.com/reference/stateinteract-1)

Example calls:

```jsx
window.voiceflow.chat.load({
	verify: { projectID: "63906a46223f6a0007741929" },
	url: "https://general-runtime.voiceflow.com",
	versionID: "production"
});
```

```jsx
window.voiceflow.chat.open();
```

```jsx
window.voiceflow.chat.interact({
	type: "text",
	payload: "Can I order a large pepperoni pizza"
})
```

### Events

The Chat Widget also send messages (events) you can monitor to trigger a specific action in your front-end code.

The ones you might be interested in are:

**voiceflow:open**

**voiceflow:close**
