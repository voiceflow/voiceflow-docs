---
title: Slack
excerpt: Build a Slackbot with Voiceflow's Dialog Manager and deploy to Heroku
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Get started

#### Use Voiceflow Dialog Manager API to run a Slack Bot

> 🚧 Before you start
> 
> - [Clone project from Github](https://github.com/voiceflow-gallagan/heroku-vf-slackbot)
> - [Heroku](https://www.heroku.com/) account
> - [Slack API](https://api.slack.com/) access
> - [Voiceflow](https://creator.voiceflow.com/) **Chat Assistant** project

# Setup

### Create your Slack App

> Go to to <https://api.slack.com/apps?new_app=1> to **create your Slack app**
>
> Select **From an app manifest**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8455349-slack-create-app.png",
        "slack-create-app.png",
        513
      ],
      "sizing": "80"
    }
  ]
}
[/block]



> Select the **workspace** you want to publish the app to

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0431d77-slack-select-workspace.png",
        "slack-select-workspace.png",
        511
      ],
      "sizing": "80"
    }
  ]
}
[/block]



> Choose **JSON** on the next screen and replace evrything with the manifest bellow

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/55d99d3-slack-manifest.png",
        "slack-manifest.png",
        514
      ],
      "sizing": "80"
    }
  ]
}
[/block]



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

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dc6b51d-slack-app-review.png",
        "slack-app-review.png",
        512
      ],
      "sizing": "80"
    }
  ]
}
[/block]



> **Install** the newly created app on your workspace

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bddc4c4-slack-install.png",
        "slack-install.png",
        979
      ],
      "sizing": "80"
    }
  ]
}
[/block]



> Click on **Allow** to finish to install the app on your Workspace

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7358d50-slack-allow.png",
        "slack-allow.png",
        572
      ],
      "sizing": "80"
    }
  ]
}
[/block]



### Generate a signin key and tokens

> On the main screen, you want to **copy the secret key** and **keep it for later**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/801c740-slack-signin-secret.png",
        "slack-signin-secret.png",
        679
      ],
      "sizing": "80"
    }
  ]
}
[/block]



> Scroll down and click on **Generate Token and Scopes**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/64b1d0b-slack-app-level-tokens.png",
        "slack-app-level-tokens.png",
        681
      ],
      "sizing": "80"
    }
  ]
}
[/block]



> Give this Token a **name** and add the **connections:write** scope to it. Then click on **Generate**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a048b7f-slack-app-level-scope.png",
        "slack-app-level-scope.png",
        513
      ],
      "sizing": "80"
    }
  ]
}
[/block]



> Copy the **app token** and **save it for later**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5a21372-slack-app-token.png",
        "slack-app-token.png",
        511
      ],
      "sizing": "80"
    }
  ]
}
[/block]



> Go to the **OAuth & Permissions** section, copy the **Bot User OAuth Token** from there and save it for later

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/974a2c8-slack-bot-user-token.png",
        "slack-bot-user-token.png",
        969
      ],
      "sizing": "80"
    }
  ]
}
[/block]



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

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/af0cf6a-voiceflow-integration.png",
        "voiceflow-integration.png",
        351
      ],
      "sizing": "80"
    }
  ]
}
[/block]



> Click **Copy** to copy your Voiceflow Dialog API Key and save it for later

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fc371df-voiceflow-copy.png",
        "voiceflow-copy.png",
        1066
      ],
      "sizing": "80"
    }
  ]
}
[/block]



# Heroku

### Deploy this code to Heroku

<a href="https://heroku.com/deploy" target="_blank"><img src="https://www.herokucdn.com/deploy/button.svg" alt="Heroku logo" width="180"/></a>

### Setup the Heroku app

> Choose a **name** for your app  
> Set the config var with all the info you've previously saved

**SLACK\_APP\_TOKEN**  
Slack **app secret** (starting with **xapp-**)

**SLACK\_BOT\_TOKEN**  
Slack **bot token** (starting with **xoxb-**)

**SLACK\_SIGNING\_SECRET**  
Slack app **signing secret**

**VOICEFLOW\_API\_KEY**  
Voiceflow **project API key** (from the Integration section)

> Click on **Deploy app**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a3a76c5-heroku-setup.png",
        "heroku-setup.png",
        727
      ],
      "sizing": "80"
    }
  ]
}
[/block]



> Wait for your app to be fully deployed

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/88e58a9-heroku-deploy.png",
        "heroku-deploy.png",
        651
      ],
      "sizing": "80"
    }
  ]
}
[/block]



> **Last important thing we want to do is to swap ressources on your Heroky app.**  
> Here we want to **turn off** the **web** and **turn on** the **worker** as the Slack bot is setup in **socket mode**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e5c0327-heroku-ressources.png",
        "heroku-ressources.png",
        776
      ],
      "sizing": "80"
    }
  ]
}
[/block]



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eacf9b2-heroku-worker-confirm.png",
        "heroku-worker-confirm.png",
        767
      ],
      "sizing": "80"
    }
  ]
}
[/block]



> After the changes, your config **should look like this**:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0ad5752-heroku-worker.png",
        "heroku-worker.png",
        768
      ],
      "sizing": "80"
    }
  ]
}
[/block]



# Slack

### Install your Slack App

> On your **Slack workspace**, click on **Apps** > **Add apps**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/84ffbd2-slack-add-app.png",
        "slack-add-app.png",
        855
      ],
      "sizing": "80"
    }
  ]
}
[/block]



> **Search** for 'Voiceflow Slack Demo' or the app name you've created earlier on Slack API website and **click on it** in the Search results list to install it

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4d7b8c8-slack-install-app.png",
        "slack-install-app.png",
        848
      ],
      "sizing": "80"
    }
  ]
}
[/block]



> The app is now available and you can click on **Messages** to start interacting with your bot.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a36dc87-slack-try-app.png",
        "slack-try-app.png",
        849
      ],
      "sizing": "80"
    }
  ]
}
[/block]



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ae76f9d-slack-bot.png",
        "slack-bot.png",
        775
      ],
      "sizing": "80"
    }
  ]
}
[/block]