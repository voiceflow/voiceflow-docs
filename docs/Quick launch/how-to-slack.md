---
title: Slack
excerpt: Build a Slackbot with Voiceflow's Dialog Manager and deploy to Heroku
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Voiceflow Slackbot

#### Use Voiceflow Dialog Manager API to run a Slack Bot

# Updates

```
[v1.0]
- Fix for Socket Mode on Heroku
- Handle weblinks in Text step
- Translate text styling to Slack Markdown format

[v1.0.1]
- Handle choice/buttons
- Updated logic to translate slate text

[v1.0.2]
- Add createSession function
- Updated interact to save transcript
- Migrate from Heroku to Replit
```

# Prerequisite

* [Replit](https://www.replit.com/) account
* [Slack API](https://api.slack.com/) access
* [Voiceflow](https://www.voiceflow.com) **Chat Assistant** project

# Setup

### Create your Slack App

> Go to to [https://api.slack.com/apps?new\_app=1](https://api.slack.com/apps?new_app=1) to **create your Slack app**
>
> Select **From an app manifest**

<Image align="center" width="80%" src="https://files.readme.io/8455349-slack-create-app.png" />

> Select the **workspace** you want to publish the app to

<Image align="center" width="80%" src="https://files.readme.io/0431d77-slack-select-workspace.png" />

> Choose **JSON** on the next screen and replace evrything with the manifest bellow

<Image align="center" width="80%" src="https://files.readme.io/55d99d3-slack-manifest.png" />

```json
{
    "display_information": {
        "name": "Voiceflow Slack Demo",
        "description": "Slack Assistant using Voiceflow Dialog Manager API",
        "background_color": "#37393d"
    },
    "features": {
        "app_home": {
            "home_tab_enabled": true,
            "messages_tab_enabled": true,
            "messages_tab_read_only_enabled": false
        },
        "bot_user": {
            "display_name": "Voiceflow Demo",
            "always_online": true
        }
    },
    "oauth_config": {
        "scopes": {
            "user": [
                "users:read"
            ],
            "bot": [
                "app_mentions:read",
                "channels:history",
                "chat:write",
                "im:history",
                "im:read",
                "im:write",
                "mpim:history",
                "mpim:read",
                "mpim:write",
                "users.profile:read",
                "users:read"
            ]
        }
    },
    "settings": {
        "event_subscriptions": {
            "user_events": [
                "message.app_home",
                "user_change"
            ],
            "bot_events": [
                "app_home_opened",
                "app_mention",
                "message.channels",
                "message.im",
                "message.mpim",
                "user_change"
            ]
        },
        "interactivity": {
            "is_enabled": true
        },
        "org_deploy_enabled": false,
        "socket_mode_enabled": true,
        "token_rotation_enabled": false
    }
}
```

> Click **Next** at the bottom of the window

![](https://files.readme.io/9ce963b-slack-app-next.png "slack-app-next.png")

> **Review** the app details and comfirm by clicking on **Create**

<Image align="center" width="80%" src="https://files.readme.io/dc6b51d-slack-app-review.png" />

> **Install** the newly created app on your workspace

<Image align="center" width="80%" src="https://files.readme.io/bddc4c4-slack-install.png" />

> Click on **Allow** to finish to install the app on your Workspace

<Image align="center" width="80%" src="https://files.readme.io/7358d50-slack-allow.png" />

### Generate a signin key and tokens

> On the main screen, you want to **copy the secret key** and **keep it for later**

<Image align="center" width="80%" src="https://files.readme.io/801c740-slack-signin-secret.png" />

> Scroll down and click on **Generate Token and Scopes**

<Image align="center" width="80%" src="https://files.readme.io/64b1d0b-slack-app-level-tokens.png" />

> Give this Token a **name** and add the **connections:write** scope to it. Then click on **Generate**

<Image align="center" width="80%" src="https://files.readme.io/a048b7f-slack-app-level-scope.png" />

> Copy the **app token** and **save it for later**

<Image align="center" width="80%" src="https://files.readme.io/5a21372-slack-app-token.png" />

> Go to the **OAuth & Permissions** section, copy the **Bot User OAuth Token** from there and save it for later

<Image align="center" width="80%" src="https://files.readme.io/974a2c8-slack-bot-user-token.png" />

> You should now have:

```
a **secret key**
an **app token**
a **bot token**
```

# Voiceflow

### Get your project Dialog API key

> Go to [Voiceflow Creator](https://creator.voiceflow.com) and open the **Chat Assistant project** you want to use
>
> On your project, click on **Integration** from the left sidebar (or press the **3** key)

<Image align="center" width="80%" src="https://files.readme.io/af0cf6a-voiceflow-integration.png" />

> Click **Copy** to copy your Voiceflow Dialog API Key and save it for later

<Image align="center" width="80%" src="https://files.readme.io/fc371df-voiceflow-copy.png" />

# To Deploy on Replit

### ->  [Fork on Replit](https://replit.com/@niko-voiceflow/voiceflow-slackbot?v=1)

*Click this link to fork the project on Replit to your account.*

### Setup the Replit secrets

> Set new Secrets with the following info

**SLACK\_APP\_TOKEN**\
Slack **app secret** (starting with **xapp-**)

**SLACK\_BOT\_TOKEN**\
Slack **bot token** (starting with **xoxb-**)

**SLACK\_SIGNING\_SECRET**\
Slack app **signing secret**

**VOICEFLOW\_VERSION\_ID**\
Voiceflow **project version ID** (Needed if you want to save transcripts, will default to 'production' otherwise)

**VOICEFLOW\_API\_KEY**\
Voiceflow **project API key** (from the Integration section)

In the Secrets tab, you can click on Edit as JSON button and paste the following JSON (do not forget to update the keys values):

```
{
  "VOICEFLOW_API_KEY":"VF.12345678",
  "VOICEFLOW_VERSION_ID":"12345678",
  "VOICEFLOW_RUNTIME_ENDPOINT":"general-runtime.voiceflow.com",
  "SLACK_APP_TOKEN":"XXXX",
  "SLACK_BOT_TOKEN":"XXXXX",
  "SLACK_SIGNING_SECRET":"XXXXXXX"
}
```

### Setup the Replit secrets

> Set new Secrets with the following info

**SLACK\_APP\_TOKEN**\
Slack **app secret** (starting with **xapp-**)

**SLACK\_BOT\_TOKEN**\
Slack **bot token** (starting with **xoxb-**)

**SLACK\_SIGNING\_SECRET**\
Slack app **signing secret**

**VOICEFLOW\_VERSION\_ID**\
Voiceflow **project version ID** (Needed if you want to save transcripts, will default to 'production' otherwise)

**VOICEFLOW\_API\_KEY**\
Voiceflow **project API key** (from the Integration section)

In the Secrets tab, you can click on Edit as JSON button and paste the following JSON (do not forget to update the keys values):

```
{
  "VOICEFLOW_API_KEY":"VF.12345678",
  "VOICEFLOW_VERSION_ID":"12345678",
  "VOICEFLOW_RUNTIME_ENDPOINT":"general-runtime.voiceflow.com",
  "SLACK_APP_TOKEN":"XXXX",
  "SLACK_BOT_TOKEN":"XXXXX",
  "SLACK_SIGNING_SECRET":"XXXXXXX"
}
```

# Slack

### Install your Slack App

> On your **Slack workspace**, click on **Apps** > **Add apps**

<Image align="center" width="80%" src="https://files.readme.io/84ffbd2-slack-add-app.png" />

> **Search** for 'Voiceflow Slack Demo' or the app name you've created earlier on Slack API website and **click on it** in the Search results list to install it

<Image align="center" width="80%" src="https://files.readme.io/4d7b8c8-slack-install-app.png" />

> The app is now available and you can click on **Messages** to start interacting with your bot.

<Image align="center" width="80%" src="https://files.readme.io/a36dc87-slack-try-app.png" />

<Image align="center" width="80%" src="https://files.readme.io/ae76f9d-slack-bot.png" />
