---
title: WhatsApp (Basic)
excerpt: Connect Voiceflow to WhatsApp
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
  pages:
    - type: basic
      slug: advanced-whatsapp
      title: Advanced WhatsApp
---
> 🚧 Changes to WhatsApp projects
>
> On November 8th, 2023, you will no longer be able to create a WhatsApp project type on Voiceflow. Existing WhatsApp projects will continue to be supported. Looking ahead, for customers using this WhatsApp integration, we recommend instead utilizing our [Dialog API ](https://developer.voiceflow.com/reference/stateinteract-1)or a [community-built integration](https://www.voiceflow.com/showcase) to launch to WhatsApp. You can find more information and our advanced integration documentation [here](https://developer.voiceflow.com/docs/advanced-whatsapp).

# Get started

WhatsApp is a powerful communication tool that enables businesses to easily connect with their customers worldwide. With over 1 billion users, WhatsApp offers a simple, secure, and reliable platform for businesses to connect and engage with their audience in real-time. Whether you want to send promotional messages, provide customer support, or keep customers informed about your latest products and services, WhatsApp provides the perfect solution.

<Image align="center" width="90% " src="https://files.readme.io/2406b8b-2022-12-16_12-26-35.2022-12-16_12_34_41.gif" />

For easy integration, Voiceflow has teamed up with our messaging partner, **Twilio**, for easy setup and support for Whatsapp as a hosted channel option for your assistant. 

Whether you only want to prototype your assistant on Whatsapp or launch it to all of your users, both paths are available as part of the integration.

> 📘 Prerequisites
>
> Before starting the integration, you will need the following:
>
> 1. A Twilio account
> 2. A Whatsapp sender
> 3. A Twilio messaging service

This integration guide will provide you with the steps and information needed to integrate your assistant with Whatsapp. 

# Create a WhatsApp assistant

First, you will need to:

1. Select Create Project
2. Give your assistant a name and select the *Launch and Host* project type
3. Select *Channel* -> *Whatsapp*
4. Select the language of your assistant
5. Click *Create*

![](https://files.readme.io/8260b1d-Screen_Shot_2022-12-16_at_12.37.59_PM.png)

Once created, you can begin working on your assistant design. There are two methods to see your assistant working within Whatsapp:

1. Testing
2. Launching

## Test on WhatsApp

To test your Whatsapp assistant before taking it to production, you can take advantage of  our Whatsapp sandbox. 

First, select the *Test on Whatsapp* button from the *Run* dropdown. 

![](https://files.readme.io/a2c367f-Screen_Shot_2022-12-14_at_7.02.46_PM.png)

Add your phone number and select **Add Number & Test**.

![](https://files.readme.io/62602f1-Screen_Shot_2022-12-15_at_2.58.04_PM.png)

Once the model has completed training, you should receive an outbound message from the Voiceflow number similar to below with the name of your assistant that is connected:

<Image align="center" width="90% " src="https://files.readme.io/d3a6841-Screen_Shot_2022-12-16_at_10.22.56_AM.png" />

> 🚧
>
> If you do not receive a message from Voiceflow, you can message your assistant directly by sending a Whatsapp message to **+16802198814**

Continue to make changes to your assistant design and test again by selecting the *Test on Whatsapp* option.

## Launch on WhatsApp

*If you do not have a WhatsApp sender available on Twilio, follow the instructions here to create one:[WhatsApp Self Sign-up](https://www.twilio.com/docs/whatsapp/self-sign-up#:~:text=Create%20a%20WhatsApp%20Sender,-To%20create%20a\&text=Start%20by%20logging%20into%20the,and%20click%20%22Get%20Started%22.).*

To connect your assistant to your Whatsapp sender, you will be adding a webhook to a Twilio messaging service where you Whatsapp senders are assigned. For more information about how to setup a Twilio messaging service, see [here](https://support.twilio.com/hc/en-us/articles/223181308-Getting-started-with-Messaging-Services). 

To start, select the Publish button and Connect to Whatsapp. 

![](https://files.readme.io/55ba219-Screen_Shot_2022-12-16_at_10.26.18_AM.png)

Copy the webhook URL from the integration page.

![](https://files.readme.io/658d1e2-Screen_Shot_2022-12-08_at_9.20.04_AM.png)

Navigate to your Twilio account to add a callback URL to a Twilio messaging service. You will need to do the following:

1. Log in to your Twilio account.
2. In the Twilio Console, navigate to the "Messaging" menu and select the "Services" option.
3. Select the messaging service you want to add a callback URL to.
4. Click on the "Integration" tab.
5. Select the "Send a Webhook" option, and in the "Request URL" field, enter the URL you want to use as your callback URL.
6. Click "Save" to save your changes.
7. Test the callback URL by sending a message to the messaging service and verifying that the callback is triggered and functions properly.

![](https://files.readme.io/681ee0a-Screen_Shot_2022-12-08_at_9.24.31_AM.png)

Once you've confirmed everything is working as expected, next time you select the *Publish* button to push a new version from the Voiceflow canvas, select *I've Already Done This*.

<Image align="center" width="80% " src="https://files.readme.io/fd2c8e3-Screen_Shot_2022-12-16_at_1.17.32_PM.png" />

Now whenever you are ready to update your production version of your assistant, simply select the **Publish** button and it will be available for all your users to interact.
