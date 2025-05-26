---
title: Amazon Alexa
excerpt: Learn how to use our NLU export with Amazon Alexa
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
[block:api-header]
{
  "title": "Quick Reference"
}
[/block]

[block:parameters]
{
  "data": {
    "0-0": "File format",
    "0-1": "JSON",
    "1-0": "**Data Support**",
    "2-0": "Intents",
    "2-1": "✅",
    "3-1": "✅",
    "4-1": "✅",
    "5-1": "✅",
    "3-0": "Training Phrases",
    "4-0": "Slots",
    "5-0": "Synonyms",
    "6-0": "**Import Type** ",
    "7-0": "Modify",
    "7-1": "❌",
    "h-0": "Data",
    "h-1": "Support",
    "8-0": "Overwrite",
    "8-1": "✅"
  },
  "cols": 2,
  "rows": 9
}
[/block]

[block:api-header]
{
  "title": "Sample Export"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "{\n   \"interactionModel\":{\n      \"dialog\":{\n         \"delegationStrategy\":\"ALWAYS\",\n         \"intents\":[\n            {\n               \"name\":\"AMAZON.StopIntent\",\n               \"prompts\":{\n                  \n               },\n               \"confirmationRequired\":false,\n               \"slots\":[\n                  \n               ]\n            }\n         ]\n      },\n      \"languageModel\":{\n         \"intents\":[\n            {\n               \"name\":\"AMAZON.RepeatIntent\"\n            },\n            {\n               \"name\":\"AMAZON.FallbackIntent\",\n               \"samples\":[\n                  \n               ]\n            },\n            {\n               \"name\":\"Number\",\n               \"samples\":[\n                  \"I want to learn about the number intent\",\n                  \"Number intent please\",\n                  \"I want to test the number intent\",\n                  \"Test the number intent\",\n                  \"I want to test number intent\",\n                  \"What about the number intent\",\n                  \"I want to know about number intent\",\n                  \"Show me number intent\",\n                  \"Number please\",\n                  \"Number\",\n                  \"Number intent\",\n                  \"Activate number intent\",\n                  \"I want to activate the number intent\"\n               ]\n            },\n            {\n               \"name\":\"Email\",\n               \"samples\":[\n                  \"I want to learn about e-mail\",\n                  \"Email intent please\",\n                  \"I want to test email intent\",\n                  \"I want to know about email intent\",\n                  \"Email intent\",\n                  \"Email please\",\n                  \"I want to activate the email intent\",\n                  \"Activate email intent\",\n                  \"Show me the email intent\",\n                  \"What about the email intent\",\n                  \"Test the email intent\",\n                  \"I want to test the email intent\",\n                  \"Email\"\n               ]\n            },\n            {\n               \"name\":\"Phonenumber\",\n               \"samples\":[\n                  \"I want to learn about the phone number\",\n                  \"Phone number intent please\",\n                  \"I want to test the phone number intent\",\n                  \"What about the phone number intent\",\n                  \"Phone number intent\",\n                  \"Phone number please\",\n                  \"Show me phone number intent\",\n                  \"I want to test phone number intent\",\n                  \"Test the phone number intent\",\n                  \"I want to activate phone number\",\n                  \"Activate phone number\",\n                  \"Phone\",\n                  \"Mobile\",\n                  \"Phone number\"\n               ]\n            },\n            {\n               \"name\":\"Custom\",\n               \"samples\":[\n                  \"I want to learn about a custom intent\",\n                  \"Custom intent please\",\n                  \"I want to test the custom intent\",\n                  \"I want to know about custom intent\",\n                  \"What about the custom intent\",\n                  \"Custom intent\",\n                  \"Custom please\",\n                  \"I want to test custom intent\",\n                  \"Test the custom intent\",\n                  \"Show me the custom intent\",\n                  \"I want to activate the custom intent\",\n                  \"Activate custom intent\",\n                  \"Custom\"\n               ]\n            },\n            {\n               \"name\":\"AMAZON.YesIntent\",\n               \"samples\":[\n                  \"yes\",\n                  \"yea\",\n                  \"ok\",\n                  \"okay\",\n                  \"yup\",\n                  \"ya\",\n                  \"sure\"\n               ]\n            },\n            {\n               \"name\":\"AMAZON.NoIntent\",\n               \"samples\":[\n                  \"no\",\n                  \"nope\",\n                  \"nay\",\n                  \"nah\",\n                  \"no way\",\n                  \"negative\"\n               ]\n            },\n            {\n               \"name\":\"AMAZON.StopIntent\",\n               \"samples\":[\n                  \n               ]\n            }\n         ],\n         \"invocationName\":\"intent step component\",\n         \"modelConfiguration\":{\n            \"fallbackIntentSensitivity\":{\n               \"level\":\"LOW\"\n            }\n         }\n      }\n   }\n}",
      "language": "json",
      "name": "voice_project.json"
    }
  ]
}
[/block]