---
title: Dialogflow ES - NLU Model Export
excerpt: Learn how to use our NLU export with your Dialogflow ES agent
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
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
    "4-0": "Entities",
    "5-0": "Synonyms",
    "6-0": "**Import Type** ",
    "7-0": "Modify",
    "7-1": "✅",
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
  "title": "Video Walkthrough"
}
[/block]

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FyPTcxVKLoxk%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DyPTcxVKLoxk&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FyPTcxVKLoxk%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=yPTcxVKLoxk&feature=youtu.be",
  "title": "Voiceflow NLU Export: Dialogflow ES",
  "favicon": "https://www.youtube.com/s/desktop/f03577db/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/yPTcxVKLoxk/hqdefault.jpg"
}
[/block]

[block:api-header]
{
  "title": "Sample Intent Export"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "{\n  \"id\": \"9220ea61-ff17-446b-a371-e62ca8eb47c1\",\n  \"name\": \"place_order\",\n  \"auto\": true,\n  \"contexts\": [],\n  \"responses\": [\n    {\n      \"resetContexts\": false,\n      \"action\": \"\",\n      \"affectedContexts\": [],\n      \"parameters\": [\n        {\n          \"id\": \"7d93c35b-1170-4b19-abe7-9f781dbecab8\",\n          \"name\": \"sandwich\",\n          \"required\": true,\n          \"dataType\": \"@sandwich\",\n          \"value\": \"$sandwich.original\",\n          \"defaultValue\": \"\",\n          \"isList\": false,\n          \"prompts\": [\n            {\n              \"value\": \"What kind of burger would you like?\",\n              \"lang\": \"en\"\n            }\n          ],\n          \"promptMessages\": [],\n          \"noMatchPromptMessages\": [],\n          \"noInputPromptMessages\": [],\n          \"outputDialogContexts\": []\n        },\n        {\n          \"id\": \"8291a742-b860-4e33-a1b6-22ac4a282a03\",\n          \"name\": \"side\",\n          \"required\": true,\n          \"dataType\": \"@side\",\n          \"value\": \"$side.original\",\n          \"defaultValue\": \"\",\n          \"isList\": false,\n          \"prompts\": [\n            {\n              \"value\": \"What side did you want?\",\n              \"lang\": \"en\"\n            }\n          ],\n          \"promptMessages\": [],\n          \"noMatchPromptMessages\": [],\n          \"noInputPromptMessages\": [],\n          \"outputDialogContexts\": []\n        },\n        {\n          \"id\": \"b0f60489-00b4-4eaa-9c11-9a41e38db822\",\n          \"name\": \"drink\",\n          \"required\": true,\n          \"dataType\": \"@drink\",\n          \"value\": \"$drink.original\",\n          \"defaultValue\": \"\",\n          \"isList\": false,\n          \"prompts\": [\n            {\n              \"value\": \"<prosody rate=\\\"fast\\\">What drink?</prosody>\",\n              \"lang\": \"en\"\n            }\n          ],\n          \"promptMessages\": [],\n          \"noMatchPromptMessages\": [],\n          \"noInputPromptMessages\": [],\n          \"outputDialogContexts\": []\n        }\n      ],\n      \"messages\": [],\n      \"speech\": []\n    }\n  ],\n  \"priority\": 500000,\n  \"webhookUsed\": true,\n  \"webhookForSlotFilling\": true,\n  \"fallbackIntent\": false,\n  \"events\": [],\n  \"conditionalResponses\": [],\n  \"condition\": \"\",\n  \"conditionalFollowupEvents\": []\n}",
      "language": "json",
      "name": "place_order.json"
    }
  ]
}
[/block]