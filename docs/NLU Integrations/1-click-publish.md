---
title: Dialogflow ES
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
Connect your Voiceflow **chat** project into Dialogflow ES with our _One-Click Publish_ feature. In this guide, we will take you through the entire workflow to get your project setup with your agent.

Instructions
------------

To get started, create a New Project and select the **Dialogflow Chat** project type under the _One-Click Publish_ section.

![](https://files.readme.io/0987ec7-Screen_Shot_2022-02-28_at_10.57.42_AM.png "Screen Shot 2022-02-28 at 10.57.42 AM.png")

Next, go ahead and create an intent with some example utterances.

![](https://files.readme.io/8149705-Screen_Shot_2022-02-28_at_10.59.43_AM.png "Screen Shot 2022-02-28 at 10.59.43 AM.png")

Now that you've setup your intents, create a design that includes the intent in a step.

> 🚧 Active intents only
> 
> The publish tool will only upload active intents and their associated entities (those used in the design).

![](https://files.readme.io/ef1a686-Screen_Shot_2022-02-28_at_11.27.56_AM.png "Screen Shot 2022-02-28 at 11.27.56 AM.png")

Connect your Dialogflow instance to the project by following the sign-in steps.

![](https://files.readme.io/d5faebb-Screen_Shot_2022-02-28_at_10.59.56_AM.png "Screen Shot 2022-02-28 at 10.59.56 AM.png")

Select the Agent you want to connect to or create a new agent.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e938de3-Screen_Shot_2022-03-01_at_8.36.06_AM.png",
        "Screen Shot 2022-03-01 at 8.36.06 AM.png",
        604
      ],
      "sizing": "80"
    }
  ]
}
[/block]

You will receive the below prompt on successful upload.

![](https://files.readme.io/7e766e1-Screen_Shot_2022-02-28_at_11.00.59_AM.png "Screen Shot 2022-02-28 at 11.00.59 AM.png")

To confirm everything worked correctly, navigate to the _Intent_ tab in Dialogflow and make sure that all your active intents are listed with their associated training phrases. 

![](https://files.readme.io/17a7d81-Screen_Shot_2022-02-28_at_11.21.42_AM.png "Screen Shot 2022-02-28 at 11.21.42 AM.png")

Notice that '_Enable webhook call for this intent_' and '_Enable webhook call for slot filling_' are marked as on by default so that your agent can interface directly with your Voiceflow design.

![](https://files.readme.io/a17ffe4-Screen_Shot_2022-02-28_at_11.24.22_AM.png "Screen Shot 2022-02-28 at 11.24.22 AM.png")

Finally, confirm that all of your entities (if used in your intent utterances) with their related synonyms are also reflected. 

![](https://files.readme.io/7e03501-Screen_Shot_2022-02-28_at_11.22.32_AM.png "Screen Shot 2022-02-28 at 11.22.32 AM.png")

Congrats, your project is now connected with your Dialogflow ES agent!

> 🚧 Disconnect Dialogflow from Voiceflow
> 
> If you're interested in managing context independently, you can remove the fulfilment webhook at any time to disconnect your agent from Voiceflow.