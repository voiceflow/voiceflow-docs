---
title: Custom Actions
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Overview

The **Custom Action step** allows you to perform any kind of integration to a Voiceflow project. It also allows you to dynamically render Voiceflow chat elements like Carousels, Cards, and Buttons in Voiceflow-built chat interfaces such as the Test Tool, Prototype Tool and Web Chat.

![](https://files.readme.io/3f13d52-Screenshot_2023-02-27_at_5.06.36_PM.png)

## Custom Action step configuration

* **Custom Action name:** the string you enter in this field will be the trace “type” value.
  * To render a default Voiceflow step, use the step’s trace type value. For example, if you want to render a Carousel, the Custom Action name should be “carousel”.
* **Action Body:** the value passed here will be included in the Custom Action trace payload.
  * To render a default Voiceflow step, select “JSON”, and pass the corresponding trace payload in the body.
* **Paths:** the available action paths after the Custom Action is executed. You can set custom paths to navigate your user to the best next step for their conversation.
* **Stop on action:** this toggle determines if the Voiceflow conversation will continue immediately after the Custom Action is executed or if it stops. Enable this setting when you want an action outside of Voiceflow to occur before moving forward (e.g. trigger a live chat handoff, wait for a user to select a Carousel button).
* **Global Listen:** by default, Voiceflow listen steps actively listen for user events only until the event is detected. When this setting is enabled, any of the Custom Action’s elements that can be interacted with will continue to listen for a user event such as a button click; this is useful if you want to allow your user to select a Carousel Button later in a conversation.

Note about user events: the `last_event` system variable will capture the trace of the last user event such as a button selection, carousel button selection, and when an intent is triggered. The type of this is `{ type: string, payload: object | string }`

## Perform actions outside of Voiceflow

A Custom Action step is similar to an event handler. A Voiceflow application can be commanded to stop on a Custom Action step and wait for your client application to send back an event, a Custom Action request, telling the Voiceflow diagram which logic it should execute next.

Before sending back this event, your client application can perform a variety of tasks including, but not limited to:

1. Triggering navigation on your website
2. Processing a credit card payment
3. Opening the windows on a car
4. Handing off the call to a human
5. Render a custom user interface element

### Execution of a Custom Action

Here is how a Custom Action works:

1. Your **user** interacts with your client app, e.g, saying "talk to a human"

2. Your **client** sends an interact request normally, but also specifies the name of Custom Action steps that the Voiceflow diagram should stop on.

3. Our **DM API** executes your diagram normally, but returns early if it encounters one of the Custom Actions specified in Step 1 and sends back a corresponding Custom Action trace, e.g, a `"dial"` type trace defined by your Voiceflow project.

4. Your **client** receives the Custom Action trace. Your code can detect this trace and perform any necessary processing.

5. Your **client** sends a Custom Action request back, e.g, a `"call success"` type request.

6. Our **DM API** follows the path in your diagram chosen by the Custom Action request. It will produce responses as normal, such as a message `"have a great day!"`

7. Your **client** can display the response `"have a great day"` on your application to the user. 

![Custom Action Flow](https://media.voiceflow.com/image/dialog-manager-api-docs/custom-actions-flow.png)

### Example - Stripe Integration

As a concrete example, let's look at how we can implement an integration for Stripe to charge our user's credit cards. 

![Credit Card Custom Action](https://user-images.githubusercontent.com/5643574/115419275-333b7d80-a1c8-11eb-9a70-30398f4c9358.png)

First, on the Voiceflow Creator, add a Custom Action Step to your diagram with the name "Pay Credit Card" and three paths named "success", "denied", and "pending". 

Ensure that the "Stop on action" is option checked in the editor of the Custom Action step. You can also add an Action Body.

![](https://files.readme.io/e0686bd-Screenshot_2023-06-05_at_4.16.44_PM.png)

Then the client app will receive a list of traces in the response as usual, but the last trace will be a Custom Action trace corresponding to the Custom Action step you just defined. 

```json
[
  ...other_traces,
  {
    "type": "Pay Credit Card",
    "payload": "{ 'amount': 25 }",
    "defaultPath": 0,
    "paths": [
      { "event": { "type": "success" } },
      { "event": { "type": "denied" } },
      { "event": { "type": "pending" } }
    ]
  }
]
```

Your client code might extract this last trace, detect that it is a custom "Pay Credit Card" trace, and then perform some logic such as calling the Stripe API to charge your user's credit card. 

```js
const traces = await dmapiInteract({
  "action": { "type": "text", "payload": "hello!" } // any request type here,
  "config": {
    "stopTypes": ["Pay Credit Card"]
  }
});

const customActionTrace = traces[traces.length - 1];

const customActionPayload = JSON.parse(customActionTrace.payload);


if (customActionTrace.type === "Pay Credit Card") {
  const ok = await stripeAPI.chargeUserCreditCard(customActionPayload.amount);

  await dmapiInteract({
    action: {
      type: ok ? "success" : "denied"
    }
  });
} else if (customActionType.trace === "Some Other Custom Action") {
  // do something else
}
```

Finally, the client application should send an appropriate response based on the results of the logic in step 3. For example, if the Stripe API reported that the user's credit card was successfully charged, we might send back the following:

```json
{
  "action": { "type": "success" }
}
```

where a value of `"success"` for `type` might indicate that your Voiceflow diagram should execute the logic corresponding to a successful credit card payment. Your diagram might then print a confirmation message such as "your order was successful!".

If the `type` field is not one of the path names of your Custom Action (`"success"`, `"denied"`, or `"pending"` in this case), the Custom Action will behave as though it was a "dead-end" block with no lines connecting to other blocks.

## Dynamically render Voiceflow steps

Voiceflow steps have corresponding traces, which are in JSON format. Voiceflow-built chat interfaces such as the Test Tool, Prototype Tool and Web Chat can automatically render default Voiceflow chat elements such as the Text Step, Card Step, Carousel, and Buttons based on their traces.

A Custom Action can be useful when you have an API that returns an unknown number of items such as a list of products that you want to render in a Carousel, or a list of order IDs that you want to display as a set of Buttons.

<Embed url="https://www.youtube.com/embed/2V46rOkkprg?si=sdtqLtTAkdYAcVbD" title="" provider="youtube.com" href="https://www.youtube.com/embed/2V46rOkkprg?si=sdtqLtTAkdYAcVbD" typeOfEmbed="youtube" html="%3Ciframe%20width%3D%22100%25%22%20style%3D%22aspect-ratio%3A%2021%20%2F%209%22%20%20src%3D%22https%3A%2F%2Fwww.youtube.com%2Fembed%2F2V46rOkkprg%3Fsi%3DfMhtdl3ezz4-PC3y%22%20title%3D%22YouTube%20video%20player%22%20frameborder%3D%220%22%20allow%3D%22accelerometer%3B%20autoplay%3B%20clipboard-write%3B%20encrypted-media%3B%20gyroscope%3B%20picture-in-picture%3B%20web-share%22%20allowfullscreen%3E%3C%2Fiframe%3E" />
