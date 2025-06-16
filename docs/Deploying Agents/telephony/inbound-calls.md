---
title: Inbound calls
deprecated: false
hidden: true
metadata:
  robots: index
---
Outbound calls share the same concurrency pool as outbound calls. The number of simultaneous calls you can make is [determined by your plan limits](https://voiceflow.com/pricing).

If your Voiceflow agent is already[ linked to Twilio and published to production](/voice), you're ready to start handling inbound calls.

Here’s how to test it, and what to expect.

<br />

## 1. Create Your Twilio Account and Gather Credentials

To get started, head over to twilio.com and sign up for a free account. Once you're in the dashboard, claim a phone number. This will be the number people call to reach your Voiceflow agent.

Twilio will provide three essential credentials: your Account SID, Auth Token, and Phone Number SID. These act as the keys that allow Voiceflow to securely connect with your Twilio number.

Make sure to copy these credentials and keep them somewhere safe, you’ll need them in just a moment.

<br />

## 2. Connect Twilio to Your Voiceflow Agent

Now, it’s time to connect Twilio to your Voiceflow project!

Open your project in Voiceflow and navigate to the Interfaces section on the left sidebar. Click into the Telephony tab. Here, you’ll see fields where you can paste in the Account SID, Auth Token, and Phone Number SID from Twilio.

Before you move on, make sure the environment is set to “Prod”, this ensures your calls are routed through your live agent, not a test version.

Once everything’s filled in, Voiceflow is now linked to your Twilio phone number, your agent is just one step away from answering real calls.

<br />

## 3. Publish Your Voiceflow Agent

To activate your changes, click Publish at the top right of your Voiceflow project. This will push your updates to production, making your agent ready to handle real inbound calls.

Publishing is what connects the dots. Your Twilio number, your Voiceflow project, and your users all come together in this moment.

<br />

## 4. Make Your First Call

Now for the fun part, testing it live.

Grab your phone and dial the Twilio number you set up earlier. Within seconds, you should hear your Voiceflow agent answer and begin the conversation flow you designed.

If everything was set up correctly, your agent is now live, responsive, and fully connected to the real world.