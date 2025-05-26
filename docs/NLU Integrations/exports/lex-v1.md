---
title: Lex V1 - NLU Model Export
excerpt: Learn how to use our NLU export with Lex V1
deprecated: false
hidden: true
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
    "4-0": "Entities",
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
  "title": "Video Walkthrough"
}
[/block]

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2F1ehfNl_C-Xg%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D1ehfNl_C-Xg&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2F1ehfNl_C-Xg%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=1ehfNl_C-Xg&feature=youtu.be",
  "title": "Voiceflow NLU Export: Lex V1",
  "favicon": "https://www.youtube.com/s/desktop/bd4478ba/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/1ehfNl_C-Xg/hqdefault.jpg"
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
      "code": "{\n   \"metadata\":{\n      \"schemaVersion\":\"1.0\",\n      \"importType\":\"LEX\",\n      \"importFormat\":\"JSON\"\n   },\n   \"resource\":{\n      \"name\":\"spell_intent\",\n      \"description\":\"\",\n      \"fulfillmentActivity\":{\n         \"type\":\"ReturnIntent\"\n      },\n      \"sampleUtterances\":[\n         \"sure {spell}\",\n         \"its {spell}\",\n         \"{spell}\",\n         \"it's {spell}\",\n         \"word is {spell}\",\n         \"the word is {spell}\"\n      ],\n      \"slots\":[\n         {\n            \"name\":\"spell\",\n            \"sampleUtterances\":[\n               \"its {spell}\",\n               \"it's written {spell}\",\n               \"the word is {spell}\",\n               \"it's {spell}\",\n               \"{spell}\"\n            ],\n            \"slotType\":\"spell\",\n            \"obfuscationSetting\":\"NONE\",\n            \"description\":\"spell\",\n            \"slotConstraint\":\"Optional\",\n            \"valueElicitationPrompt\":{\n               \"messages\":[\n                  {\n                     \"contentType\":\"PlainText\",\n                     \"content\":\"Sorry I didn't get that. Can you say that again? \"\n                  }\n               ],\n               \"maxAttempts\":2\n            },\n            \"priority\":1\n         }\n      ],\n      \"slotTypes\":[\n         {\n            \"name\":\"spell\",\n            \"enumerationValues\":[\n               {\n                  \"value\":\"DOG\",\n                  \"synonyms\":[\n                     \"d. o. g.\",\n                     \"d o g\"\n                  ]\n               },\n               {\n                  \"value\":\"CAR\",\n                  \"synonyms\":[\n                     \"c. a. r.\",\n                     \"c a r\"\n                  ]\n               },\n               {\n                  \"value\":\"HOUSE\",\n                  \"synonyms\":[\n                     \"h. o. u. s. e.\",\n                     \"h o u s e\"\n                  ]\n               },\n               {\n                  \"value\":\"ROCK\",\n                  \"synonyms\":[\n                     \"r. o. c. k.\",\n                     \"r o c k\"\n                  ]\n               },\n               {\n                  \"value\":\"PIZZA\",\n                  \"synonyms\":[\n                     \"p. i. z. z. a.\",\n                     \"p i z z a\"\n                  ]\n               },\n               {\n                  \"value\":\"FRIDGE\",\n                  \"synonyms\":[\n                     \"f. r. i. d. g. e.\",\n                     \"f r i d g e\"\n                  ]\n               }\n            ],\n            \"valueSelectionStrategy\":\"TOP_RESOLUTION\"\n         }\n      ]\n   }\n}",
      "language": "json",
      "name": "spell_intent.json"
    }
  ]
}
[/block]