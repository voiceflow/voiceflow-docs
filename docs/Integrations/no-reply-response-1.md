---
title: No Reply Response
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
When the user gives no response at all - remaining silent or away from keyboard - we can use no reply feature. Under any "User Input" type step, there is an option to "Add No Reply Response" and designate a timeout period.

![Screen Shot 2021-12-02 at 11 29 26 AM](https://user-images.githubusercontent.com/5643574/144462791-b8e0f8bf-626e-453d-9dfb-78b0006ceaed.png)

To handle interactions within the Dialog Manager API, we can reference the `no-reply` trace:

```
trace: [
  ...otherTraces,
  {
    type: "no-reply",
    payload: {
      timeout: 5
    }
  }
]
```

The responsibility of handling this is on your client calling the API. This would require a timer function of some kind that detects if the user has not responded within the `timeout` number of seconds. In which case, the next `request` is simply `null` to denote that the user has no replied, and the API will handle the following logic:

```
{
  action: {
    type: "no-reply" //  BaseRequest.RequestType.NO_REPLY
  },
  // state, config, and other metadata here
}
```