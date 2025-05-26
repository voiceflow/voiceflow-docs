---
title: How to send user replies
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

Let's make a basic input loop now so that we can talk back and forth with our Voiceflow agent. Inside the loop, we'll take input from the user to be sent to Voiceflow agent, and then format it into a response **text** payload `{ 'type': 'text', 'payload': nextInput }`.

👉 Add a `while (True):` loop to your script to send input to your Voiceflow agent. Inside it, get input from a user, and add a call to the interact function.

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
    
    for trace in response.json():
        if trace['type'] == 'text':
            print(trace['payload']['message'])
    
name = input('> What is your name?\n')
interact(name, { 'type': 'launch' })

while (True):
    nextInput = input('> Say something\n')
    interact(name, { 'type': 'text', 'payload': nextInput })
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

        const traces = response.data;
        for (let trace of traces) {
            if (trace.type === 'text') {
                console.log(trace.payload.message);
            }
        }
    } catch (error) {
        console.error('Error interacting with Voiceflow:', error);
    }
};

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

const startConversation = async () => {
    rl.question('> What is your name?\n', async (name) => {
        await interact(name, { type: 'launch' });

        while (true) {
            rl.question('> Say something\n', async (nextInput) => {
                await interact(name, { type: 'text', payload: nextInput });
            });
        }
    });
};

startConversation();
```

Now, if you run the script, you should be able to talk back and forth with your agent! 

```
python3 VoiceflowAPIGuide.py
> What is your name?
Testing-Alex
Hi there Python!
Echoing
> Say something
test
Echo #1: test
> Say something
tests
Echo #2: tests
> Say something
this is so cool!
Echo #3: this is so cool!
...
```

Our simple testing flow only uses a text step and a capture step to get text input from a user, and is an infinite loop. Let's switch to a slightly more advanced agent.

> 📘 Next up: [How to deal with other traces (button, end, and more)](https://docs.voiceflow.com/reference/api-guide-other-traces)