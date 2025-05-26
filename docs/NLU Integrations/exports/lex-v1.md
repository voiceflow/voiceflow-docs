---
title: Lex V1
excerpt: Learn how to use our NLU export with Lex V1
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Quick Reference

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Data
      </th>

      <th style={{ textAlign: "left" }}>
        Support
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        File format
      </td>

      <td style={{ textAlign: "left" }}>
        JSON
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **Data Support**
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Intents
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Training Phrases
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Entities
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Synonyms
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **Import Type** 
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Modify
      </td>

      <td style={{ textAlign: "left" }}>
        ❌
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Overwrite
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>
  </tbody>
</Table>

## Video Walkthrough

<Embed url="https://www.youtube.com/watch?v=1ehfNl_C-Xg&feature=youtu.be" title="Voiceflow NLU Export: Lex V1" favicon="https://www.youtube.com/s/desktop/bd4478ba/img/favicon.ico" image="https://i.ytimg.com/vi/1ehfNl_C-Xg/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=1ehfNl_C-Xg&feature=youtu.be" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252F1ehfNl_C-Xg%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253D1ehfNl_C-Xg%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252F1ehfNl_C-Xg%252Fhqdefault.jpg%26key%3Df2aa6fc3595946d0afc3d76cbbd25dc3%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## Sample Intent Export

```json spell_intent.json
{
   "metadata":{
      "schemaVersion":"1.0",
      "importType":"LEX",
      "importFormat":"JSON"
   },
   "resource":{
      "name":"spell_intent",
      "description":"",
      "fulfillmentActivity":{
         "type":"ReturnIntent"
      },
      "sampleUtterances":[
         "sure {spell}",
         "its {spell}",
         "{spell}",
         "it's {spell}",
         "word is {spell}",
         "the word is {spell}"
      ],
      "slots":[
         {
            "name":"spell",
            "sampleUtterances":[
               "its {spell}",
               "it's written {spell}",
               "the word is {spell}",
               "it's {spell}",
               "{spell}"
            ],
            "slotType":"spell",
            "obfuscationSetting":"NONE",
            "description":"spell",
            "slotConstraint":"Optional",
            "valueElicitationPrompt":{
               "messages":[
                  {
                     "contentType":"PlainText",
                     "content":"Sorry I didn't get that. Can you say that again? "
                  }
               ],
               "maxAttempts":2
            },
            "priority":1
         }
      ],
      "slotTypes":[
         {
            "name":"spell",
            "enumerationValues":[
               {
                  "value":"DOG",
                  "synonyms":[
                     "d. o. g.",
                     "d o g"
                  ]
               },
               {
                  "value":"CAR",
                  "synonyms":[
                     "c. a. r.",
                     "c a r"
                  ]
               },
               {
                  "value":"HOUSE",
                  "synonyms":[
                     "h. o. u. s. e.",
                     "h o u s e"
                  ]
               },
               {
                  "value":"ROCK",
                  "synonyms":[
                     "r. o. c. k.",
                     "r o c k"
                  ]
               },
               {
                  "value":"PIZZA",
                  "synonyms":[
                     "p. i. z. z. a.",
                     "p i z z a"
                  ]
               },
               {
                  "value":"FRIDGE",
                  "synonyms":[
                     "f. r. i. d. g. e.",
                     "f r i d g e"
                  ]
               }
            ],
            "valueSelectionStrategy":"TOP_RESOLUTION"
         }
      ]
   }
}
```
