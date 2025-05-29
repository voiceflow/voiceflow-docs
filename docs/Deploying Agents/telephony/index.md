---
title: Voice (phone number)
excerpt: Make your agent call phone numbers, and receive inbound phone calls.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Voiceflow integrates with Twilio, allowing you to connect a phone number to your agent. Agents with a phone number connected can receive inbound calls and programatically make outbound calls, subject to concurrency limits [associated with your plan](https://voiceflow.com/pricing). Our voice integration is often used for customer support hotlines, lead qualification workflows, and appointment scheduling.

<Image align="center" src="https://files.readme.io/8428ebe6c40486a6eebd700a972125273115c25bd3d4c0ea56ae7abf3533e507-Voiceflow_Slack.png" />

<br />

## Setting up voice

> ℹ️
>
> To use our voice features, you'll need a [Twilio account](https://twilio.com) and a Twilio phone number. A free trial account is enough to test out our voice integration.

You can add voice support to your agent in just a few minutes. Follow the instructions in the video below to get setup.

<Embed url="https://www.google.com/sorry/index?continue=https://www.youtube.com/watch%3Fv%3DOKwNac44-ok&q=EhAmAB8YEA2fMYrcc8iUu1GVGLPSvLoGIjDrnnTqeKP4K7-hiv2U51OmGdOsPwq0Kw4zlZx1O4gsqj18tKsPOTkPhxbu41laVS8yAXJaAUM" href="https://www.google.com/sorry/index?continue=https://www.youtube.com/watch%3Fv%3DOKwNac44-ok&q=EhAmAB8YEA2fMYrcc8iUu1GVGLPSvLoGIjDrnnTqeKP4K7-hiv2U51OmGdOsPwq0Kw4zlZx1O4gsqj18tKsPOTkPhxbu41laVS8yAXJaAUM" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Furl%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DOKwNac44-ok%26type%3Dtext%252Fhtml%26schema%3Dgoogle%26display_name%3DYouTube%26src%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FOKwNac44-ok%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

<Accordion title="Written version" icon="fa-file">
  test
  2\. 1. ![](https://files.readme.io/d47acc945735bf7ca7efe30fec612b62797d31344ab340c03e256e86fe750dfd-CleanShot_2024-12-02_at_11.28.29.png)
</Accordion>

<br />

## Getting Started

To set up the Twilio integration, you'll need to have a Twilio account with an active phone number, as well as Editor permissions in your Voiceflow workspace. Here's how to get started:

1. **Generate Twilio API credentials**
   1. Log in to your Twilio console and navigate to the Account Info section on the dashboard.
   2. Save the Account SID and Auth token for your account.

> ❗️
>
> Before proceeding, ensure you've setup a phone number in your Twilio account that is ready to connect to your agent.

2. **Enable the integration in Voiceflow (from Workspace)**

   1. Open your Voiceflow workspace and go to *Phone Numbers*.

      ![](https://files.readme.io/d47acc945735bf7ca7efe30fec612b62797d31344ab340c03e256e86fe750dfd-CleanShot_2024-12-02_at_11.28.29.png)
   2. Click *Import Numbers* and input the number you want to use.
   3. Enter your Twilio Account SID, Auth Token.
   4. *Optionally*, add a friendly name for your number.
   5. Click *Import* to connect your accounts.

   <Image align="center" src="https://files.readme.io/811b8ce14d0283eff8498b64bbc5300e1c79050df1904ebfd86ebe4476c4336c-CleanShot_2024-12-02_at_11.29.53.png" />

3. **Enable the integration in Voiceflow (from Agent)**
   1. Open your Voiceflow agent and go to the *Integrations* > *Telephony* tab.
   2. Follow same steps as above.

4. **Assign a phone number to your agent**

   1. Open your agent and go to the *Integrations* > *Telephony* tab.
   2. Under *Phone Numbers*, click *Assign existing number*.

      ![](https://files.readme.io/17989c07ffd31d7c8ccd5b60b5cb2afd506f6448d041f03a74e56442a7d3e193-CleanShot_2024-12-02_at_11.57.37.png)
   3. Choose a number and the environment (Development/Production) to route calls to.
      > 📘
      >
      > Reminder: Agents come with two built-in environments: the **development** and **production** environments. The development environment is what you edit with the Voiceflow canvas, while the production environment is the version that is automatically created (or updated) when you publish your agent.

5. **Test the integration by calling your agent from a real phone.**

## Change the Agent Assigned to a Phone Number

1. Go to the *Integrations* > *Telephony* tab for the agent you want to unassign.
2. Under Phone Numbers, click the *Unassign* option in the more menu next to the number.
3. Navigate to the same tab in the agent you want to reassign the number to.
4. Click *Assign existing number* and select the newly unassigned number.
5. Choose the environment and click *Assign number*.

## Best Practices & Tips

<Embed url="https://www.google.com/sorry/index?continue=https://www.youtube.com/watch%3Fv%3DqAmE7dbhJqw&q=EhAmAB8YEA2fEflVPTOI6fAvGOvRvLoGIjBA4L6vkw1NP6cMwVodwcxmgL3V-dN_99ClC9z_jCMfSZzq0BYr6PeB1EFyBxJlzpAyAXJaAUM" href="https://www.google.com/sorry/index?continue=https://www.youtube.com/watch%3Fv%3DqAmE7dbhJqw&q=EhAmAB8YEA2fEflVPTOI6fAvGOvRvLoGIjBA4L6vkw1NP6cMwVodwcxmgL3V-dN_99ClC9z_jCMfSZzq0BYr6PeB1EFyBxJlzpAyAXJaAUM" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Furl%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DqAmE7dbhJqw%26type%3Dtext%252Fhtml%26schema%3Dgoogle%26display_name%3DYouTube%26src%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FqAmE7dbhJqw%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

* Assign separate phone numbers for your Development and Production agent environments. This ensures that test calls don't interfere with production traffic.
* Verify the caller experience by dialing the phone numbers yourself before publicizing them to end users.

## Troubleshooting

### Limits

* **number of concurrent calls:**
  * **Starter**: 1 call
  * **Pro**: 5 calls
  * **Team**: 15 calls
  * **Enterprise**: 100 calls
* **maximum duration of call:** after 30 minutes, the call will automatically end
* **maximum user silence:** after 3 minutes, if the user does not speak or interact within this time, the call will end

### Integration Authorization Error

* Double check that you've entered your Twilio credentials (Account SID, Auth Token, Phone Number) correctly.
* If issue persists, check if your Twilio account is suspended due to lack of funds.

### Calls Not Routing to Voiceflow Agent

* Ensure that the **Routing** region is US. If it is not, please select US and then press 're-route' to save, you should see a URL that starts with [https://runtime-api.voiceflow.com/](https://runtime-api.voiceflow.com/)... in the 'A call comes in' section.

  ![](https://files.readme.io/34f88dfaa18ee1fe4e231a8f9786aedcd9a50741ffa05d5d57d42fd1c2f1c4ce-image.png)
* On Twilio, if you are porting a number from another service, check your number's *Configure With* isn't on an existing **TwiML App** or **SIP Trunk**. If so, select the **Webhook, TwiML Bin, Function, Studio Flow, Proxy Service** option and save the configuration. Then reassign the agent on Voiceflow.

  <Image align="center" width="80% " src="https://files.readme.io/6ae647cb3b51dc082c29be22df4e7c088faa948cb4ceae3decb7da6e8513982d-Screenshot_2024-12-13_at_8.54.00_AM.png" />

  * **If the "A call comes in" - "URL" starts with`https://runtime-api.voiceflow.com/...` then it's correct.**
* Confirm that the phone number has been properly assigned to the correct agent and environment in Voiceflow.
* Check that the agent's Interaction Endpoint URL has been correctly configured in the Twilio phone number's webhook settings.
* Verify that the agent is reachable and not throwing errors by testing it in the Voiceflow prototype tool.

### Sorry, no agents are available to take your call at this time.

* If you hear this message from the agent it means you've hit the limit for concurrent sessions for your plan. See "**number of concurrent calls**".

## Next Steps

* Explore the [ASR/TTS options](https://docs.voiceflow.com/docs/configuring-voice-settings) to customize the voice interaction behaviours.
* Learn how to configure [advanced voice workflows](https://docs.voiceflow.com/docs/advanced-using-custom-voice-actions) using custom actions.
* Join the Voiceflow Community to get inspired by what other builders are creating.