---
title: Zapier
deprecated: false
hidden: true
metadata:
  robots: index
---
## Connecting to Zapier from inside Voiceflow

Voiceflow does not yet have a native Zapier integration available in the [Agent step](doc:agents) or [Tool step](changelog:tools-step), but we expect this to change in the near future!

<br />

## Trigger Voiceflow events from your Zapier zaps

<Callout icon="❗️" theme="error">
  If you've found this page early, hold tight! This feature is coming soon.
</Callout>

Voiceflow is available as a native integration on Zapier. This allows you to trigger outbound calls when an action happens in another tool, as well as routing conversations from a wide range of platforms into your Voiceflow agent.

The following actions are available inside Zapier:

* Start agent conversation - [sends a launch request to your agent](https://docs.voiceflow.com/reference/stateinteract-1#/)
* Send message to agent - [sends a text request to your agent](https://docs.voiceflow.com/reference/stateinteract-1#/)
* Send event to agent - [sends an event request to your agent](https://docs.voiceflow.com/reference/stateinteract-1#/)
* Trigger outbound call - [sends a call using the outbound calling API](doc:outbound-calls)

Please note that Voiceflow doesn't currently support any Zapier triggers.

<br />

### Using Voiceflow actions in Zapier

Voiceflow's actions can be added to your zaps in the same way as any other integration. Simply click on an empty action, search for Voiceflow, then choose the action you'd like to trigger.

![](https://files.readme.io/fcba7239696c0984f51fc282a151d65a1435af0cc0abb6836dc2b7a561a9486a-CleanShot_2025-08-07_at_13.10.092x.png)

<Callout icon="ℹ️">
  **Protip:** if you're beginning a new conversation, make sure you use the **Start agent conversation** action before sending a message or an event to your agent!
</Callout>

Once you've chosen the action you'd like to trigger, you'll then need to link your Voiceflow project to Zapier. To do this, click on the **Account** dropdown and select **Connect a new account**.

For each Voiceflow project, you'll need to provide two values:

* Your **Voiceflow Project API Key**, which can be found by opening your project from the dashboard, clicking the ⚙️ item on the sidebar, then selecting **API keys**. To get your API key, click the **copy** button.
* Your **Voiceflow Project ID**, which is found in the **General** tab of your project's settings.

Once you've provided these values, click the continue button to link your project to Zapier.

![](https://files.readme.io/b077bad6b79133a6603d59375a3d6d5d2d4b234e02d04daeea53e19d9bb8a9c8-CleanShot_2025-08-07_at_13.17.502x.png)