---
title: Custom Actions (Event Listener)
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
Take advantage of the Custom Action step to allow you Voiceflow project to perform any kind of integration action.

Examples can include triggering navigation your website or app, processing a credit card payment, opening the windows on a car, handing off to a human on a phone call, or anything else your app can support.

Let's take a look at an example Custom Action step where we want to use a third party integration like Stripe for actually charging a credit card:

![](https://files.readme.io/320ef2c-custom-actions.png "custom-actions.png")

In your request body call, you can specify which Custom Actions to stop on in the `config.stopTypes` field:

```json
{
  "action": { "type": "text", "payload": "hello!" } // any request type here,
  "config": {
    "stopTypes": ["Pay Credit Card"]
  }
}
```

This will inform the dialog manager to stop on any `Pay Credit Card` Custom Action, ensuring that the last trace is always the Custom Action. By default, Custom Action steps will always go out the default port, but still leave a trace.

Here's what the Custom Action `trace` for the "Pay Credit Card" block above might look like:

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

Now whenever we come across a `Pay Credit Card` trace, we can actually trigger a side effect such as the Stripe API and perform the action. Depending on the result of that, we can now select which path we want to go down. In the subsequent request body, you simply have to do this:

```json
{
  "action": { "type": "success" }
}
```

Where the `type` of the request is the same as the name of the path you've labelled in Voiceflow. If the next request is an invalid path, your project will simply behave as if there were no lines coming out of the Custom Action step.

The below illustration describes the custom action workflow. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4f671b4-Group_1_1.png",
        "Group 1 (1).png",
        2340
      ],
      "caption": "Custom Action Diagram"
    }
  ]
}
[/block]

In summary, here's what's happening:

1. We send a request saying to stop on our Custom Action
2. We get a response which stopped on it
3. In the next request we specify which path to go down