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

<Image title="gif.gif" alt={1280} align="center" src="https://files.readme.io/034697c-gif.gif">
  Discord and Voiceflow
</Image>

# Voiceflow Discord

### Use Voiceflow Dialog Manager API to run a Discord Bot

# Prerequisite

* [Replit](https://www.replit.com/) account
* [Discord App](https://discord.com/developers/applications)
* [Voiceflow](https://www.voiceflow.com/) **Chat Assistant** project

# Setup

![discord-logo.jpg](images/discord-logo.jpg)

### Create your Discord App

Go to to [https://discord.com/developers/applications](https://discord.com/developers/applications) to create your Discord app

![](https://files.readme.io/28f8e6a-image.png)

Name your application and click “**Create**”

![](https://files.readme.io/4c0d035-image.png)

From the General Information tab, copy the **APPLICATION ID** and **save it for later**

![](https://files.readme.io/d8edb03-image.png)

On the Bot tab, generate a Token by clicking on **Reset Token** button

![](https://files.readme.io/34c0389-image.png)

Copy the newly created token and **save it for later**

![](https://files.readme.io/7aa511a-image.png)

Scroll down and toggle **PRESENCE INTENT**, **SERVER MEMBERS INTENT** and **MESSAGE CONTENT INTENT**. Do not forget to save your changes.

![](https://files.readme.io/909cd52-image.png)

Now, on the OAuth2 tab, select bot for the **SCOPES** and give the **BOT PERMISSIONS** you need.

Once it’s done, click the **Copy** button at the bottom of the page.

![](https://files.readme.io/06c4bfa-image.png)

Open this link in a new tab and add the bot to **your Discord server**

![](https://files.readme.io/b046710-image.png)

![](https://files.readme.io/768f4ac-image.png)

![](https://files.readme.io/51dc8cb-image.png)

On your Discord server you should now see the bot in the Users tab and a new message

![](https://files.readme.io/e83aaf8-image.png)

![](https://files.readme.io/1a0bc7c-image.png)

If you haven’t activated the Developer Mode already, do it by going to the settings: **APP SETTINGS** > **Advanced**

![](https://files.readme.io/bb03b4c-image.png)

**Right click** on your server icon in the left sidebar, click on **Copy Server ID** and **save it for later**.

![](https://files.readme.io/b43b124-image.png)

You should now have: an app key, bot token, and server id

![](https://files.readme.io/fc74580-image.png)

### Get your project Dialog API key

Go to **Voiceflow Creator** and open the Chat Assistant project you want to use.\
Click on **Integration** from the left sidebar (or press the 6 key)

![](https://files.readme.io/46de4ff-image.png)

Select the **Dialog API** integration, click **Copy API Key** to copy your Voiceflow Dialog API Key and **save it for later**

![](https://files.readme.io/1ab3cf4-image.png)

![](https://files.readme.io/b586abb-image.png)

[Fork on Replit](https://replit.com/@niko-voiceflow/voiceflow-slackbot?v=1)

### Setup the Replit secrets

Set new Secrets with the following info

**DISCORD\_TOKEN**\
Discord bot token

**APP\_ID**\
Discord App ID

**SERVER\_ID**\
Discord server ID

**VOICEFLOW\_API\_URL**\
Voiceflow Dialog API endpoint (default to general runtime)

**VOICEFLOW\_API\_KEY**\
Voiceflow project API key (from the Integration section)

On the **Secrets tab**, you can click the **Edit as JSON** button and paste the following JSON (do not forget to update the keys values):

![](https://files.readme.io/4007a61-image.png)

```
{
  "DISCORD_TOKEN": "XXX",
  "APP_ID": "XXX",
  "SERVER_ID": "XXX",
  "VOICEFLOW_API_URL": "https://general-runtime.voiceflow.com",
  "VOICEFLOW_API_KEY": "VF.DM.XXX"
}

```

### Run your app on Replit

Once forked and updated with the Secrets, run your app and check the Console

![](https://files.readme.io/48ac947-image.png)

![](https://files.readme.io/0ad874a-image.png)

## Video

If you are a bit curious and want to dive in the code, we’ve made a video to go over the Node JS app and the different ways to interact with the Discord bot.

[https://www.loom.com/share/58af327708104dfaaec6ffb11d62b271](https://www.loom.com/share/58af327708104dfaaec6ffb11d62b271)
