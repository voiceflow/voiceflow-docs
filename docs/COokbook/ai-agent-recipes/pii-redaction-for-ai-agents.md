---
title: PII redaction for AI Agents
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: PII redaction for AI Agents with Microsoft Presidio
  description: >-
    PI stands for Personally information. Examples include, name, phone number,
    address, email and many other pieces of information. PI redaction is a way
    to limit which data is stored in a system providing an additional layer of
    security. When many pieces of Personal information are obtained, they become
    PII, or Personally Identifiable information. PII can be used to uniquely
    identify a person, for example combining address, first and last name.
  image: https://files.readme.io/4c58892-Subtle_Logo.png
  keywords:
    - PII
    - ' ai'
    - ' personal'
    - ' information'
    - ' Presidio'
    - ' docker'
    - ' api'
  robots: index
next:
  description: ''
---
## Intro

In this video, we will review and explain how to use Presidio to redact PII within your Voiceflow AI Agent.

### What is PII

PII stands for Personal Identifiable Information. Examples include, name, phone number, address, email and many other pieces of information. PII redaction is a way to limit which data is stored in a system providing an additional layer of security. When many pieces of Personal information are obtained, they become PII, or Personally Identifiable information. PII can be used to uniquely identify a person, for example combining address, first and last name.

### Redacting PI and PII

There are different options for redaction. In the cookbook we show full redaction and partial redaction.

`Bob Joe -> {First Name} {Last Name}` is one way to anonymize by fully redacting the properties but leaving their type intact.

`123-456-7890 -> ***-***-7890` is another way by keeping some information for verification purposes.

From a API perspective it can look like this:

```json json
//request
{
	"text":"John Smith phone number is +33123456789"
}
//The response will contain the anonymized text:

  {
	"text": "<PERSON> phone number is <PHONE_NUMBER>",
	"items": [
		{
			"start": 25,
			"end": 39,
			"entity_type": "PHONE_NUMBER",
			"text": "<PHONE_NUMBER>",
			"operator": "replace"
		},
		{
			"start": 0,
			"end": 8,
			"entity_type": "PERSON",
			"text": "<PERSON>",
			"operator": "replace"
		}
	]
}
```

<br />

## Guide

See below for the full tutorial.

<Embed url="https://www.youtube.com/watch?v=CKIoCGraulM" title="Data Protection and De-identification in your Voiceflow assistant using Microsoft Presidio" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/CKIoCGraulM/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=CKIoCGraulM" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FCKIoCGraulM%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DCKIoCGraulM%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FCKIoCGraulM%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## Github link

Follow along with the content on our [github page ](https://github.com/voiceflow-gallagan/presidio-api)
