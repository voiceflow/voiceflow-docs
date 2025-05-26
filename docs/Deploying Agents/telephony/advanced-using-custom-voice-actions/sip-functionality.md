---
title: SIP Functionality
excerpt: Recieve and forward calls with Session Initiation Protocol (SIP)
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# SIP Forwarding

If you wish to foward an existing call to a SIP address, this is possible through Twilio's TwiML Dial SIP feature.

Create a **Custom action** step and name it `twiml`. 

Set the **Action Body** to "Text", and you can Dial to a SIP address.

<Image align="center" src="https://files.readme.io/468290474003c2d0b0e00f9f68eaf07f3988fc45ccd9955ada415298cfcf749e-Capture_decran_le_2025-02-12_a_11.39.30.png" />

Example TwiML code:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Response>
    <Dial>
        <Sip>sip:alice@example.com;region=ie1</Sip>
    </Dial>
</Response>
```

Reference Twilio documentation for further information on how to format SIP addresses:\
[https://www.twilio.com/docs/voice/twiml/sip](https://www.twilio.com/docs/voice/twiml/sip)

# SIP Outbound

It is possible to bind a Voiceflow agent to a SIP address via Twilio. For more information reference:\
[https://www.twilio.com/docs/voice/api/sending-sip](https://www.twilio.com/docs/voice/api/sending-sip)\
[https://www.twilio.com/docs/voice/tutorials/how-to-route-calls-to-your-sip-network](https://www.twilio.com/docs/voice/tutorials/how-to-route-calls-to-your-sip-network)

On Twilio, under "Voice" > "Manage", you'll find a tab called "SIP domains". You'll need to register a new domain with Twilio and set it up.

<Image align="center" src="https://files.readme.io/14818be7a978effb9ef5c088356501c4c4ccddb9686810a678ae560f5bad8cdf-Capture_decran_le_2025-02-12_a_11.48.43.png" />

Create a new credential, remember the username and password, this is what will be needed to log in.

<Image align="center" src="https://files.readme.io/94684b92cce2187ba1b679ce5657aac64a7f852d2af3d8de3c396765fd9b3985-Capture_decran_le_2025-02-12_a_11.49.46.png" />

Add your credential to "Voice Authentication".

Enable **SIP Registration**, and ensure your credential is added to "SIP Registration Authentication".

When you assign a [Voiceflow agent to a phone number](https://docs.voiceflow.com/docs/setting-up-twilio-integration), it'll automatically populate the webhook with a URL.

<Image align="center" src="https://files.readme.io/532dba2e2e21e32d5319b42dbf22d52a9f49eefe961797e54bc07b5539412e3f-Capture_decran_le_2025-02-12_a_11.46.29.png" />

Copy and paste this webhook into "Call Control Configuration". When a call is initiated from this SIP address, it will now hit the same webhook that the phone call hits.

<Image align="center" src="https://files.readme.io/18e4687a491aa0a1113552900ba152df89cb4e0e51a2534d5e4805d3b06fa51e-Capture_decran_le_2025-02-12_a_11.53.32.png" />

To test this SIP functionality, you can download a free softphone service such as Zopier5 and register the login:\
[https://www.zoiper.com/](https://www.zoiper.com/)

Log in with the same credentials you've used earlier. i.e. `test@voiceflowtest.sip.twilio.com`.

<Image align="center" src="https://files.readme.io/3732b2f9c5b7451fa29de0b832ff468ba28796026de261827f234ed728327079-Capture_decran_le_2025-02-12_a_11.56.42.png" />

Create a new contact, just call it whatever you want. The "Phone" field can just be "test".\
When you try to call outbound to that number it will now hit your Voiceflow bot.

<Image align="center" src="https://files.readme.io/37b4209ccc8a3245131fdbd1097e8688e975f920b14c180191a1caf1aa158a35-Capture_decran_le_2025-02-12_a_11.59.14.png" />
