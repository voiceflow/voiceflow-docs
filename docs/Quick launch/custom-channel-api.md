---
title: Custom Channel (API)
excerpt: Use the Dialog API to deploy Assistants to custom channels.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Overview

You can use the Dialog API to integrate your Assistant with any custom channel or interface (voice, chat or multimodal). Any Voiceflow Project Type works with a Custom Channel deployment as it uses the Dialog API which is available across every project type.

The Dialog API integrates through a REST API with your Custom Channel.

## Example Custom Channel Deployment

> 🚧 First steps
>
> Before you start with the Dialog API, you need to create a project on your Voiceflow [workspace](https://creator.voiceflow.com/).

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

<Embed url="https://github.com/voiceflow/api-examples" title="GitHub - voiceflow/api-examples: examples implementing the voiceflow dialog manager API" favicon="https://github.com/favicon.ico" image="https://opengraph.githubassets.com/d5a9bd46f368f48bf1772a03d599fa9b4aac8f857b866e5fee879c9d47857638/voiceflow/api-examples" provider="github.com" href="https://github.com/voiceflow/api-examples" />
