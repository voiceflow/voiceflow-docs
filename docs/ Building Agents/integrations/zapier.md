---
title: Zapier
excerpt: Connect your Voiceflow agent to all the tools your business uses.
deprecated: false
hidden: true
metadata:
  robots: index
---
## Connecting to Zapier from inside Voiceflow

Voiceflow does not yet have a native Zapier integration available in the [Agent step](doc:agents) or [Tool step](changelog:tools-step), but we expect this to change in the future! For now, we recommend using using a [Zapier webhook trigger](https://help.zapier.com/hc/en-us/articles/8496288690317-Trigger-Zaps-from-webhooks) with the an API on the [Tool step](changelog:tools-step) to trigger zaps from inside your agent.

<br />

## Trigger Voiceflow events from your Zapier zaps

<Callout icon="❗️" theme="error">
  If you've found this page early, hold tight! This feature is coming soon.
</Callout>

Voiceflow is available as a native integration on Zapier. This allows you to trigger outbound calls when an action happens in another tool, as well as routing conversations from a wide range of platforms into your Voiceflow agent.

The following actions are available inside Zapier:

| Action Name              | Description                                                                                                                                                           |
| :----------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Start agent conversation | [Sends a launch request to your agent](https://docs.voiceflow.com/reference/stateinteract-1#/). When starting a new conversation, always start with a launch request. |
| Send message to agent    | [Sends a text request to your agent](https://docs.voiceflow.com/reference/stateinteract-1#/). This allows you to send text messages to your agent.                    |
| Send event to agent      | [Sends an event request to your agent](https://docs.voiceflow.com/reference/stateinteract-1#/). This lets you jump to a specific part of your agent's workflow.       |
| Make outbound call       | [Sends a call using the outbound calling API](doc:outbound-calls).                                                                                                    |

Please note that Voiceflow doesn't currently have any triggers available on Zapier.

### Using Voiceflow actions in Zapier

Voiceflow's actions can be added to your zaps in the same way as any other integration. Simply click on an empty action, search for Voiceflow, then choose the action you'd like to trigger.

![](https://files.readme.io/fcba7239696c0984f51fc282a151d65a1435af0cc0abb6836dc2b7a561a9486a-CleanShot_2025-08-07_at_13.10.092x.png)

<Callout icon="ℹ️" theme="info">
  **Protip:** if you're beginning a new conversation, make sure you use the **Start agent conversation** action before sending a message or an event to your agent!
</Callout>

<br />

Once you've chosen the action you'd like to trigger, you'll then need to link your Voiceflow project to Zapier. To do this, click on the **Account** dropdown and select **Connect a new account**.

For each Voiceflow project, you'll need to provide two values:

* Your **Voiceflow Project API Key**, which can be found by opening your project from the dashboard, clicking the ⚙️ icon on the sidebar, then selecting **API keys**. To get your API key, click the **copy** button.
* Your **Voiceflow Project ID**, which is found in the **General** tab of your project's settings.

After entering these values, click the continue button to link your Voiceflow project to Zapier.

<br />

![](https://files.readme.io/b077bad6b79133a6603d59375a3d6d5d2d4b234e02d04daeea53e19d9bb8a9c8-CleanShot_2025-08-07_at_13.17.502x.png)

<br />

### Handling outbound calls

While most of Voiceflow's Zapier actions only require the project's ID and API key, the **Trigger outbound call** action requires a **Agent Phone Number ID**. This can be found by opening clicking the **Interfaces** button on your project's sidebar, selecting **Telephony**, then clicking the **View** button next to the phone number that you'd like to call from.

The `Agent Phone Number ID` is the set of characters shown in the cURL request.

![](https://files.readme.io/8903135c9f883dc12b82c4302ef0ca0f522bb1d7887f5c52fcc926494b07f77e-CleanShot_2025-08-07_at_13.29.112x.png)

<br />

***

<zapier-workflow sign-up-email="email_of_your_user@example.com" sign-up-first-name="first_name_of_your_user" sign-up-last-name="last_name_of_your_user" client-id="rUkiqc6dl67ZP0IQF98xUmMLtiabc0rRR1lTagvT" theme="auto" intro-copy-display="hide" manage-zaps-display="hide" guess-zap-display="hide" app-search-bar-display="show" />