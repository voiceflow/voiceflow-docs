---
title: Saving your user transcript
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

Looking at the Create Transcripts API, we can see a quick description of it as well as a code snippet showing how to use it. Transcripts in Voiceflow aren't automatically saved whenever a conversation happens, so we have to send a `create transcript` request after each interaction to save it.

In the interactive documentation, it looks like we need to pass some information about the agent, and the `sessionID`. We can fill out the body parameters with our `projectID`, `versionID`, `sessionID` (it's just the same as the `user_id`) you've used in one of your previous tests, and insert our API key above and click **Try It!** to see the response from the transcripts API (this actually runs the full request on the real API!).

![](https://files.readme.io/1f5b9f0-image.png)

Looks like it's worked! We've saved a transcript with ID `6695a11bab10e059b87753e8`. Now let's adapt this code snippet into our Python script so that transcripts can automatically be saved.

 👉 Add and `projectID`, `versionID` variables to the top of your Python script. To learn how to find your IDs, see [this](https://developer.voiceflow.com/reference/project-ids-and-versions) doc. Note, you have to use the full versionID and not just “production”, and this versionID will update every time you publish your agent.

```python
import requests

api_key = 'YOUR_API_KEY_HERE' # it should look like this: VF.DM.XXXXXXX.XXXXXX... keep this a secret!

projectID = "YOUR_PROJECT_ID_HERE"
versionID = "YOUR_VERSION_ID_HERE"

buttons = []
[...]
```
```javascript
const axios = require('axios');
const readline = require('readline');

const api_key = 'YOUR_API_KEY_HERE'; // it should look like this: VF.DM.XXXXXXX.XXXXXX... keep this a secret!
const projectID = 'YOUR_PROJECT_ID_HERE';
const versionID = 'YOUR_VERSION_ID_HERE';

let buttons = [];

[...]
```

 👉 Add a new function to your script to save a transcript. Notice that this is a **put** request and not a **post** request. We'll then add it to run after each run through the main conversation loop.

```python
def save_transcript(user_id):
    url = "https://api.voiceflow.com/v2/transcripts"

    payload = {
        "projectID": projectID,
        "versionID": versionID,
        "sessionID": user_id
    }
    headers = {
        "accept": "application/json",
        "content-type": "application/json",
        "Authorization": api_key
    }

    response = requests.put(url, json=payload, headers=headers)

    print("Saved transcript with code " + str(response.status_code))

[...]

while (isRunning):
    [...]
    save_transcript(name)
```
```javascript
const axios = require('axios');
const readline = require('readline');

const api_key = 'YOUR_API_KEY_HERE'; // it should look like this: VF.DM.XXXXXXX.XXXXXX... keep this a secret!
const projectID = 'YOUR_PROJECT_ID_HERE';
const versionID = 'YOUR_VERSION_ID_HERE';

let buttons = [];

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
            } else if (trace.type === 'choice') {
                buttons = trace.payload.buttons;
                console.log('Choose one of the following:');
                for (let i = 0; i < buttons.length; i++) {
                    console.log(`${i + 1}. ${buttons[i].name}`);
                }
            } else if (trace.type === 'end') {
                return false;
            } else {
                console.log('Unhandled trace');
                console.log(trace);
            }
        }
        return true;
    } catch (error) {
        console.error('Error interacting with Voiceflow:', error);
        return false;
    }
};

const saveTranscript = async (user_id) => {
    try {
        const url = "https://api.voiceflow.com/v2/transcripts";
        const payload = {
            projectID: projectID,
            versionID: versionID,
            sessionID: user_id
        };
        const headers = {
            accept: "application/json",
            "content-type": "application/json",
            Authorization: api_key
        };

        const response = await axios.put(url, payload, { headers });

        console.log("Saved transcript with code " + response.status);
    } catch (error) {
        console.error('Error saving transcript:', error);
    }
};

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

const startConversation = async () => {
    rl.question('> What is your name?\n', async (name) => {
        let isRunning = await interact(name, { type: 'launch' });

        while (isRunning) {
            if (buttons.length > 0) {
                rl.question('> Choose a button number, or a reply\n', async (buttonSelection) => {
                    try {
                        isRunning = await interact(name, buttons[parseInt(buttonSelection) - 1].request);
                    } catch {
                        isRunning = await interact(name, { type: 'text', payload: buttonSelection });
                    }
                    buttons = [];
                    await saveTranscript(name); // Call saveTranscript after interaction
                });
            } else {
                rl.question('> Say something\n', async (nextInput) => {
                    isRunning = await interact(name, { type: 'text', payload: nextInput });
                    await saveTranscript(name); // Call saveTranscript after interaction
                });
            }
        }

        console.log('The conversation has ended.');
        rl.close();
    });
};

startConversation();
```

After running this script through to the end, and indeed we can check our transcript! I ran this one with User ID: `alex`, we can see the test I ran earlier with the interactive documentation with ID `test`.

![](https://files.readme.io/43a734f-image.png)

Treading transcripts like this can be super useful for analyzing how people use your Voiceflow agent, catch odd behavior or check AI token usage.

> ✨ Extra Challenge
> 
> Now try using the same method we showed above to write a compleltly seperate Python script to search for a transcript based on creation time, and then to read it's dialog. As a hint, you might want to use the **Fetch Project Transcripts** and **Get Transcript Dialog** endpoints. Good luck!

Here's the entirely **finished** code.

```python
import requests

api_key = 'YOUR_API_KEY_HERE' # it should look like this: VF.DM.XXXXXXX.XXXXXX... keep this a secret!

projectID = "YOUR_PROJECT_ID_HERE"
versionID = "YOUR_VERSION_ID_HERE"

buttons = []

# user_id defines who is having the conversation, e.g. steve, john.doe@gmail.com, username_464
def interact(user_id, request):
    global buttons

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
        elif trace['type'] == "choice":
            buttons = trace['payload']['buttons']
            print("Choose one of the following:")
            for i in range(len(buttons)):
                print(f"{i+1}. {buttons[i]['name']}")
        elif trace['type'] == 'end':
            # an end trace means the the voiceflow dialog has ended
            return False
        else:
            print("Unhandled trace")
            print(trace)
    # the dialog is still running
    return True

def save_transcript(user_id):
    url = "https://api.voiceflow.com/v2/transcripts"

    payload = {
        "projectID": projectID,
        "versionID": versionID,
        "sessionID": user_id
    }
    headers = {
        "accept": "application/json",
        "content-type": "application/json",
        "Authorization": api_key
    }

    response = requests.put(url, json=payload, headers=headers)

    print("Saved transcript with code " + str(response.status_code))

name = input('> What is your name?\n')
isRunning = interact(name, { 'type': 'launch' })

while (isRunning):
    if (len(buttons) > 0):
        buttonSelection = input('> Choose a button number, or a reply\n')
        try:
            isRunning = interact(name, buttons[int(buttonSelection) - 1]["request"])
        except:
            isRunning = interact(name, { 'type': 'text', 'payload': buttonSelection })
        buttons = []
    else:
        nextInput = input('> Say something\n')
        isRunning = interact(name, { 'type': 'text', 'payload': nextInput })
    save_transcript(name)

print("The conversation has ended.")
```
```javascript
const axios = require('axios');
const readline = require('readline');

const api_key = 'YOUR_API_KEY_HERE'; // it should look like this: VF.DM.XXXXXXX.XXXXXX... keep this a secret!
const projectID = 'YOUR_PROJECT_ID_HERE';
const versionID = 'YOUR_VERSION_ID_HERE';

let buttons = [];

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

const interact = async (user_id, request) => {
    try {
        const response = await axios.post(
            `https://general-runtime.voiceflow.com/state/user/${user_id}/interact`,
            { request: request },
            {
                headers: {
                    'Authorization': api_key,
                    'versionID': 'production',
                    "accept": "application/json",
                    "content-type": "application/json"
                }
            }
        );

        const traces = response.data;
        for (let trace of traces) {
            if (trace.type === 'text') {
                console.log(trace.payload.message);
            } else if (trace.type === 'choice') {
                buttons = trace.payload.buttons;
                console.log('Choose one of the following:');
                for (let i = 0; i < buttons.length; i++) {
                    console.log(`${i + 1}. ${buttons[i].name}`);
                }
            } else if (trace.type === 'end') {
                // an end trace means the voiceflow dialog has ended
                return false;
            } else {
                console.log('Unhandled trace');
                console.log(trace);
            }
        }
        // the dialog is still running
        return true;
    } catch (error) {
        console.error('Error interacting with Voiceflow:', error);
        return false;
    }
};

const saveTranscript = async (user_id) => {
    try {
        const response = await axios.put(
            'https://api.voiceflow.com/v2/transcripts',
            {
                projectID: projectID,
                versionID: versionID,
                sessionID: user_id
            },
            {
                headers: {
                    'accept': 'application/json',
                    'content-type': 'application/json',
                    'Authorization': api_key
                }
            }
        );

        console.log('Saved transcript with code ' + response.status);
    } catch (error) {
        console.error('Error saving transcript:', error);
    }
};

const startConversation = async () => {
    const question = (query) => {
        return new Promise(resolve => {
            rl.question(query, (answer) => {
                resolve(answer);
            });
        });
    };

    rl.question('> What is your name?\n', async (name) => {
        let isRunning = await interact(name, { type: 'launch' });

        while (isRunning) {
            if (buttons.length > 0) {
                const buttonSelection = await question('> Choose a button number, or a reply\n');
                try {
                    const selection = parseInt(buttonSelection);
                    if (isNaN(selection) || selection < 1 || selection > buttons.length) {
                        throw new Error('Invalid selection');
                    }
                    isRunning = await interact(name, buttons[selection - 1].request);
                } catch {
                    isRunning = await interact(name, { type: 'text', payload: buttonSelection });
                }
                buttons = [];
                await saveTranscript(name);
            } else {
                const nextInput = await question('> Say something\n');
                isRunning = await interact(name, { type: 'text', payload: nextInput });
                await saveTranscript(name);
            }
        }

        console.log('The conversation has ended.');
        rl.close();
    });
};

startConversation();
```

> 📘 [Next steps](https://docs.voiceflow.com/reference/api-guide-next-steps)