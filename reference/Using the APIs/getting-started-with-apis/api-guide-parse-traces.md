---
title: How to parse the output traces
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

Now, let's go into how to interpret this big array of JSON objects. Each of these objects is called a trace, which represent any _output_ from Voiceflow. Their most important fields are the `type` which tells you how to interpret the second part, the `payload` that actually stores the content you need to use the output. 

So a response from the DM API is made of an array of traces, and to parse them we have to iterate through the array of traces. You can learn more about other traces [here](https://developer.voiceflow.com/reference/trace-types).

To get a simple output from our agent, we'll just start off with looking for `text` traces, that store their content in the payload's message field: `trace['payload']['message']`.

👉 Add a `for` loop iterating through all the response traces, looking for `text` traces and printing it's output.

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

rl.question('> What is your name?\n', (name) => {
    interact(name, { type: 'launch' }).then(() => rl.close());
});

```

You should now get a much easier to understand output in your terminal.

```
python3 VoiceflowAPIGuide.py
> What is your name?
Testing-Alex
Hi there Python!
Echoing
```

Amazing! Now we've got text messages back from our Voiceflow agent. But the conversation's just one step… let's figure out how to send an answer back.

> 📘 Next up: [How to send user replies](https://docs.voiceflow.com/reference/api-guide-user-reply)