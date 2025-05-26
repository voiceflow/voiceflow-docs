---
title: Microsoft Teams (old)
excerpt: >-
  Learn the basics of building a Microsoft Teams bot with Voiceflow's Dialog
  Manager.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
In this article, we will work on an integration for Microsoft Teams and the Voiceflow Dialog Manager API.

> 🚧 Before you start
>
> 1. **Create a Voiceflow project**: you need to first build a chat project on [Voiceflow](https://creator.voiceflow.com/).
> 2. **Find your Project API Key**: Follow these [instructions](https://developer.voiceflow.com/reference/project) to obtain your API key.
> 3. Microsoft Teams account
> 4. [Template source code on Github](https://github.com/voiceflow-gallagan/api-integration-msteams)

## 1. Setting up the application and creating a bot in Teams

The first this you will have to do is to add the Developer Portal app to your Teams:

![](https://files.readme.io/1f46778-CleanShot_2022-08-17_at_19.45.56.png)

After the install you will find the app on the left sidebar:

![](https://files.readme.io/82b834a-CleanShot_2022-08-18_at_20.07.02.png)

Go to the **Apps** tab and click on **+ New app**

![](https://files.readme.io/b9feb04-CleanShot_2022-08-18_at_20.20.57.png)

The next steps are pretty straight forward as you just need to fill the required fields.

![](https://files.readme.io/17e28cd-CleanShot_2022-08-18_at_19.58.26.png)

![](https://files.readme.io/df769e5-CleanShot_2022-08-18_at_20.01.13.png)

Click Save to create the app.

![](https://files.readme.io/d505861-CleanShot_2022-08-17_at_19.53.22.png)

Now, create a Bot for your app.

Form the Tool tab, click on **+ New Bot**

We want to create a new Bot so click on the **Create a new bot** link

![](https://files.readme.io/68d9c6f-CleanShot_2022-08-18_at_21.58.50.png)

Keep that page **open** as we will need it later to fill the **Bot endpoint** address and generate a **client secret**:

![](https://files.readme.io/97e6086-CleanShot_2022-08-18_at_20.24.25.png)

## 2. Setting up the code

> 🚧
>
> For the following step, we are assuming that your dev environment is already setup

In a directory, clone the following Git repository and install the dependencies: [https://github.com/voiceflow-gallagan/api-integration-msteams](https://github.com/voiceflow-gallagan/api-integration-msteams)

```shell
git clone https://github.com/voiceflow-gallagan/api-integration-msteams.git
cd api-integration-msteams && npm i
```

Open the **.env.template** file in the editor of your choice:

```
MicrosoftAppId='<your bot id>'
MicrosoftAppPassword='<your bot secret>'
VOICEFLOW_VERSION='development'
VOICEFLOW_API_KEY='<Voiceflow Chat project API>'
VOICEFLOW_RUNTIME_ENDPOINT='https://general-runtime.voiceflow.com'
TUNNEL_SUBDOMAIN='voiceflow-teams'
PORT=3978
```

Update the **TUNNEL\_SUBDOMAIN** with the subdomain of your choice. Try to use something “unique” as we will use it to generate a tunnel so you will be able to test your Bot in Teams.

For the **VOICEFLOW\_API\_KEY**, simply copy/paste it form your Voiceflow’s project.

* open your Chat project in Voiceflow
* click on the Integrations button in the sidebar (shortcut: 4)
* copy your Dialog API key
* paste it in the **.env.template** file

![](https://files.readme.io/7efd358-CleanShot_2022-08-18_at_21.40.08.png)

If you want to, you can also change the port you want to use. Here we will keep **3978**.

Now, we will need to grab the **MicrosoftAppId** et **MicrosoftAppPassword** from the **Developer app** on **Teams**.

But first, let’s finish to setup our Bot, in the Endpoint address field, type the following URL:

```text
https://<your subdomain>.loca.lt/api/messages
```

![](https://files.readme.io/ed6d3f7-CleanShot_2022-08-18_at_21.45.39.png)

Click on **Save**

To generate the **MicrosoftAppPassword**, click on Client secrets on the left:

![](https://files.readme.io/08f7bbe-CleanShot_2022-08-18_at_21.49.01.png)

Then click on **Add a client secret for your bot**:

![](https://files.readme.io/a6c6098-CleanShot_2022-08-18_at_21.49.49.png)

Copy the generated secret and paste it in your .env.template for the **MicrosoftAppPassword** value.

For the **MicrosoftAppId**, go back to the previous screen:

![](https://files.readme.io/bff5b40-CleanShot_2022-08-18_at_21.52.46.png)

and copy the Bot ID

![](https://files.readme.io/69bf74a-CleanShot_2022-08-18_at_21.52.06.png)

Paste the id in your **.env.template** for the **MicrosoftAppId.**

## 3. Linking the Bot to our Teams App

Go back to the **Apps** tab and click on the **app** you’ve created

![](https://files.readme.io/eecffc3-CleanShot_2022-08-18_at_21.54.41.png)

From the **left panel**, click on **App features** and select **Bot** in the **App features** list:

![](https://files.readme.io/6fc7714-CleanShot_2022-08-18_at_20.02.49.png)

![](https://files.readme.io/c178dd2-CleanShot_2022-08-18_at_22.01.43.png)

Select your **bot**, check the **last 3 boxes** and click on **Save**

The Teams setup is done, you will be able to Publish your App to your Org store when you will be ready and/or on a production stage.

![](https://files.readme.io/e5ed5fd-CleanShot_2022-08-18_at_22.05.58.png)

## 4. Test locally

You are ready to test your bot, rename the .env.template to .env and launch the node app.

```shell
npm test
```

he console should give the following output:

![](https://files.readme.io/29227b5-CleanShot_2022-08-18_at_22.25.58.png)

Microsoft share a test tool to help you debugging your Bot, to start testing, download the version for your platform here:

```text
https://github.com/microsoft/BotFramework-Emulator/releases
```

Install the **Bot Framework Emulator** and open it to create a **Bot configuration**

![](https://files.readme.io/0bba566-CleanShot_2022-08-18_at_22.11.12.png)

For the endpoint URL, we are testing locally so use (edit the port if you choose another one):

```
http://localhost:3978/api/messages
```

Use the Application Id and Password (secret) info from your .env file

![](https://files.readme.io/7e64852-CleanShot_2022-08-18_at_22.14.57.png)

Give the test bot a name and save your configuration.

Congratulations, you are now able to test your bot in the tool and/or Teams!

![](https://files.readme.io/8a50707-CleanShot_2022-08-18_at_22.23.19.png)

![](https://files.readme.io/5663f09-CleanShot_2022-08-18_at_22.27.03.png)
