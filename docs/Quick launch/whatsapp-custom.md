---
title: WhatsApp (Cloud API)
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
# Get started

#### Use Voiceflow Dialog Manager API to run a Whatsapp assistant

> 🚧 Before you start
> 
> - [Clone project from Github](https://github.com/voiceflow/example-integration-whatsapp)
> - [Whatsapp Cloud API](https://developers.facebook.com/docs/whatsapp/cloud-api/)
> - Install ngrok, more details here: <https://ngrok.com/download>
> - [Voiceflow](https://www.voiceflow.com) **Chat Assistant** project

# Create an app on Facebook Developers portal

Follow the Get started guide here to create your app and get your WhatsApp token:  
<https://developers.facebook.com/docs/whatsapp/cloud-api/get-started>

![](https://files.readme.io/23aa0c2-get-started_1.png)

## The App

Once registered as a dev, go to <https://developers.facebook.com/apps/>

Create a new app by clicking on **Create App**.

Select "**Business**" for app type  and click **Next**.

![](https://files.readme.io/301a010-business-app.png)

Fill the needed info for the app creation  and click **Create app**:

![](https://files.readme.io/4318242-app-info.png)

On the next page, scroll down to the WhatsApp integration and click on **Set up**:

![](https://files.readme.io/20aa553-whatsapp-setup.png)

Create a Business account (or select an existing one)

![](https://files.readme.io/c760db8-business-account.png)

Link an existing number or create a new one:

![](https://files.readme.io/06b0f2e-add-number.png)

You can add your phone number by clicking on Manage phone number list.

Now that you are ready to do a test, simply click on the **Send message** button.

![](https://files.readme.io/a3c3a5d-curl-message.png)

You should get something like this in your **WhatsApp** app:

![](https://files.readme.io/2edfde8-test-message.png)

Last step here, you want to go to the top of the page and click on **Refresh** then **Copy** to copy your token.

![](https://files.readme.io/3002519-get-token.png)

Save it as we will need it in the new step.

# Webhook

Before going further, let's start populating our `.env` file with our token.  
In the root of the app directory, create the `.env` file.  
We are going to populate this file with the needed info for the WhatsApp webhook as well as the Voiceflow project.

```
WHATSAPP_TOKEN = 'EAAQlqaPy54MBAGqxxxxxxxx'
VERIFY_TOKEN = 'voiceflow'
VF_PROJECT_API = ''
VF_PROJECT_VERSION = 'production'
PORT = '3000'
```



For now, you can paste the token for the `WHATSAPP_TOKEN` variable, you can use anything for the `VERIFY_TOKEN` or leave it to 'voiceflow'.

Regarding the port, you can put the value you want, by default the app will use `3000`.

For the `VF_` variables, we will see that a bit later.

Back on our `Getting Started` Facebook Developer page, click on the `Configure webhooks` link in **Step 3**:

![](https://files.readme.io/83e8277-step-3.png)

On this new page, click on **Edit**:

![](https://files.readme.io/5cead5a-edit-webhook.png)

This is where you will need to set your **webhook's callback URL** and your **Verify token**:

![](https://files.readme.io/9e4f8b2-edit-webhook-2.png)

For the **Verify token**, put what you've set in your `.env` file (**voiceflow** by default).  
For the Callback URL, we will need to start the app.

From the root of the directory, start the app with `npm start`.

And if everything work as expected, you should have something similar to this:

![](https://files.readme.io/8e90e3c-app-start.png)

We are listening, let's use ngrok to open this to the world.

In a new terminal, type `ngrok http 3000`.

Replace **3000** with the **PORT** number you want to use.

![](https://files.readme.io/b6e9b05-ngrok-console.png)

Here, the URL you want to copy is the secure one (starting with https).

Almost there, go back to your **Config page**, paste this URL and add the **/webhook** path to it

![](https://files.readme.io/d754cd3-webhook-url.png)

And click on **Verify and save**.

The previous window should close and your webhook set up.

![](https://files.readme.io/c79cf1a-webhook-setup.png)

On your terminal, you should see this message: `WEBHOOK_VERIFIED`

Last step, we want to choose what to receive, and to do so, we need to subscribe to the message event.

Click on **Manage** and, on the new window, **subscribe** to **messages**:

![](https://files.readme.io/89e6244-manage.png)

You should have a config similar to this one:

![](https://files.readme.io/773e286-sub-messages.png)

# Voiceflow Project

So, the webhook is setup, our app is running waiting to get some messages and send them to our Dialog Manager API running your Voiceflow Chat project.

To use the Dialog Manager API with your project, we will need the project API key and, to test it in an easy way, we will create and use the 'production' version.

In Voiceflow Creator, open a Chat project and go to the Integrations:

![](https://files.readme.io/3f23b00-integrations.png)

On the Integrations page, you want to copy the API key

Now, paste it in your .env file for the **VF_PROJECT_API** variable:  
`VF_PROJECT_API='VF.DM.62xxxxxxxxxxxxxxxxxxxxxxx`

Back on Voiceflow Creator, go to the **Designer** view and click on the **Publish** button:

![](https://files.readme.io/0a230a5-publish-button.png)

Set a name (optional) for this version and click on **Publish** to publish this version as the **production** one:

![](https://files.readme.io/a1f0aba-prod.png)

# Testing

**Congratulations**, you are ready to test your Voiceflow project using WhatsApp!

Close your app with **Ctrl+C** (but keep ngrok running in the other terminal) and launch it again with `npm start` so it will use the updated values from the `.env` file.

That's it, start interacting on WhatsApp with your Voiceflow project.

![](https://files.readme.io/e65f032-whatsapp-chat.png)

### Documentation

Cloud API: <https://developers.facebook.com/docs/whatsapp/cloud-api>  
Voiceflow Dialog Manager API: <https://developer.voiceflow.com/reference>  
Project Versioning in Voiceflow: <https://www.voiceflow.com/docs/documentation-project-versioning>