---
title: Twilio SMS [Legacy]
excerpt: Connect Voiceflow to Twilio SMS
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
> 🚧 Changes to Twilio SMS projects
>
> On November 8th, 2023, you will no longer be able to create a Twilio SMS project type on Voiceflow. Existing Twilio SMS projects will continue to be supported. We recommend utilizing our [Dialog API](https://developer.voiceflow.com/reference/stateinteract-1) to integrate with this channel.

# Get started

Twilio is a cloud communications platform that allows companies to easily send and receive text messages programmatically. By using Twilio SMS, companies can automate these types of communications and reach a large number of people quickly and efficiently. Additionally, Twilio SMS provides a variety of features such as delivery tracking, logging and compliance that make it easy for companies to scale their messaging operations.

![](https://files.readme.io/eb32dc6-2023-01-10_20-11-23.2023-01-10_20_28_58.gif)

Whether you only want to prototype your assistant through SMS or launch it to all of your users, both paths are available as part of this integration.

> 📘 Prerequisites
>
> Before starting the integration, you will need the following:
>
> 1. A Twilio account
> 2. A Twilio phone number
> 3. A Twilio messaging service

This integration guide will provide you with the steps and information needed to integrate your assistant with SMS. 

# Create a Twilio SMS assistant

First, you will need to:

1. Select Create Project
2. Give your assistant a name and select the *Launch and Host* project type
3. Select *Channel* -> *Twilio SMS*
4. Select the language of your assistant
5. Click *Create*

![](https://files.readme.io/1fde668-Screen_Shot_2023-01-10_at_8.59.21_AM.png)

# Test through SMS

To test your SMS assistant before taking it to production, you can take advantage of our SMS sandbox. 

First, select the *Test via SMS* button from the *Run* dropdown. 

![](https://files.readme.io/c77e6e6-Screen_Shot_2023-01-10_at_8.59.49_AM.png)

Add your phone number and select **Add Number & Test**.

![](https://files.readme.io/3464dfa-Screen_Shot_2023-01-10_at_9.00.21_AM.png)

Once the model has completed training, you should receive an outbound message from the Voiceflow number similar to below with the name of your assistant that is connected:

![](https://files.readme.io/b339530-Screen_Shot_2023-01-10_at_9.09.04_AM.png)

Continue to make changes to your assistant design and test again by selecting the *Test via SMS* option.

# Launch on Twilio SMS

> 📘
>
> *To connect your assistant to Twilio, you will be connecting to a Twilio messaging service where you phone numbers are assigned. For more information about how to setup a Twilio messaging service, see[here](https://support.twilio.com/hc/en-us/articles/223181308-Getting-started-with-Messaging-Services).*

You’ll need to gather your Twilio account SID and API key.

First, navigate to the *Integration* page of your assistant (shortcut: 4) as shown below. Here you will be adding your credentials that we will be going over in the next steps.

![](https://files.readme.io/3c2b47b-Screen_Shot_2023-01-10_at_9.11.45_AM.png)

## Retrieve Account SID and API key

Login to your Twilio console. In the Account Info box you’ll see your Account SID. Make a note of it as you’ll be adding this to integration page.

![](https://files.readme.io/2a41828-Screen_Shot_2023-01-10_at_7.44.43_PM.png)

Next, you will need to retrieve an API key SID and Secret. Navigate to the [API key management page](https://www.twilio.com/console/project/api-keys). Click the blue *Create API key* button to create a new key. Make sure the type is set to Standard.

![](https://files.readme.io/c7aa94e-Screen_Shot_2023-01-10_at_7.39.50_PM.png)

Note your API key **SID** and **secret** to add to the Voiceflow integration page. 

## Select a Twilio Messaging Service

With the Account SID and API key, you're ready to complete the integration. Once your credentials have been added, you will be able to select a messaging service from the dropdown. In this case, we have selected the service named *SMS Demo*. 

![](https://files.readme.io/a160d1b-Screen_Shot_2023-01-10_at_7.18.27_PM.png)

NOTE: Messaging services without any numbers associated with it will be greyed out with an error symbol. If you would like to connect your Voiceflow assistant to one of these services, you will be required to add at least one number to the service from the Twilio console. 

![](https://files.readme.io/51a9617-Screen_Shot_2023-01-10_at_7.17.21_PM.png)

Once you've successfully selected an applicable messaging service, you're ready to complete the integration by publishing your assistant. 

## Publish

Final step is to navigate back to the canvas and select *Publish*. If successful, you will see the Successfully Published modal appear as shown below. 

![](https://files.readme.io/b9b2617-Screen_Shot_2023-01-10_at_7.18.58_PM.png)

You can make sure the integration worked by going to the selected messaging channel in Twilio and validate that the Voiceflow webhook is now displayed as a callback URL. 

![](https://files.readme.io/11f1bae-Screen_Shot_2023-01-10_at_8.52.09_PM.png)

Now whenever you are ready to update your production version of your assistant, simply select the **Publish** button and it will be available for all your users to have a conversation with.
