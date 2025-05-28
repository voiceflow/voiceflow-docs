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
# Overview

Voiceflow's extensions feature lets you add advanced functionality to your web chat experience. Extensions allow your assistant to render custom widgets or trigger custom effects directly on your website.

There are two types of extensions:

* **Response extensions**: these render interactive widgets inside the web chat window like file uploads, calendar pickers, or payment modals.
* **Effect extensions**: these don’t render a UI element but can trigger changes elsewhere on your site, such as updating a status icon, deep-linking a user, or running custom scripts.

> 📘
>
> Want to jump into code? [Find examples on GitHub](https://github.com/voiceflow-gallagan/vf-extensions-demo/tree/c7a5eda8116dc915f0b85cf9014baeefe92a22c5).

<br />

<Image align="center" border={false} caption="Here's an example of two extensions in action - the form is a response extension, and the confetti is an effect extension." src="https://files.readme.io/d4bdbf6-extensions.gif" />

## How extensions work

Extensions are triggered by a [Custom action step](doc:custom-actions) or a [Function step](doc:function-step) in your Voiceflow assistant. You define them in your site’s code and register them in the [web chat snippet](https://docs.voiceflow.com/docs/chat-widget#how-to-add-your-agents-widget-to-your-website).

> 📘 Find the examples repo [here](https://github.com/voiceflow-gallagan/vf-extensions-demo/tree/c7a5eda8116dc915f0b85cf9014baeefe92a22c5)

<Embed url="https://www.youtube.com/watch?v=xY0vNkzFzAI" href="https://www.youtube.com/watch?v=xY0vNkzFzAI" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FxY0vNkzFzAI%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DxY0vNkzFzAI%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FxY0vNkzFzAI%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

Extensions allows you to use the **custom action step** or a **function** in your Voiceflow design to trigger a piece of custom code (the extension) in the code of your website. An example of a form is shown below.

An extension follows the pattern below

**Response Extension**

```
interface ResponseExtension {
	name: string,
	type: "response",
	match: (args: { trace: Trace }) => boolean,
	render?: (args: { trace: Trace, element: HTMLDivElement }) => (() => void) | void
}
```

**Effects Extension**

```
interface EffectExtension {
	name: string,
	type: "effect",
	match: (args: { trace: Trace }) => boolean,
	effect?: (args: { trace: Trace }) => Promise<void> | void
}
```

To activate these extensions, you would include them in your Web Chat installation code in the following way.

```
window.voiceflow.chat.load({
	...config,
	assistant: {
		extensions: [extension1, extension2, extension3, ...etc]
	}
});
```

These extensions can be triggered in your design using the **custom action step** or a **function**.

Let's walk through an example of a simple form below.

# Example 1: Custom Form

<Image align="center" src="https://files.readme.io/38847f8-CleanShot_2024-02-29_at_09.53.45_1.gif" />

## 1. Create the extension

An extension called **Custom\_Form** is written. This extension contains a field for name, email, and phone number. It also has a submit button. It also contains custom CSS that styles the form to appear like it does above.

**Where do I add this on my website?**

If you are using a Website builder you can add this **above** the chat widget script before the \</body> tag on your website. You can also include it on a separate file in your website and import the extension as shown in the github repository.

```
<script>
const FormExtension = {
  name: 'Forms',
  type: 'response',
  match: ({ trace }) =>
    trace.type === 'Custom_Form' || trace.payload?.name === 'Custom_Form',
  render: ({ trace, element }) => {
    const formContainer = document.createElement('form');

    formContainer.innerHTML = `
      <style>
        label {
          font-size: 0.8em;
          color: #888;
        }
        input[type="text"], input[type="email"], input[type="tel"] {
          width: 100%;
          border: none;
          border-bottom: 0.5px solid rgba(0, 0, 0, 0.1);
          background: transparent;
          margin: 5px 0;
          outline: none;
          padding: 8px 0; /* Added some padding for better UX */
        }
        .phone {
          width: 150px;
        }
        .invalid {
          border-color: red;
        }
        .submit {
          background: linear-gradient(to right, #2e6ee1, #2e7ff1);
          border: none;
          color: white;
          padding: 10px;
          border-radius: 5px;
          width: 100%;
          cursor: pointer;
        }
      </style>

      <label for="name">Name</label>
      <input type="text" class="name" name="name" required><br><br>

      <label for="email">Email</label>
      <input type="email" class="email" name="email" required pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\\.[a-z]{2,}$" title="Invalid email address"><br><br>

      <label for="phone">Phone Number</label>
      <input type="tel" class="phone" name="phone" required pattern="\\d+" title="Invalid phone number, please enter only numbers"><br><br>

      <input type="submit" class="submit" value="Submit">
    `;

    formContainer.addEventListener('input', function () {
      // Remove 'invalid' class when input becomes valid
      const name = formContainer.querySelector('.name');
      const email = formContainer.querySelector('.email');
      const phone = formContainer.querySelector('.phone');

      if (name.checkValidity()) name.classList.remove('invalid');
      if (email.checkValidity()) email.classList.remove('invalid');
      if (phone.checkValidity()) phone.classList.remove('invalid');
    });

    formContainer.addEventListener('submit', function (event) {
      event.preventDefault();

      const name = formContainer.querySelector('.name');
      const email = formContainer.querySelector('.email');
      const phone = formContainer.querySelector('.phone');

      if (
        !name.checkValidity() ||
        !email.checkValidity() ||
        !phone.checkValidity()
      ) {
        name.classList.add('invalid');
        email.classList.add('invalid');
        phone.classList.add('invalid');
        return;
      }

      formContainer.querySelector('.submit').remove();

      window.voiceflow.chat.interact({
        type: 'complete',
        payload: { name: name.value, email: email.value, phone: phone.value },
      });
    });

    element.appendChild(formContainer);
  },
};
</script>
```

You can get the full sample of extensions [here](https://github.com/voiceflow-gallagan/vf-extensions-demo/tree/c7a5eda8116dc915f0b85cf9014baeefe92a22c5).

## 2. Modify the Chat Widget Installation Code

The Web Chat widget is modified to include the extension **Custom\_Form**

```
window.voiceflow.chat.load({
  verify: {
    projectID: "<ID>"
  },
  url: "https://general-runtime.voiceflow.com",
  versionID: "production",
	assistant: {
		extensions: [FormExtension]
	}
});
```

There is no limit on the number of extensions you can add.

## 3. Trigger the Extension with a Custom Action

A custom action is added to the flow with the name **Custom\_Form**. We have turned the 'stop on action' setting on. This means that when this step is reached, the extension will be triggered and the agent will wait for a response to be received before proceeding.

![](https://files.readme.io/7e42c92-CleanShot_2024-03-06_at_17.11.072x.png)

<Image align="center" width="-4px" src="https://files.readme.io/703b286-CleanShot_2024-03-06_at_17.54.452x.png" />

When a user reaches the custom action, it will send the following **trace** to the Web Chat. This is what triggers the extension to appear.

```
  {
    "type": "Custom_Form",
    "payload": "{ }",
    "defaultPath": 0,
    "paths": [
      { "event": { "type": "Response_Submitted" } }
    ]
  }
```

## 4. Retrieve the response

Responses from the custom action are saved in a variable called `last_event`in Voiceflow. This can be accessed and parsed using the JavaScript step.

```
name = last_event.payload.name
```

![](https://files.readme.io/8f2c30c-CleanShot_2024-03-06_at_19.50.492x.png)

# Other Examples

For a number of other examples including file upload, forms, timers, date pickers, thumbs up/down and more please see the video and GitHub repo below.

<br />

<LinkCard type="Repo" title="Form extension demo" description="Add a form to your agent. Features waiting and done animatinos." href="https://github.com/voiceflow-gallagan/voiceflow-form-extension-demo" imageSrc="https://files.readme.io/ce7d6a8bfda19281a4c1518573122d11f20f5373dc9335afb838ab030f544050-Credits_1.png" />

<br />

[https://github.com/voiceflow-gallagan/vf-extensions-demo/tree/c7a5eda8116dc915f0b85cf9014baeefe92a22c5](https://github.com/voiceflow-gallagan/vf-extensions-demo/tree/c7a5eda8116dc915f0b85cf9014baeefe92a22c5)

<Embed url="https://www.youtube.com/watch?v=xY0vNkzFzAI" href="https://www.youtube.com/watch?v=xY0vNkzFzAI" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FxY0vNkzFzAI%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DxY0vNkzFzAI%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FxY0vNkzFzAI%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />