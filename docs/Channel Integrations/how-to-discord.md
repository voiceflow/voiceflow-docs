---
title: Discord
excerpt: Learn the basics of building a Discord bot with Voiceflow's Dialog Manager.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Build your assistant

In this guide, we are creating an assistant that is connected directly with Voiceflow. 

<Image title="gif.gif" alt={1280} src="https://files.readme.io/034697c-gif.gif">
  Discord and Voiceflow
</Image>

> 🚧 Before you start
>
> Make sure you have:
>
> 1. **Setup a Discord bot on your DIscord server**: [How to](https://www.freecodecamp.org/news/create-a-discord-bot-with-python/)
> 2. **Created a Voiceflow project.** You need to first build a chat project on [Voiceflow](https://creator.voiceflow.com/)
> 3. [Template source code on Github](https://github.com/zslamkov/voiceflow_discord)

## Setup

To obtain your `versionID` you have to go to your Voiceflow Project:

<Image title="Screen Shot 2022-02-11 at 11.08.51 AM.png" alt={1724} src="https://files.readme.io/3b61b4b-Screen_Shot_2022-02-11_at_11.08.51_AM.png">
  Find VersionID
</Image>

Then copy the `VERSION_ID` from the URL in your address bar. When you are inside a Voiceflow project, your address bar should have a URL of the form: `<https://creator.voiceflow.com/project/{VERSION_ID}/...`>

`apiKey`\
To obtain the Workspace API Key we have to go to our workspace where we have created our General Project. After this, we have to append to the URL /api-keys:

<Image title="Screen Shot 2022-03-30 at 12.37.57 PM.png" alt={1579} src="https://files.readme.io/86e83a6-Screen_Shot_2022-03-30_at_12.37.57_PM.png">
  Find API Key
</Image>

## Video Walkthrough

In the video below, we cover the entire integration between Voiceflow and Discord. 

<Embed url="https://www.youtube.com/watch?v=y34Zjznkz_4&feature=youtu.be" title="How to build a Discord bot using Voiceflow's Dialog Manager API" favicon="https://www.youtube.com/s/desktop/ecd7151d/img/favicon.ico" image="https://i.ytimg.com/vi/y34Zjznkz_4/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=y34Zjznkz_4&feature=youtu.be" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252Fy34Zjznkz_4%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253Dy34Zjznkz_4%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252Fy34Zjznkz_4%252Fhqdefault.jpg%26key%3Df2aa6fc3595946d0afc3d76cbbd25dc3%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## Source Code

```javascript
const Discord = require('discord.js');
const axios = require('axios');

const discordClient = new Discord.Client();

//Add start command to activate bot in Discord
const START_COMMAND = '!starter';
let isRunning = false;

// Add Voiceflow versionID and apiKey. You can find this on the project 
const versionID = "xxx";
const apiKey = "VF.xxx.xxx";


discordClient.on('message', async (message) => {
    if (message.author.bot) 
        return;

    if (message.content !== START_COMMAND && ! isRunning) 
        return;
    

    const userID = message.author.username;

    async function interact(userID, request) {
      // Dialog Manager POST request
      const response = await axios({
            method: "POST",
            url: `https://general-runtime.voiceflow.com/state/${versionID}/user/${userID}/interact`,
            headers: {
                Authorization: apiKey
            },
            data: {
                request
            }
        });

        for (const trace of response.data) {
            switch (trace.type) {
                case "text":
                case "speak":
                    {
                        message.channel.send(trace.payload.message);
                        break;
                    }
                case "end":
                    {
                        return false;
                    }
            }
        }
        return true;
    }
    isRunning = message.content === START_COMMAND ? await interact(userID, {type: "launch"}) : await interact(userID, {
        type: "text",
        payload: message.content
    });
    if (! isRunning) {
        message.channel.send("Try again by saying the starter command");
    }
});

//Login to Discord bot using your bot token
discordClient.login("{discord_bot_token}");
```

# Voiceflow Community Challenge

***

Try triggering a response from the assistant through a message reaction (e.g. with a 😊 )

Share it on Twitter and make sure to mention @voiceflow!
