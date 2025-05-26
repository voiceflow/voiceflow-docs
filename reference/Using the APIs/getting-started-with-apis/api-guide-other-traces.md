---
title: How to deal with other traces (button, end, and more)
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

👉 Import [the second agent example project](https://github.com/SuperZooper3/Voiceflow-Getting-Started-APIs-Guide/blob/main/Voiceflow_API_Getting_Started_Part_2.vf). Make sure to run it, publish it, and the update the API key in your Python code.

Other than just the text step, you might want to be able to use buttons, but you might find that if you run the new project, the buttons don't appear in the terminal. That's because a button is a different type of trace than we have dealt with yet.

To see the traces we haven't dealt with show up in the terminal so that we can debug, we'll add a catch-all trace behavior. **We recommend to always add this kind of catch-all printing, as it's super helpful when you're developing and debugging.**

👉 Add an `else:` case to the trace handling loop.

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
        else:
            print("Unhandled trace")
            print(trace)
    
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
            } else {
                console.log('Unhandled trace');
                console.log(trace);
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

Now, when we run the agent, we'll see that the unhandled button trace is printed. (You can ignore the path trace, it's just an extra trace output by Voiceflow that indicates what path you've gone down, and shouldn't be necessary for any projects).

```
python3 VoiceflowAPIGuide.py
[...]
Unhandled trace
{
   "time":1721077675242,
   "type":"choice",
   "payload":{
      "buttons":[
         {
            "name":"Hat",
            "request":{
               "type":"path-mu25u3epc",
               [..]
            }
         },
         {
            "name":"Shirt",
            "request":{
               "type":"path-if27o3ev7",
               [...]
            }
         },
         {
            "name":"Neither",
            "request":{
               "type":"path-2v28a3eqk",
[...]
```

To learn how to handle each different kind of trace, it's really useful to look at [this trace documentation](https://developer.voiceflow.com/reference/trace-types), and we'll walk through handling the `choice` (buttons) trace.

The important steps are

1. Storing all the buttons in an array
2. Displaying the button options in the terminal and get input from the user
3. Tell voiceflow which button we've clicked.

👉 To store the buttons in an array, we'll create a **global** array at the top of the file called `buttons` and store each button in it by adding a new trace case for `choice`, and then print all the options available.

```python
import requests

api_key = 'YOUR_API_KEY_HERE' # it should look like this: VF.DM.XXXXXXX.XXXXXX... keep this a secret!

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
        else:
            print("Unhandled trace")
            print(trace)

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

let buttons = [];

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
            } else if (trace.type === 'choice') {
                buttons = trace.payload.buttons;
                console.log('Choose one of the following:');
                for (let i = 0; i < buttons.length; i++) {
                    console.log(`${i + 1}. ${buttons[i].name}`);
                }
            } else {
                console.log('Unhandled trace');
                console.log(trace);
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

This will then print something like:

```
Would you prefer to get a test hat or a test t-shirt?
Choose one of the following:
1. Hat
2. Shirt
3. Neither
```

Now, we have to get the button selection from a user. We'll add some conditional logic to check if there are button choices available, and if so to interpret the input as an index into that list of choices. If the user selects one of the choices, we'll reply to Voiceflow with the **request** payload that each button had attached to it. If they give another answer, we'll pass it to Voiceflow as a normal text response, and it'll either be recognized as an intent, or go down the No Match path of the button.

👉 Copy the new code below that gets a selected button from the user if there are any options, and sends the associated answer back.

```python
import requests

api_key = 'YOUR_API_KEY_HERE' # it should look like this: VF.DM.XXXXXXX.XXXXXX... keep this a secret!

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
        else:
            print("Unhandled trace")
            print(trace)

name = input('> What is your name?\n')
interact(name, { 'type': 'launch' })

