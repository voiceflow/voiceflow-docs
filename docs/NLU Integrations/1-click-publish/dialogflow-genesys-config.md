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

## 📞 Handling no response event

### Dialogflow setup

Follow the instructions to setup your no response events in Dialogflow ES [here](https://help.mypurecloud.com/articles/configure-google-cloud-dialogflow-intent-behavior-when-the-caller-does-not-answer/) . Voiceflow will not modify any events on upload that are set on active intents. 

<Image alt="Dialogflow ES events" src="https://files.readme.io/7513401-Screen_Shot_2022-08-05_at_10.30.27_AM.png">
  Dialogflow ES events
</Image>

### Design Best Practise

We recommend the intent with the `GENESYS_INITIAL_NO_INPUT`, `GENESYS_NO_INPUT` and `GENESYS_FINAL_NO_INPUT` event are set as [Commands](https://www.voiceflow.com/tutorials/flows-commands) in your project. This will ensure that they can be triggered at any time without losing context of the current conversation state. 

<Image alt="Commands Menu" src="https://files.readme.io/8a9c264-Screen_Shot_2022-08-05_at_2.35.01_PM.png">
  Commands Menu
</Image>

Add your text response in the *Flow* your command triggers:

<Image alt="Flow triggered by Command" src="https://files.readme.io/35aa94b-Screen_Shot_2022-08-05_at_2.34.36_PM.png">
  Flow triggered by Command
</Image>

## 🛑 End Conversation

### Dialogflow setup

To set an intent as the *end of conversation*, you will need to configure this on the relevant intents inside Dialoglow. Voiceflow will not modify the end conversation toggle on upload set on active intents.

<Image alt="End of conversation toggle" src="https://files.readme.io/6d06fa9-Screen_Shot_2022-08-05_at_10.29.52_AM.png">
  End of conversation toggle
</Image>

### Design Best Practise

It is recommended to configure all intents that trigger the end of a conversation as global intents in Voiceflow (i.e. not intent scoped to a choice block).

<Image alt="escalate flow" src="https://files.readme.io/6fa684d-Screen_Shot_2022-08-05_at_1.20.03_PM.png">
  Intent + Say step
</Image>
