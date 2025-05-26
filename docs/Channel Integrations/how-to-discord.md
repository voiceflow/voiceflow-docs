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

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/034697c-gif.gif",
        "gif.gif",
        1280
      ],
      "caption": "Discord and Voiceflow"
    }
  ]
}
[/block]

> 🚧 Before you start
> 
> Make sure you have:
> 
> 1. **Setup a Discord bot on your DIscord server**: [How to](https://www.freecodecamp.org/news/create-a-discord-bot-with-python/)
> 2. **Created a Voiceflow project. **You need to first build a chat project on [Voiceflow](https://creator.voiceflow.com/)
> 3. [Template source code on Github](https://github.com/zslamkov/voiceflow_discord)

## Setup

To obtain your `versionID` you have to go to your Voiceflow Project:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3b61b4b-Screen_Shot_2022-02-11_at_11.08.51_AM.png",
        "Screen Shot 2022-02-11 at 11.08.51 AM.png",
        1724
      ],
      "caption": "Find VersionID"
    }
  ]
}
[/block]

Then copy the `VERSION_ID` from the URL in your address bar. When you are inside a Voiceflow project, your address bar should have a URL of the form: `<https://creator.voiceflow.com/project/{VERSION_ID}/...`>

`apiKey`  
To obtain the Workspace API Key we have to go to our workspace where we have created our General Project. After this, we have to append to the URL /api-keys:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/86e83a6-Screen_Shot_2022-03-30_at_12.37.57_PM.png",
        "Screen Shot 2022-03-30 at 12.37.57 PM.png",
        1579
      ],
      "caption": "Find API Key"
    }
  ]
}
[/block]

## Video Walkthrough

In the video below, we cover the entire integration between Voiceflow and Discord. 


[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2Fy34Zjznkz_4%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3Dy34Zjznkz_4&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2Fy34Zjznkz_4%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=y34Zjznkz_4&feature=youtu.be",
  "title": "How to build a Discord bot using Voiceflow's Dialog Manager API",
  "favicon": "https://www.youtube.com/s/desktop/ecd7151d/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/y34Zjznkz_4/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=y34Zjznkz_4&feature=youtu.be"
}
[/block]




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