while (True):
    if (len(buttons) > 0):
        buttonSelection = input('> Choose a button number, or a reply\n')
        try:
            interact(name, buttons[int(buttonSelection) - 1]["request"])
        except:
            interact(name, { 'type': 'text', 'payload': buttonSelection })
        buttons = []
    else:
        nextInput = input('> Say something\n')
        interact(name, { 'type': 'text', 'payload': nextInput })
```
```javascript
const axios = require('axios');
const readline = require('readline');

const api_key = 'YOUR_API_KEY_HERE'; // it should look like this: VF.DM.XXXXXXX.XXXXXX... keep this a secret!

let buttons = [];

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
            } else if (trace.type === 'choice') {
                buttons = trace.payload.buttons;
                console.log('Choose one of the following:');
                for (let i = 0; i < buttons.length; i++) {
                    console.log(`${i + 1}. ${buttons[i].name}`);
                }
            } else {
                console.log('Unhandled trace');
                console.log(trace);
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
            if (buttons.length > 0) {
                rl.question('> Choose a button number, or a reply\n', async (buttonSelection) => {
                    try {
                        const selection = parseInt(buttonSelection);
                        if (isNaN(selection) || selection < 1 || selection > buttons.length) {
                            throw new Error('Invalid selection');
                        }
                        await interact(name, buttons[selection - 1].request);
                    } catch {
                        await interact(name, { type: 'text', payload: buttonSelection });
                    }
                    buttons = [];
                });
            } else {
                rl.question('> Say something\n', async (nextInput) => {
                    await interact(name, { type: 'text', payload: nextInput });
                });
            }
        }
    });
};

startConversation();
```

Now, we can answer `2` to select a Shirt! 

Handling buttons is similar to how many other traces are handled, so as you expand your interface using the DM API, you'll implement more and more traces.

> ✨ Extra Challenge
> 
> The provided flow includes two images that are shared when you choose either a shirt or a hat. Try handling those traces and displaying the images from inside your Python script! As a hint, you could use matplotlib, pillow, or IPython.display to show the images. Good luck!

One last trace that's important to handle is the **end** trace. It's triggered by Voiceflow when there's no more steps attached to a path, or you hit the end step. You might have seen it after choosing one of the options in your handy catch-all trace print: `{'type': 'end'}`. 

👉 To handle the end trace, we'll store a boolean called `isRunning` that's updated each time we interact with Voiceflow, and represents if we've encountered the end trace, and we'll loop while `isRunning` is true, and set it false if we encounter the end trace.

```python
import requests

api_key = 'YOUR_API_KEY_HERE' # it should look like this: VF.DM.XXXXXXX.XXXXXX... keep this a secret!

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

print("The conversation has ended.")
```
```javascript
const axios = require('axios');
const readline = require('readline');

const api_key = 'YOUR_API_KEY_HERE'; // it should look like this: VF.DM.XXXXXXX.XXXXXX... keep this a secret!

let buttons = [];

// Function to interact with Voiceflow API
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
                // End of conversation
                return false;
            } else {
                console.log('Unhandled trace');
                console.log(trace);
            }
        }
        // Conversation is still running
        return true;
    } catch (error) {
        console.error('Error interacting with Voiceflow:', error);
        return false;
    }
};

// Readline interface for user input
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

// Function to start the conversation
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
                });
            } else {
                rl.question('> Say something\n', async (nextInput) => {
                    isRunning = await interact(name, { type: 'text', payload: nextInput });
                });
            }
        }

        console.log('The conversation has ended.');
        rl.close();
    });
};

startConversation();
```

Congratulations! We've made a nice little Voiceflow conversation interface here, and you can extrapolate lots of the lessons we've learned here to build apps and custom interfaces like the [EduChat Article Reader](https://youtu.be/DxIsHNxr_0g?si=7oli8xejSiIzSfFj) or the [Unity AI NPC](https://youtu.be/-_grpoO6AJ0?si=jtGaIpiDrMGlE27A).

> 📘 Next up: [Using the Transcripts API](https://docs.voiceflow.com/reference/using-the-transcripts-api)