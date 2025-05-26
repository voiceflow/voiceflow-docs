---
title: Voice-Forward & Account Linking
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Introduction

In this article we will learn how to setup **Voice-Forward Account Linking** for **Login for Amazon** in your **Voiceflow Alexa project**.

# Context

Sometimes, to access specific APIs on the behalf of the user, you need to setup the account linking feature in your Alexa skill. This will allow your users to login by voice or with their credentials via the Alexa app without sharing any credentials with you. 

For this project, as we want to use the **Voice-Forward feature**, we are going to use the **Login for Amazon** service to authenticate and access user’s information.

## **How it works**

1. Create a new **Security Profile** on **Login with Amazon** portal
2. Setup **Account linking** and **permissions** on the Alexa Developer Console (**ADC**)
3. Handle the needed **Directives** and **Events** steps in your Voiceflow project
4. Retrieve user’s access token, consent token and use them to make authenticated API calls

***

## Step 1 | Create an Alexa project

The first thing we want to setup is our **Alexa project**. We don’t need to design it for now, we only want to upload it to **Alexa** to get access to it within the **Alexa Developer Console** for the next step.

![](https://files.readme.io/175b623-CleanShot_2022-09-02_at_12.15.34.png)

In **Voiceflow**, create a new **Alexa project**, give it a name and upload it to the **Alexa Developer Console** (**ADC**) by clicking on the **Upload to Alexa** button.

![](https://files.readme.io/fbea913-CleanShot_2022-09-02_at_12.19.01.png)

On the **Alexa Developer Console**, we need to get some **redirect URLs** to setup **Login with Amazon**.

Be sure to be on the **Build** tab, **TOOLS** section and click on **Account linking**.

![](https://files.readme.io/182ae23-CleanShot_2022-09-09_at_13.54.22.png)

On the main page, go to the **bottom** to see the **Alexa Redirect URLs**:

![](https://files.readme.io/a617fb0-CleanShot_2022-09-09_at_13.56.18.png)

**Keep this tab open** as we will need to access this information in our next step.

## Step 2 | Create a new Security Profile on Login with Amazon portal

**On another tab**, go to the **Login with Amazon** portal

[Amazon Developer Sign-In](https://developer.amazon.com/loginwithamazon/console/site/lwa/overview.html)

 And click on **Create a New Security Profile**.

![](https://files.readme.io/b34bf3d-CleanShot_2022-09-09_at_14.00.04.png)

Fill in the requested info and click on **Save**.

![](https://files.readme.io/6f7a0dc-CleanShot_2022-09-09_at_14.00.29.png)

Back on the main screen, move over the little **gear** to manage the profile you’ve just created.

![](https://files.readme.io/48ee411-CleanShot_2022-09-09_at_14.04.20.png)

In the drop-down menu, select **Web Settings**:

![](https://files.readme.io/1ef7ba7-CleanShot_2022-09-09_at_14.06.38.png)

Click on **Edit** as we need to add the **Return URLs from the Alexa Developer Console Account linking page** from our other tab.

![](https://files.readme.io/45fa251-CleanShot_2022-09-09_at_14.07.53.png)

Add the 3 URLs from the **Alexa Developer Console** and click on **Save**.

![](https://files.readme.io/157e72e-CleanShot_2022-09-09_at_14.10.17.png)

**Keep that page open** to get access to the **Client ID** and **Client Secret** a bit later.

## Step 3 | Setup Account Linking for your Skill

**Switch back to the Alexa Developer Console tab** and **enable Account linking** by clicking on the **first toggle** as well as the **last one** to allow user to link their account using voice.

![](https://files.readme.io/830cd2e-CleanShot_2022-09-09_at_14.14.25.png)

To fill all the information needed here you can refer to the **Configure an Authorization Code Grant documentation** at the bottom of this article but to help you with this process, here is what you will need to do to setup the **Login with Amazon account linking**:

*Your Web Authorization URI*:

```bash
https://www.amazon.com/ap/oa
```

*Access Token URI*:

```bash
https://api.amazon.com/auth/o2/token
```

*Your Client ID & Client Secret*

You can get this information from the **Login with Amazon** page:

![](https://files.readme.io/693bc52-CleanShot_2022-09-09_at_14.19.37.png)

*Your Authentication Scheme*:

```bash
HTTP Basic
```

Scope:

```bash
profile
postal_code
```

![](https://files.readme.io/cd22ac1-CleanShot_2022-09-09_at_14.16.16.png)

When done, click on the **Save** button on page the top right:

![](https://files.readme.io/b740ab3-CleanShot_2022-09-09_at_14.22.09.png)

## Step 4 | Add the needed permissions to your Skill

Now, on the left sidebar, click on **PERMISSIONS**:

![](https://files.readme.io/c36dbfd-CleanShot_2022-09-09_at_14.23.37.png)

And **activate the following permissions**:

![](https://files.readme.io/b4a6d9e-CleanShot_2022-09-09_at_14.24.31.png)

## Step 5 | Design your Voiceflow Alexa project

On the project, let’s add a simple Welcome **Speak step** followed by a **Set step**.

In the **Set step**, we are going to create and populate the \{**apiEndpoint**} and \{**consentToken**} with some data form the **\_system** variable.

In our case, we want the **access token** returned by the **account linking**, the **api endpoint** to use in our API call as well as the **consent token** to authorize those calls.

![](https://files.readme.io/c136480-CleanShot_2022-09-09_at_14.36.53.png)

\{**apiEndpoint**}

```bash
_system.apiEndpoint || 0
```

\{**consentToken**}

```bash
_system.user.permissions.consentToken || 0
```

\{**accessToken**}

```bash
_system.user.accessToken || 0
```

The following step in block is a **Condition** to check the \{**accessToken**} variable value:

![](https://files.readme.io/24390e2-CleanShot_2022-09-09_at_14.31.53.png)

To allow the user to **authorize with their voice**, we need to use the **Connections.StartConnection** directive.

![](https://files.readme.io/7c79174-CleanShot_2022-09-09_at_14.39.16.png)

![](https://files.readme.io/679a2b2-CleanShot_2022-09-09_at_14.39.39.png)

Drag a **Directive step** on the canvas and populate it with the following code:

```bash
{
   "type": "Connections.StartConnection",
   "uri": "connection://AMAZON.AskForAccountLinking/1",
   "onCompletion": "RESUME_SESSION",
   "input": {
            "@version": "1",
            "@type": "AskForAccountLinking"
    },
   "token": "accountLinking"
}
```

If you want to learn more about this directive, do not hesitate to check the **Voice-Forward Account Linking link in the Documentation section** of the article.

Thanks to that directive, Alexa will handle most of the process here:

![](https://files.readme.io/e1bad96-CleanShot_2022-09-09_at_14.44.09.png)

But, as explained in the documentation, we will have to handle the returned request, we can do so with the **Event step**.

First we want to be sure to **keep the session open** by using a **Javascript step** and the following code:

![](https://files.readme.io/2330949-CleanShot_2022-09-09_at_14.45.30.png)

```bash
_response = {
  shouldEndSession: null
}
```

**This will allow the skill to keep listening for any event**.

We are looking for two events here, the **Task.CompleteTask** and the **SessionResumedRequest** so let’s create two **Event steps** to handle that.

![](https://files.readme.io/1e277b5-CleanShot_2022-09-09_at_14.47.26.png)

The first one is just here to redirect any **Task.CompleteTask** event to the **Javascript** **step** that keep the session open.

![](https://files.readme.io/2107097-CleanShot_2022-09-09_at_14.50.58.png)

Set the Event Request Name to:

```bash
Task.CompleteTask
```

We are not really using any data from it so you can ignore the Request Mapping part.

The **SessionResumedRequest** is the one we are looking for to handle the account linking process.

![](https://files.readme.io/823e2a2-CleanShot_2022-09-09_at_14.56.42.png)

Set the Event Request Name to:

```bash
SessionResumedRequest
```

And the Request Mapping as follow:

```bash
data.cause.result.status > {status}
```

Now that we have the **Event** info mapped to our \{**status**} variable, we can use it in a **Conditions** **step** to redirect the user.

![](https://files.readme.io/7640bee-CleanShot_2022-09-09_at_14.59.52.png)

![](https://files.readme.io/e854e15-CleanShot_2022-09-09_at_14.59.29.png)

Again, you can find more details in the documentation at the bottom of the article but to summarize, if the \{**status**} variable value is:

> **USER\_REQUIREMENTS\_NOT\_MET** > We want to generate an Account Linking card and allow the user to authenticate within the Alexa app.
>
> **LINKED** > The user successfully link their account
>
> **DENIED** > The user says “No” to the prompt

* The ***DENIED*** port doesn’t need to be linked to anything, if the user refuse the link their account, Alexa will say “Okay, you can link your account at any time by going to the skills section of your Alexa app.” and we can exit the skill.
* The ***Else*** port will redirect the user to the Javascript step to let the session open.
* The ***LINKED*** port will follow the pass to tell the user that their account has been linked and the 2 API calls we will make to retrieve user’s info.
* The ***USER\_REQUIREMENTS\_NOT\_MET*** port is linked to another Directive step to generate the Account Linking card and exit the skill.

Let’s create the **Account Linking card** with a **Directive step** so we can link the ***USER\_REQUIREMENTS\_NOT\_MET*** port to it.

Drag a **Directive step** and paste the following code in it:

```bash
{
    "version": "1.0",
    "sessionAttributes": {},
    "response": {
      "outputSpeech": {
        "type": "PlainText",
        "text": "You must have an Amazon account to use this skill. Please use the Alexa app to link your Amazon account."
      },
      "card": {
        "type": "LinkAccount"
      },
      "shouldEndSession": true
    }
}
```

Then link it to the ***USER\_REQUIREMENTS\_NOT\_MET*** port.

![](https://files.readme.io/530e79f-CleanShot_2022-09-09_at_15.12.37.png)

While we are here, let’s also link the **Else** **port** to our **Javascript** **step**.

![](https://files.readme.io/899b19e-CleanShot_2022-09-09_at_15.13.15.png)

For the **LINKED** port, we are going to create the ‘**Access**’ **block** with a **Speak** **step** for the confirmation message, 2 **API steps** to retrieve user’s info (*name and email*) and a final **Speak step** to debug the info.

It will look to something similar to this:

![](https://files.readme.io/f78ba78-CleanShot_2022-09-09_at_15.16.41.png)

The first **Speak step** is only here to confirm that we were able to retrieve the **access token** from the account linking, or, if the user launch the skill again after having previously done the account linking process, **refresh** that token.

The first **API step** will get the user’s name by making the following request:

```bash
GET URL > {apiEndpoint}/v2/accounts/~current/settings/Profile.name
Headers > Authorization: Bearer {consentToken}
Mapping > response to {name}
```

![](https://files.readme.io/4b856ae-CleanShot_2022-09-09_at_15.21.08.png)

The second **API step** will get the user’s email by making the following request:

```bash
GET URL > {apiEndpoint}/v2/accounts/~current/settings/Profile.email
Headers > Authorization: Bearer {consentToken}
Mapping > response to {email}
```

![](https://files.readme.io/827ad76-CleanShot_2022-09-09_at_15.24.10.png)

In the last **Speak step** we are simply debugging the \{**name**} and \{**email**} variables values.

If you’ve followed this guide so far, this is how your project should look like.

![](https://files.readme.io/80534a9-CleanShot_2022-09-09_at_15.25.35.png)

**Upload it to Alexa** and test it in the Alexa Developer console (with a mic so Alexa can recognize your voice) or on an Echo device.

<aside>
⚠️ Do not forget to create a voice id in the Alexa app > Settings > Your Profile & Family section to be able to fully test your skill.

</aside>

***

### Information

<aside>
💡 For each upload, you might need to wait around 3-5 minutes for the changes made into your Voiceflow project to populate on the Alexa Developer Console and being able to fully test the skill. 

A good way to be sure that you are testing the updated version is to use a Speak step at the very beginning of your project with a version number. That way you can quickly know if you’re testing the correct updated version or if you have to wait a bit for your changes to propagate.

</aside>

### Documentation

Configure an Authorization Code Grant

[Configure an Authorization Code Grant | Alexa Skills Kit](https://developer.amazon.com/en-US/docs/alexa/account-linking/configure-authorization-code-grant.html)

Voice-Forward Account Linking

[Use Voice-Forward Account Linking for Alexa Skills (LWA) | Alexa Skills Kit](https://developer.amazon.com/en-US/docs/alexa/account-linking/use-voice-forward-account-linking.html)

[Voice-Forward Account Linking Implementation Details (LWA) | Alexa Skills Kit](https://developer.amazon.com/en-US/docs/alexa/account-linking/voice-forward-account-linking-implementation-details.html#implement-handler-request-task)

Request Customer Contact Information

[Request Customer Contact Information for Use in Your Skill | Alexa Skills Kit](https://developer.amazon.com/en-US/docs/alexa/custom-skills/request-customer-contact-information-for-use-in-your-skill.html)
