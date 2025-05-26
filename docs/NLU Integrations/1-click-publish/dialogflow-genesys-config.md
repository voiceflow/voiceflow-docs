---
title: Genesys Cloud Configuration
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
In this guide, we will cover how to support the various configuration details required when the caller does not answer on a Genesys telephony integration.

More details on the no response options available [here](https://help.mypurecloud.com/articles/configure-google-cloud-dialogflow-intent-behavior-when-the-caller-does-not-answer/) on the Genesys website.

📞 Handling no response event
-----------------------------

### Dialogflow setup

Follow the instructions to setup your no response events in Dialogflow ES [here](https://help.mypurecloud.com/articles/configure-google-cloud-dialogflow-intent-behavior-when-the-caller-does-not-answer/) . Voiceflow will not modify any events on upload that are set on active intents. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7513401-Screen_Shot_2022-08-05_at_10.30.27_AM.png",
        null,
        "Dialogflow ES events"
      ],
      "caption": "Dialogflow ES events"
    }
  ]
}
[/block]

### Design Best Practise

We recommend the intent with the `GENESYS_INITIAL_NO_INPUT`, `GENESYS_NO_INPUT` and `GENESYS_FINAL_NO_INPUT` event are set as [Commands](https://www.voiceflow.com/tutorials/flows-commands) in your project. This will ensure that they can be triggered at any time without losing context of the current conversation state. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8a9c264-Screen_Shot_2022-08-05_at_2.35.01_PM.png",
        null,
        "Commands Menu"
      ],
      "caption": "Commands Menu"
    }
  ]
}
[/block]

Add your text response in the _Flow_ your command triggers:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/35aa94b-Screen_Shot_2022-08-05_at_2.34.36_PM.png",
        null,
        "Flow triggered by Command"
      ],
      "caption": "Flow triggered by Command"
    }
  ]
}
[/block]

🛑 End Conversation
-------------------

### Dialogflow setup

To set an intent as the _end of conversation_, you will need to configure this on the relevant intents inside Dialoglow. Voiceflow will not modify the end conversation toggle on upload set on active intents.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6d06fa9-Screen_Shot_2022-08-05_at_10.29.52_AM.png",
        null,
        "End of conversation toggle"
      ],
      "caption": "End of conversation toggle"
    }
  ]
}
[/block]

### Design Best Practise

It is recommended to configure all intents that trigger the end of a conversation as global intents in Voiceflow (i.e. not intent scoped to a choice block).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6fa684d-Screen_Shot_2022-08-05_at_1.20.03_PM.png",
        null,
        "escalate flow"
      ],
      "caption": "Intent + Say step"
    }
  ]
}
[/block]