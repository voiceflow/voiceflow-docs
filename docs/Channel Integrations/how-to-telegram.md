---
title: Telegram
excerpt: Learn the basics of building a Telegram bot with Voiceflow's Dialog Manager.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Get started

In this guide, we are creating a Telegram bot that is connected directly with a Voiceflow CxD.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/236a926-telegram_gif.gif",
        "telegram_gif.gif",
        1464
      ],
      "caption": "Telegram bot"
    }
  ]
}
[/block]

> 🚧 Before you start
> 
> 1. **Create a Voiceflow project**: you need to first build a chat project on [Voiceflow](https://creator.voiceflow.com/)
> 2. **Find your Project API Key**: Follow these [instructions](https://developer.voiceflow.com/reference/project) to obtain your API key.
> 3. [Template source code on Github](https://github.com/zslamkov/voiceflow_telegram)

## Create your Telegram bot

First, create a bot with BotFather. BotFather is the one bot to rule them all. We will use it to create new bot accounts and manage your existing bots.

If you open a chat with a BotFather, click on the “Start” button.

We should create a new bot by clicking `/newbot` command. Next, you should enter any name for the bot. In this example, we named it VF Game.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b38ea87-Screen_Shot_2022-03-15_at_9.54.16_AM.png",
        "Screen Shot 2022-03-15 at 9.54.16 AM.png",
        1077
      ],
      "caption": "BotFather"
    }
  ]
}
[/block]

The Telegram setup is completed! Remember to add your Telegram token to your `.env` file in the property `BOT_TOKEN`

## Telegraf setup

We can create bot by the following code lines:

```javascript
const Telegraf = require('telegraf') // import telegram lib

const bot = new Telegraf(process.env.BOT_TOKEN) // get the token from envirenment variable
bot.start((ctx) => ctx.reply('Welcome')) // display Welcome text when we start bot
bot.hears('hi', (ctx) => ctx.reply('Hey there')) // listen and handle when user type hi text
bot.launch() // start
```



## Voiceflow setup

First, create a new function that takes Telegraf `ctx`, `userID` and a `request` in as arguments:  
`async function interact(ctx, chatID, request){}`

Inside the function, make an API call to the Voiceflow `/interact` endpoint.

```javascript
const response = await axios({
        method: "POST",
        url: `https://general-runtime.voiceflow.com/state/user/${chatID}/interact`,
        headers: {
            Authorization: process.env.VOICEFLOW_API_KEY
        },
        data: {
            request
        }
    });
```



Expect Voiceflow to return an array. Iterate over the array to map the various response types to an operation.

```javascript
for (const trace of response.data) {
        switch (trace.type) {
            case "text":
            case "speak":
                {
                    await ctx.reply(trace.payload.message);
                    break;
                }
            case "visual":
                {
                    await ctx.replyWithPhoto(trace.payload.image);
                    break;
                }
            case "end":
                {
                    await ctx.reply("Conversation is over")
                    break;
                }
        }
    }
```



Everything is ready. Let's continue with our Telegrom bot code. Let's replace the start standard replay for this one, getting the correct replay from Voiceflow:

```javascript
bot.start(async (ctx) => {
    let chatID = ctx.message.chat.id;
    await interact(ctx, ctx.message.chat.id, {type: "launch"});
});
```



Then we replace the hi utterance for a regex like (.+). This means that the bot will hear for everything. All the text recieved we will pass directly to Voiceflow and the we mange the state of the conversation: if it is ended or if it is not ended yet:

```javascript
const ANY_WORD_REGEX = new RegExp(/(.+)/i);
bot.hears(ANY_WORD_REGEX, async (ctx) => {
    let chatID = ctx.message.chat.id;
  	await interact(ctx, chatID, {
        type: "text",
        payload: ctx.message.text
    });
```



## Video Walkthrough

In the video below, we cover the entire integration between Voiceflow and Telegram.


[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FsRLLWcnLurg%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DsRLLWcnLurg&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FsRLLWcnLurg%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=sRLLWcnLurg&feature=youtu.be",
  "title": "How to build a Telegram bot using Voiceflow's Dialog Manager",
  "favicon": "https://www.youtube.com/s/desktop/a1277e8a/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/sRLLWcnLurg/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=sRLLWcnLurg&feature=youtu.be"
}
[/block]




## Sample Code

```javascript app.js
const {Telegraf} = require('telegraf') // import telegram lib
const axios = require('axios');

require('dotenv').config();

const bot = new Telegraf(process.env.BOT_TOKEN) // get the token from environment variable

async function interact(ctx, chatID, request) {

    const response = await axios({
        method: "POST",
        url: `https://general-runtime.voiceflow.com/state/user/${chatID}/interact`,
        headers: {
            Authorization: process.env.VOICEFLOW_API_KEY
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
                    await ctx.reply(trace.payload.message);
                    break;
                }
            case "visual":
                {
                    await ctx.replyWithPhoto(trace.payload.image);
                    break;
                }
            case "end":
                {
                    await ctx.reply("Conversation is over")
                    break;
                }
        }
    }
};


bot.start(async (ctx) => {
    let chatID = ctx.message.chat.id;
    await interact(ctx, chatID, {type: "launch"});
});

const ANY_WORD_REGEX = new RegExp(/(.+)/i);
bot.hears(ANY_WORD_REGEX, async (ctx) => {
    let chatID = ctx.message.chat.id;
  	await interact(ctx, chatID, {
        type: "text",
        payload: ctx.message.text
    });
});

bot.launch() // start

process.once('SIGINT', () => bot.stop('SIGINT'))
process.once('SIGTERM', () => bot.stop('SIGTERM'))
```



# Voiceflow Community Challenge

***



When your bot is part of a group chat, make sure that it can maintain context with the various users 

Share it on Twitter and make sure to mention @voiceflow!