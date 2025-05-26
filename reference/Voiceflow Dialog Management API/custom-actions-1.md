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
### Overview

The **Custom Action step** allows you to perform any kind of integration to a Voiceflow project.

![](https://files.readme.io/3f13d52-Screenshot_2023-02-27_at_5.06.36_PM.png)

A Custom Action step is similar to an event handler. A Voiceflow application can be commanded to stop on a Custom Action step and wait for your client application to send back an event, a Custom Action request, telling the Voiceflow diagram which logic it should execute next.

Before sending back this event, your client application can perform a variety of tasks including, but not limited to:

1. Triggering navigation on your website
2. Processing a credit card payment
3. Opening the windows on a car
4. Handing off the call to a human

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

Ensure that the "Stop on action" is option checked in the editor of the Custom Action step.

![](https://files.readme.io/b9fc2ca-Screenshot_2023-02-27_at_5.05.39_PM.png)

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



Finally, the client application should send an appropriate response based on the results of the logic in step 3. For example, if the Stripe API reported that the user's credit card was successfuly charged, we might send back the following:

```json
{
  "action": { "type": "success" }
}
```



where a value of `"success"` for `type` might indicate that your Voiceflow diagram should execute the logic corresponding to a successful credit card payment. Your diagram might then print a confirmation message such as "your order was successful!".

If the `type` field is not one of the path names of your Custom Action (`"success"`, `"denied"`, or `"pending"` in this case), the Custom Action will behave as though it was a "dead-end" block with no lines connecting to other blocks.