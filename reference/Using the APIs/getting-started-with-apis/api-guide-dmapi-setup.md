---
title: Using the Dialog Manager API (DM API)
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

The most commonly used API with Voiceflow is the Dialog Manager API.  It's what drives the conversations on the webchat widget and acts as the backbone of any conversion happening with a Voiceflow agent. 

You send a request to it with a user input, it runs your Voiceflow agent and returns the agent's responses, and your program then takes turns giving user input and getting Voiceflow output.

You can read through it's full docs [here](https://developer.voiceflow.com/reference/overview) if you're interested in learning more, after this guide. 

You'll also be using a `user_id` to identify which conversation is going on. There are more details in the DM API guide, but in short, a `user_id` uniquely identifies a user's conversation, and for multiple requests to go back and forth and be in the same thread, you've got to keep the same `user_id`. If, on the other hand, you want to have multiple users talking at the same time, they should have different (unique, and hard to guess) `user_id`s. For this project, we'll just use a user's name as the `user_id`.

👉  Create a function called interact. It'll be used to communicate with Voiceflow.

```python
import requests

api_key = 'YOUR_API_KEY_HERE' # it should look like this: VF.DM.XXXXXXX.XXXXXX... keep this a secret!

# user_id defines who is having the conversation, e.g. steve, john.doe@gmail.com, username_464
def interact(user_id, request):
```
```javascript
const axios = require('axios');

const api_key = 'YOUR_API_KEY_HERE'; // it should look like this: VF.DM.XXXXXXX.XXXXXX... keep this a secret!

// user_id defines who is having the conversation, e.g. steve, john.doe@gmail.com, username_464
const interact = async (user_id, request) => {
    // Function implementation will go here
};
```

> 📘 Next up: [How to send requests to Voiceflow APIs](https://docs.voiceflow.com/reference/api-guide-send-requests)