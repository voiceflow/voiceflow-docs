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
        Slots
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

## Sample Export

```json voice_project.json
{
   "interactionModel":{
      "dialog":{
         "delegationStrategy":"ALWAYS",
         "intents":[
            {
               "name":"AMAZON.StopIntent",
               "prompts":{
                  
               },
               "confirmationRequired":false,
               "slots":[
                  
               ]
            }
         ]
      },
      "languageModel":{
         "intents":[
            {
               "name":"AMAZON.RepeatIntent"
            },
            {
               "name":"AMAZON.FallbackIntent",
               "samples":[
                  
               ]
            },
            {
               "name":"Number",
               "samples":[
                  "I want to learn about the number intent",
                  "Number intent please",
                  "I want to test the number intent",
                  "Test the number intent",
                  "I want to test number intent",
                  "What about the number intent",
                  "I want to know about number intent",
                  "Show me number intent",
                  "Number please",
                  "Number",
                  "Number intent",
                  "Activate number intent",
                  "I want to activate the number intent"
               ]
            },
            {
               "name":"Email",
               "samples":[
                  "I want to learn about e-mail",
                  "Email intent please",
                  "I want to test email intent",
                  "I want to know about email intent",
                  "Email intent",
                  "Email please",
                  "I want to activate the email intent",
                  "Activate email intent",
                  "Show me the email intent",
                  "What about the email intent",
                  "Test the email intent",
                  "I want to test the email intent",
                  "Email"
               ]
            },
            {
               "name":"Phonenumber",
               "samples":[
                  "I want to learn about the phone number",
                  "Phone number intent please",
                  "I want to test the phone number intent",
                  "What about the phone number intent",
                  "Phone number intent",
                  "Phone number please",
                  "Show me phone number intent",
                  "I want to test phone number intent",
                  "Test the phone number intent",
                  "I want to activate phone number",
                  "Activate phone number",
                  "Phone",
                  "Mobile",
                  "Phone number"
               ]
            },
            {
               "name":"Custom",
               "samples":[
                  "I want to learn about a custom intent",
                  "Custom intent please",
                  "I want to test the custom intent",
                  "I want to know about custom intent",
                  "What about the custom intent",
                  "Custom intent",
                  "Custom please",
                  "I want to test custom intent",
                  "Test the custom intent",
                  "Show me the custom intent",
                  "I want to activate the custom intent",
                  "Activate custom intent",
                  "Custom"
               ]
            },
            {
               "name":"AMAZON.YesIntent",
               "samples":[
                  "yes",
                  "yea",
                  "ok",
                  "okay",
                  "yup",
                  "ya",
                  "sure"
               ]
            },
            {
               "name":"AMAZON.NoIntent",
               "samples":[
                  "no",
                  "nope",
                  "nay",
                  "nah",
                  "no way",
                  "negative"
               ]
            },
            {
               "name":"AMAZON.StopIntent",
               "samples":[
                  
               ]
            }
         ],
         "invocationName":"intent step component",
         "modelConfiguration":{
            "fallbackIntentSensitivity":{
               "level":"LOW"
            }
         }
      }
   }
}
```
