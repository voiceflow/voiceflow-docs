---
title: Dialogflow ES
excerpt: Learn how to use our NLU export with your Dialogflow ES agent
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
        ✅
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

<Embed url="https://www.youtube.com/watch?v=yPTcxVKLoxk&feature=youtu.be" title="Voiceflow NLU Export: Dialogflow ES" favicon="https://www.youtube.com/s/desktop/f03577db/img/favicon.ico" image="https://i.ytimg.com/vi/yPTcxVKLoxk/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=yPTcxVKLoxk&feature=youtu.be" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FyPTcxVKLoxk%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DyPTcxVKLoxk%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FyPTcxVKLoxk%252Fhqdefault.jpg%26key%3Df2aa6fc3595946d0afc3d76cbbd25dc3%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## Sample Intent Export

```json place_order.json
{
  "id": "9220ea61-ff17-446b-a371-e62ca8eb47c1",
  "name": "place_order",
  "auto": true,
  "contexts": [],
  "responses": [
    {
      "resetContexts": false,
      "action": "",
      "affectedContexts": [],
      "parameters": [
        {
          "id": "7d93c35b-1170-4b19-abe7-9f781dbecab8",
          "name": "sandwich",
          "required": true,
          "dataType": "@sandwich",
          "value": "$sandwich.original",
          "defaultValue": "",
          "isList": false,
          "prompts": [
            {
              "value": "What kind of burger would you like?",
              "lang": "en"
            }
          ],
          "promptMessages": [],
          "noMatchPromptMessages": [],
          "noInputPromptMessages": [],
          "outputDialogContexts": []
        },
        {
          "id": "8291a742-b860-4e33-a1b6-22ac4a282a03",
          "name": "side",
          "required": true,
          "dataType": "@side",
          "value": "$side.original",
          "defaultValue": "",
          "isList": false,
          "prompts": [
            {
              "value": "What side did you want?",
              "lang": "en"
            }
          ],
          "promptMessages": [],
          "noMatchPromptMessages": [],
          "noInputPromptMessages": [],
          "outputDialogContexts": []
        },
        {
          "id": "b0f60489-00b4-4eaa-9c11-9a41e38db822",
          "name": "drink",
          "required": true,
          "dataType": "@drink",
          "value": "$drink.original",
          "defaultValue": "",
          "isList": false,
          "prompts": [
            {
              "value": "<prosody rate=\"fast\">What drink?</prosody>",
              "lang": "en"
            }
          ],
          "promptMessages": [],
          "noMatchPromptMessages": [],
          "noInputPromptMessages": [],
          "outputDialogContexts": []
        }
      ],
      "messages": [],
      "speech": []
    }
  ],
  "priority": 500000,
  "webhookUsed": true,
  "webhookForSlotFilling": true,
  "fallbackIntent": false,
  "events": [],
  "conditionalResponses": [],
  "condition": "",
  "conditionalFollowupEvents": []
}
```
