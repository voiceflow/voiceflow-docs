---
title: Step 4 - Deploy Assistant
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
Now that your assistant is ready to go, let's deploy it to production and add it to a channel.

## Deploying to Production

To deploy your assistant to production you need to do the two following steps.

1. Run a preview of the assistant: This compiles the project
2. Press 'Publish' on the top right: This pushes the version to production
3. Create a Version: This allows you to roll back if something breaks

When you press publish it will prompt you to create a version. Previous versions can be viewed in the project settings.

Once the project has been published (there will be a progress bar on the top of the screen). You are ready to move to the next step.

![](https://files.readme.io/c24ade5-image.png)

## Adding to a Website

If you have created a Web Chat type project, you can easily add your chatbot to any website. To access the snippet - click 'embed widget' or visit the integrations tab on the left side of the screen.

Once you're there you simply have to copy this snippet and add it to your website code. You can either add it to the footer file or your website if you want it to appear on every page, or at the bottom before the closing `</body>` tag on the specific page you want it on.

![](https://files.readme.io/ed3798a-image.png)

Here's a quick video overview of how to test it out. For basic instructions on how to customize the web chat appearance click [here](https://learn.voiceflow.com/hc/en-us/articles/10569376208781). For instructions on how to further customize the web chat, go [here](https://developer.voiceflow.com/docs/chat-widget).

<Embed url="https://www.loom.com/share/2b114b92a81143c2805030c2efeecb96" title="Preview on a Website" image="https://cdn.loom.com/sessions/thumbnails/2b114b92a81143c2805030c2efeecb96-00001.gif" provider="loom.com" href="https://www.loom.com/share/2b114b92a81143c2805030c2efeecb96" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.loom.com%252Fembed%252F2b114b92a81143c2805030c2efeecb96%26display_name%3DLoom%26url%3Dhttps%253A%252F%252Fwww.loom.com%252Fshare%252F2b114b92a81143c2805030c2efeecb96%26image%3Dhttps%253A%252F%252Fcdn.loom.com%252Fsessions%252Fthumbnails%252F2b114b92a81143c2805030c2efeecb96-00001.gif%26key%3D02466f963b9b4bb8845a05b53d3235d7%26type%3Dtext%252Fhtml%26schema%3Dloom%22%20width%3D%221152%22%20height%3D%22864%22%20scrolling%3D%22no%22%20title%3D%22Loom%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## Using the API

**Clone the starter pack**\
Download the API Examples repo found [here](https://github.com/voiceflow/api-examples) to access a variety of prebuilt API examples, including Node.js, Python, Rust and HTML.

**Authentication**\
We'll need to access the `Project API key` for the design we want to connect into our app. To obtain the API Key:

1. Open the Assistant project you are using
2. Select on the **Integrations** tab (shortcut: `3`). Found on the left-hand menu.
3. Copy the `Dialog API Key` found in the Dialog API section.

<Image alt="Above you can see the Integrations section within an Assistant project" align="center" src="https://files.readme.io/dcf4795-small-CleanShot_2023-05-02_at_00.30.30.png">
  Above you can see the Integrations section within an Assistant project
</Image>

## Launch

Open up the API Examples pack in your favourite code editor.

> 👍 **HTML and JQuery**
>
> 1. Replace `'YOUR_API_KEY_HERE'` in `index.html` with your API Key.
> 2. Open index.html on any browser to start your chat!

Example:

![](https://files.readme.io/bc3f16c-small-CleanShot_2023-05-02_at_00.27.30.png)

> 👍 Node.js
>
> 1. If you do not have node, install *Node.js* and npm from [nodejs.org](https://nodejs.org/en/), or follow an equivalent guide.
> 2. In this folder, run `npm install.`
> 3. Replace `'YOUR_API_KEY_HERE'` in `index.js` with your Dialog Manager API Key.
> 4. run `npm` start to start your chat!

Example:

```text
$ npm start

> What is your name?: tyler
what can I do for you?
...
> Say something: send email
who is the recipient?
...
> Say something: tyler@voiceflow.com
what is the title of your email?
...
> Say something: How was your day?
sending the email for tyler@voiceflow.com called "How was your day?". Is that correct?
...
> Say something: yes
successfully sent the email for tyler@voiceflow.com called "How was your day?"
The end! Start me again with `npm start`
```

## Video Walkthrough

<Embed url="https://www.youtube.com/watch?v=wRsKbRiFz6g&feature=youtu.be" title="Get started with Voiceflow's Dialog Manager API" favicon="https://www.youtube.com/s/desktop/ecd7151d/img/favicon.ico" provider="youtube.com" href="https://www.youtube.com/watch?v=wRsKbRiFz6g&feature=youtu.be" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FwRsKbRiFz6g%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DwRsKbRiFz6g%26key%3D02466f963b9b4bb8845a05b53d3235d7%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22640%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

**Dialog Manager API Examples**

[https://github.com/voiceflow/api-examples](https://github.com/voiceflow/api-examples)

## Scaling Your Assistant

To learn how to scale your assistant you can visit our guides below

* [Design Best Practices](https://learn.voiceflow.com/hc/en-us/articles/10875693411085)