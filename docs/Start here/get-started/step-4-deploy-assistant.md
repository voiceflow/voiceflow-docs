---
title: Step 4 - Deploy Assistant
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
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

Once you're there you simply have to copy this snippet and add it to your website code. You can either add it to the footer file or your website if you want it to appear on every page, or at the bottom before the closing </body> tag on the specific page you want it on.

![](https://files.readme.io/ed3798a-image.png)

Here's a quick video overview of how to test it out. For basic instructions on how to customize the web chat appearance click [here](https://learn.voiceflow.com/hc/en-us/articles/10569376208781). For instructions on how to further customize the web chat, go [here](https://developer.voiceflow.com/docs/chat-widget).


[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.loom.com%2Fembed%2F2b114b92a81143c2805030c2efeecb96&display_name=Loom&url=https%3A%2F%2Fwww.loom.com%2Fshare%2F2b114b92a81143c2805030c2efeecb96&image=https%3A%2F%2Fcdn.loom.com%2Fsessions%2Fthumbnails%2F2b114b92a81143c2805030c2efeecb96-00001.gif&key=02466f963b9b4bb8845a05b53d3235d7&type=text%2Fhtml&schema=loom\" width=\"1152\" height=\"864\" scrolling=\"no\" title=\"Loom embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.loom.com/share/2b114b92a81143c2805030c2efeecb96",
  "title": "Preview on a Website",
  "image": "https://cdn.loom.com/sessions/thumbnails/2b114b92a81143c2805030c2efeecb96-00001.gif",
  "provider": "loom.com",
  "href": "https://www.loom.com/share/2b114b92a81143c2805030c2efeecb96",
  "typeOfEmbed": "youtube"
}
[/block]


## Using the API

**Clone the starter pack**  
Download the API Examples repo found [here](https://github.com/voiceflow/api-examples) to access a variety of prebuilt API examples, including Node.js, Python, Rust and HTML.

**Authentication**  
We'll need to access the `Project API key` for the design we want to connect into our app. To obtain the API Key:

1. Open the Assistant project you are using
2. Select on the **Integrations** tab (shortcut: `3`). Found on the left-hand menu.
3. Copy the `Dialog API Key` found in the Dialog API section.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dcf4795-small-CleanShot_2023-05-02_at_00.30.30.png",
        null,
        "Above you can see the Integrations section within an Assistant project"
      ],
      "align": "center",
      "caption": "Above you can see the Integrations section within an Assistant project"
    }
  ]
}
[/block]

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
> 1. If you do not have node, install _Node.js_ and npm from [nodejs.org](https://nodejs.org/en/), or follow an equivalent guide.
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


[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FwRsKbRiFz6g%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DwRsKbRiFz6g&key=02466f963b9b4bb8845a05b53d3235d7&type=text%2Fhtml&schema=youtube\" width=\"640\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=wRsKbRiFz6g&feature=youtu.be",
  "title": "Get started with Voiceflow's Dialog Manager API",
  "favicon": "https://www.youtube.com/s/desktop/ecd7151d/img/favicon.ico",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=wRsKbRiFz6g&feature=youtu.be"
}
[/block]


**Dialog Manager API Examples**

<https://github.com/voiceflow/api-examples>



## Scaling Your Assistant

To learn how to scale your assistant you can visit our guides below

- [Design Best Practices](https://learn.voiceflow.com/hc/en-us/articles/10875693411085)