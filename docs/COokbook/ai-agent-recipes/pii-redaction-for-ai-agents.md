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

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FCKIoCGraulM%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DCKIoCGraulM&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FCKIoCGraulM%2Fhqdefault.jpg&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=CKIoCGraulM",
  "title": "Data Protection and De-identification in your Voiceflow assistant using Microsoft Presidio",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/CKIoCGraulM/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=CKIoCGraulM",
  "typeOfEmbed": "youtube"
}
[/block]


## Github link

Follow along with the content on our [github page ](https://github.com/voiceflow-gallagan/presidio-api)