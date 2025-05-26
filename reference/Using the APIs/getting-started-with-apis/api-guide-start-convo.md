---
title: How to start a conversation
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

👉  At the bottom of your file, add a variable called name that will take an input from the user to set the user_id. We'll also just add a single **launch** request to our `interact` function and see what it prints.

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
    
name = input('> What is your name?\n')
interact(name, { 'type': 'launch' })
```
```javascript
const axios = require('axios');
const readline = require('readline');

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

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

rl.question('> What is your name?\n', (name) => {
    interact(name, { type: 'launch' }).then(() => rl.close());
});
```

👉 Run your Pythons script with `python3 VoiceflowAPIGuide.py` and watch your console! 

```
python3 VoiceflowAPIGuide.py
> What is your name?
Testing-Alex
[
   {
      "time":1721073897342,
      "type":"text",
      "payload":{
         [...]
         "message":"Hi there Python!",
      }
   },
   {
      "time":1721073897342,
      "type":"text",
      "payload":{
        [...]
         "message":"Echoing",
      }
   }
]
```

We see an array of JSON objects! Congratulations on doing your first interaction with a Voiceflow API! :tada: 🥳.

> 📘 Next up: [How to parse the output traces](https://docs.voiceflow.com/reference/api-guide-parse-traces)