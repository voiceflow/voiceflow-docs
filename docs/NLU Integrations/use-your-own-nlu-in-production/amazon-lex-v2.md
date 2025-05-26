---
title: Amazon Lex V2
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
##Overview
In this guide, we will take a look at how to setup a custom NLU connection between Lex V2 and Voiceflow.
[block:callout]
{
  "type": "info",
  "title": "Resources",
  "body": "- [Template source code on Github](https://github.com/zslamkov/voiceflow_lexv2)\n- [Voiceflow](https://www.voiceflow.com) **Chat Assistant** project"
}
[/block]
## Prerequisites
Here are the tools you will need for this project:
1. Amazon Lex V2 Bot
2. Voiceflow Account

## Setting up the Project

Install and run the project:

1. Clone this repo:
```bash
git clone https://github.com/zslamkov/voiceflow_lexv2.git
```

2. Install dependencies:
```bash
npm install
```

## Signing AWS HTTP Requests

To allow for all of our AWS requests to be signed with an AWSv4 signature, we will be using the [`aws-axios`](https://www.npmjs.com/package/aws4-axios) package.

We can complete the connection with only a few lines of code
```js
const client = axios.create();

const interceptor = aws4Interceptor(
  {
    region: "us-east-1",
    service: "lex",
  },
  {
    accessKeyId: process.env.AWS_KEY_ID,
    secretAccessKey: process.env.AWS_SECRET,
  }
);

client.interceptors.request.use(interceptor);
```

## Retrieve Intent Data

We will be sending an unstructured utterance to the Lex V2 [`RecognizeText`](https://docs.aws.amazon.com/lexv2/latest/dg/API_runtime_RecognizeText.html) endpoint in order to receive a response with:
1. The triggered intent name
2. Entity key/values
3. Confidence score
[block:callout]
{
  "type": "warning",
  "title": "INTENT AND SLOT NAMES MUST MATCH",
  "body": "Make sure to have all slot and intent names in your Lex bot and Voiceflow interaction model match in order to trigger the right path."
}
[/block]
The below function illustrates the request and how to transform the response into a format ready for Voiceflow. 
```js
async function detectIntent(textInput, sessionID) {
  const response = await client
    .post(
      `https://runtime-v2-lex.us-east-1.amazonaws.com/bots/${botID}/botAliases/${aliasID}/botLocales/${botLocale}/sessions/${sessionID}/text`,
      { text: textInput }
    )
    .then(
      (response) => {
        console.log(response.data.interpretations[0].nluConfidence.score);
        return response;
      },
      (err) => {
        console.log(err);
      }
    );

  const intent = response.data.interpretations[0].intent.name;
  const entities = response.data.interpretations[0].intent.slots;
  const nluConfidence = response.data.interpretations[0].nluConfidence.score;

  const createIntent = (name, value) => ({ name, value });
  const arr = [];

  for (const [key, value] of Object.entries(entities)) {
    if (value != null) {
      const intents = createIntent(key, value.value.interpretedValue);
      arr.push(intents);
    }
  }

  return { response: intent, entities: arr, confidence: nluConfidence };
}
```

## Node.js App

The below app allows us to interact with our chat assistant via the CLI. 

We will be retrieving the `userID` by having the user enter their name. Once completed, we will send a launch request to Voiceflow to start the conversation and send the first steps to the channel. 


```js
async function main() {
  const userID = await cli.prompt("> What is your name?");
  // send a simple launch request starting the dialog
  let isRunning = await interact(userID, { type: "launch" });
```
Now on each new interaction from the user, we will be passing the userID and text input through the `detectIntent` function and returning the `intent` object that will be used in the next line of code to populate the request payload to Voiceflow. 

```js
  while (isRunning) {
    const nextInput = await cli.prompt("> Say something");
    // send a simple text type request with the user input
    let intent = await detectIntent(nextInput, userID);
    
    isRunning = await interact(userID, {
      type: "intent",
      payload: {
        intent: {
          name: intent.response,
        },
        entities: intent.entities,
        confidence: intent.confidence,
      },
    });
  }
  console.log("The end! Start me again with `npm start`");
}

main();
```

## Run
What it might look like in action:

```
$ npm start

> What is your name?: zoran
what can I do for you?
...
> Say something: send email
who is the recipient?
...
> Say something: zoran@voiceflow.com
what is the title of your email?
...
> Say something: How was your day?
sending the email for zoran@voiceflow.com called "How was your day?". Is that correct?
...
> Say something: yes
successfully sent the email for zoran@voiceflow.com called "How was your day?"
The end! Start me again with `npm start`
```