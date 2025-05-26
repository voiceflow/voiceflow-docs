---
title: How to send requests to Voiceflow APIs
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
> 📘 This article is part of a guide on getting started with Voiceflow APIs
>
> Start from the [beginning](https://docs.voiceflow.com/reference/api-guide-start) here.

More specifically, we'll be using the DM API's interact endpoint, that lets us send a request and receive a response from our Voiceflow agent. Requests being sent to the DM API consist of a user\_id and a request payload. 

👉  Add a line to your interact function that sends a post request to the Voiceflow interact endpoint. We're just going to print the response from the API for now.

```python
import requests

api_key = 'YOUR_API_KEY_HERE' # it should look like this: VF.DM.XXXXXXX.XXXXXX... keep this a secret!

# user_id defines who is having the conversation, e.g. steve, john.doe@gmail.com, username_464
def interact(user_id, request):
    response = requests.post(
        f'https://general-runtime.voiceflow.com/state/user/{user_id}/interact',
        json={ 'request': request },
        headers={ 
            'Authorization': api_key,
            'versionID': 'production'
        },
    )
    
    print(response.json())
```
```javascript
const axios = require('axios');

const api_key = 'YOUR_API_KEY_HERE'; // it should look like this: VF.DM.XXXXXXX.XXXXXX... keep this a secret!

// user_id defines who is having the conversation, e.g. steve, john.doe@gmail.com, username_464
const interact = async (user_id, request) => {
    try {
        const response = await axios.post(
            `https://general-runtime.voiceflow.com/state/user/${user_id}/interact`,
            { request: request },
            {
                headers: {
                    'Authorization': api_key,
                    'versionID': 'production',
                    'accept': 'application/json',
                    'content-type': 'application/json'
                }
            }
        );
        
        console.log(response.data);
    } catch (error) {
        console.error('Error interacting with Voiceflow:', error);
    }
};
```

In this request, you'll notice how you include your API key as an Authorization header. This is used to identify which agent we are interacting with, and that you're authorized to. We're also including a versionID alias, that just tell us to use the version that we published above.

As we discussed above, the user\_id is a unique string, but the request payload is a bit more complicated.

There are two important types of payloads you need to know about:

* The **launch** payload is used to **start or reset** the conversation. It's what's sent when you click `Start New Chat` on the web chat widget. In most projects, it's appropriate to automatically send this request when your app starts. Its payload is simply `{ 'type': 'launch' }`.
* The **text** payload is used to send a text reply from the user. It's the most common way of getting input from a user. Text messages sent this way are also matched for *intents* if you have any set up, so it can be used to select from menus or trigger intent-specific workflows. Its payload looks like ` { 'type': 'text', 'payload': 'my text' }`.

There are a few more ways that a user can interact with the Voiceflow agent, like clicking a button, but these two are enough to get us started. You can find more documentation about the types of requests that you can send in the [interact endpoint docs here](https://developer.voiceflow.com/reference/stateinteract-1).

> 📘 Next up: [How to start a conversation](https://docs.voiceflow.com/reference/api-guide-start-convo)
