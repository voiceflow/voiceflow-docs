---
title: Microsoft Teams
excerpt: Connect Voiceflow to Microsoft Teams
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
> 👍 This integration is currently in beta

> This integration is free-to-use while it is in beta.

# Get started

Microsoft Teams is a collaboration platform that brings together chat, video meetings, file storage, and integration with other applications in one place. It is designed to help teams stay organized, share information, and communicate more effectively. With Microsoft Teams, you can create a team for your project, department, or organization, and invite members to join.

![](https://files.readme.io/df2c893-2023-01-03_16-07-22.2023-01-03_16_08_45.gif)

This integration guide will provide you with the steps and information needed to integrate your assistant with Microsoft Teams.

> 📘 Prerequisites

> Before starting the integration, you will need the following:

> 1. A Microsoft Teams account
> 2. A new Microsoft Team App: [Setup Guide](https://learn.microsoft.com/en-us/microsoftteams/platform/concepts/build-and-test/teams-developer-portal)

## Create a Microsoft Teams assistant

First, you will need to:

1. Select Create Project
2. Give your assistant a name and select the Launch and Host project type
3. Select Channel -> Microsoft Teams
4. Select the language of your assistant
5. Click Create

![](https://files.readme.io/e63ded1-Screen_Shot_2023-01-03_at_4.19.35_PM.png)

Once created, you can begin working on your assistant design.

## Setting up the bot

First thing to do is go ahead and connect your assistant to a Microsoft bot. To do this, you will need a retrieve both a:

- Bot ID; and
- Client Secret.

In the Microsoft Developer portal:

1. Visit the **Tools** tab

2. Open the **Bot management** tool

   ![](https://files.readme.io/3df68c8-Screen_Shot_2023-01-03_at_12.13.34_PM.png)

3. Inside Bot management, click on **“+ New Bot”**

   ![](https://files.readme.io/3cc2d38-Screen_Shot_2023-01-03_at_12.13.46_PM.png)

4. Enter a bot name and click **Add**

   ![](https://files.readme.io/a956f49-Screen_Shot_2023-01-03_at_12.13.59_PM.png)

5. Inside the bot’s page, visit the “Client secrets” section

6. Click **“Add a client secret for your bot”**

7. Copy the client secret from the **“New client secret generated”** modal

8. Return to the Bot management tool and copy the Bot ID of your bot.

9. Visit Voiceflow > Integrations > Microsoft Teams and insert the **Bot ID** and **Client Secret** that you copied earlier, then click Save

   ![](https://files.readme.io/0298d2a-Screen_Shot_2023-01-03_at_12.14.56_PM.png)

10. In Voiceflow > Integrations > Microsoft Teams, copy the Webhook URL

11. In Microsoft Teams > Tools > Bot Management > “Hello Voiceflow Bot” page > Configure, paste the Webhook URL into the Endpoint address field and click Save

    ![](https://files.readme.io/751c11c-Screen_Shot_2023-01-03_at_2.51.01_PM.png)

## Connecting the Bot to the Application

1. In Microsoft Teams > Apps, select your app and open Configure > App features

   ![](https://files.readme.io/aba55a6-Screen_Shot_2023-01-03_at_12.49.22_PM.png)

2. **Click** the “Bot” app feature to add a Bot app feature to this application

3. In the Bot app feature page, you should Select an existing bot and select the bot you want use

   ![](https://files.readme.io/0b7dece-Screen_Shot_2023-01-03_at_4.50.40_PM.png)

4. Select the scopes that you want to support, in this case, select all of them for demonstration.

5. **Click** the “Save” button

   ![](https://files.readme.io/0d541d5-Screen_Shot_2023-01-03_at_12.44.55_PM.png)

## Submit the application

1. Open Apps > Select your App > Publish > Publish to Org

   ![](https://files.readme.io/db89865-Screen_Shot_2023-01-03_at_12.51.12_PM.png)

2. Click Publish your app, this will submit the application to your IT admin for approval. Once it is successfully submitted, the “Publish› to your org” page should look like this:

   ![](https://files.readme.io/243d4f4-Screen_Shot_2023-01-03_at_12.51.21_PM.png)

## Approve the application

The following steps require admin privileges on Microsoft Teams. Microsoft implies that this role should be assigned to the organization’s IT admin.

1. Visit the Microsoft Teams admin center: [https://admin.teams.microsoft.com/](https://admin.teams.microsoft.com/)

2. Sign in with a Microsoft Teams admin account

3. Goto Teams apps > Manage apps

   ![](https://files.readme.io/6c82532-Screen_Shot_2023-01-03_at_12.59.59_PM.png)

4. Filter the list by clicking on the Publishing status column

   ![](https://files.readme.io/36ba80b-Screen_Shot_2023-01-03_at_1.31.10_PM.png)

5. Find your application in the list, e.g, “Hello Voiceflow”. If you’ve successfully submitted the application as per the previous instructions, you should see “Publishing status” as “Submitted” for your application

   ![](https://files.readme.io/bda2613-Screen_Shot_2023-01-03_at_1.31.34_PM.png)

6. Click on your application in the list

7. In Teams apps > Manage apps > Hello Voiceflow, click Publish to complete the publishing process.– 1. The publishing process takes some time until the changes come into effect, e.g, 1-2 minutes, while the admin centre remarks that sometimes updates can take hours.

   ![](https://files.readme.io/a72feca-Screen_Shot_2023-01-03_at_1.31.53_PM.png)

## Downloading the Application

1. Navigate to the Apps tab and search for your application

   1. NOTE - It can take 1-2 minutes before this application shows up on the Apps page.

      ![](https://files.readme.io/7c6490a-Screen_Shot_2023-01-03_at_1.39.11_PM.png)

2. Click the “Hello Voiceflow” app card

3. Click the Add button in the modal that pops up. This will download the applications for your team.

   ![](https://files.readme.io/ab59c8d-Screen_Shot_2023-01-03_at_1.39.17_PM.png)

4. After adding the App, you will land in a 1-on-1 chat with the bot. You can now interact with the bot like a normal Voiceflow project.

   ![](https://files.readme.io/43a066d-Screen_Shot_2023-01-03_at_1.39.25_PM.png)

## Using the application

There are different “scopes” where you can use a Teams application. As mentioned earlier in the setup, you can configure which scopes can you use the Teams app.

### Teams-scoped chat

1. Open the Teams section on MS Teams to visit the Teams-scoped conversations

2. Select any Team on the left sidebar

   ![](https://files.readme.io/919f1c0-Screen_Shot_2023-01-03_at_1.39.37_PM.png)

3. Interact with the bot by using @My Bot Name &lt;my-message&gt;, e.g, @Hello Voiceflow this is my message

   ![](https://files.readme.io/9fe1203-Screen_Shot_2023-01-03_at_1.39.42_PM.png)

### Personal-scoped chat

1. Open the Chat section to enter the personal-scoped chat

   ![](https://files.readme.io/13f59b9-Screen_Shot_2023-01-03_at_1.39.50_PM.png)

2. Click this icon to create a new 1-on-1 chat

   ![](https://files.readme.io/299474c-Screen_Shot_2023-01-03_at_1.39.56_PM.png)

3. Under the To: field enter the name of your application and click on it. This will spawn a new 1-on-1, personal chat with your application

   ![](https://files.readme.io/af5be28-Screen_Shot_2023-01-03_at_1.40.14_PM.png)

4. Interact with the chatbot as you would with a normal Voiceflow project

   ![](https://files.readme.io/e202b5c-Screen_Shot_2023-01-03_at_1.40.30_PM.png)

### Group-scoped chat

1. Goto Apps and search for your application

   ![](https://files.readme.io/e32907b-Screen_Shot_2023-01-03_at_1.58.36_PM.png)

2. Click on your application’s card

3. Click the arrow next to Open and select Add to a chat

   ![](https://files.readme.io/c6e57f9-Screen_Shot_2023-01-03_at_1.58.43_PM.png)

4. Add a name for the new group chat and confirm clicking Set up a bot

   ![](https://files.readme.io/6097fa0-Screen_Shot_2023-01-03_at_1.58.54_PM.png)

5. Interact with the bot by using @Hello Voiceflow &lt;my-message&gt;

   ![](https://files.readme.io/057f16c-Screen_Shot_2023-01-03_at_1.59.04_PM.png)