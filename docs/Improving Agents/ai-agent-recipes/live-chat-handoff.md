---
title: Live Chat Handoff
excerpt: >-
  Use our open source chat widget and custom action step to do a handoff to a
  live chat platform
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: basic
      slug: advanced-webchat
      title: Web Chat (Advanced)
    - type: basic
      slug: custom-actions
      title: Custom Actions
---
# Overview

Voiceflow's Web Chat can be used together with any API-enabled live agent platform to create a seamless handoff experience between your Voiceflow <<glossary:agent>> and a support agent.

> 🚧 Live Agent Platform Requirements
> 
> In order to integrate effectively, make sure your live agent platform has the following features:
> 
> 1. a documented API (or an SDK) that can be used to:
>    1. create a new conversation with an agent.
>    2. add a new user-sent message to an existing conversation.
> 2. a mechanism (i.e. wehbooks, WebSocket, an SDK) for subscribing to changes to an existing conversation such as:
>    1. when a new message has been added by an agent.
>    2. [OPTIONAL] when the status of a conversation changes (agent assigned, conversation closed/ended)/

In this guide, we will walk through how you could build a live chat handoff between Voiceflow and Intercom using the Voiceflow [Chat UI Kit](doc:advanced-webchat) and a [Custom Action](doc:custom-actions) step.

The solution outlined in this guide requires an intermediary server that will maintain a Web Socket connection with the Web Chat widget. It will also make authenticated requests to the live agent platform. In practice, these features can also be added to any existing server in your infrastructure.

What we will cover:

- What the user experience might look like.
- Overview of the example project's key components.
- What you need to get started.
- Configuration guidelines for Voiceflow, Intercom, and your clone of the demo-react-chat project.

> 📘 Watch the following video tutorial for a walkthrough of the demo code:

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2Faee69aOnjSw%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3Daee69aOnjSw&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2Faee69aOnjSw%2Fhqdefault.jpg&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"100%\" style=\"aspect-ratio: 640 / 400\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=aee69aOnjSw",
  "title": "How to build a live chat handoff from Voiceflow to Intercom",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/aee69aOnjSw/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=aee69aOnjSw",
  "typeOfEmbed": "youtube"
}
[/block]


# User experience demo

When a customer reaches a point where a live agent's support is needed, you can automatically transition them from interacting with your Voiceflow <<glossary:agent>> to a live agent using Intercom.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.loom.com%2Fembed%2F86049b8284344dfcb5dc3722038ccc4a&display_name=Loom&url=https%3A%2F%2Fwww.loom.com%2Fshare%2F86049b8284344dfcb5dc3722038ccc4a%3Fsid%3De1fc05db-331a-4fb3-ab70-78e2e75e40a1&image=https%3A%2F%2Fcdn.loom.com%2Fsessions%2Fthumbnails%2F86049b8284344dfcb5dc3722038ccc4a-00001.gif&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=loom\" width=\"100%\" style=\"aspect-ratio: 640 / 400\" scrolling=\"no\" title=\"Loom embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.loom.com/share/86049b8284344dfcb5dc3722038ccc4a?sid=e1fc05db-331a-4fb3-ab70-78e2e75e40a1",
  "title": "Demo - Voiceflow to Intercom Live Chat Handoff",
  "image": "https://cdn.loom.com/sessions/thumbnails/86049b8284344dfcb5dc3722038ccc4a-00001.gif",
  "provider": "loom.com",
  "href": "https://www.loom.com/share/86049b8284344dfcb5dc3722038ccc4a?sid=e1fc05db-331a-4fb3-ab70-78e2e75e40a1",
  "typeOfEmbed": "youtube"
}
[/block]


# Key solution components

Following are key components of the example project's solution:

- **[@voiceflow/react-chat](https://www.npmjs.com/package/@voiceflow/react-chat)** — a library available on `npm` that contains a ReactJS component library. This library can be used to build a custom Voiceflow Web Chat experience. These components can be viewed in our storybook at any time.
- **webchat-server** — a simple Node.js server that maintains a Web Socket connection with the front-end. The server makes requests to the target live agent platform.
- **webchat-app** — a simple ReactJS web app that contains our custom Voiceflow Web Chat with live agent integration.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2859c4e-live-agent-handoff-simple-architecture-diagram.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


# What you need to get started

To follow along with this tutorial, you will need the following.

Voiceflow:

1. A Voiceflow account and workspace.
2. Voiceflow's [demo-react-chat repository](https://github.com/voiceflow/demo-react-chat).

Intercom:

1. An active Intercom account and workspace. (We recommend using a separate workspace for testing.)
2. Intercom permissions to create and manage apps in the Intercom Developer Hub.

# Configuration guidelines

## demo-react-chat configuration

1. Clone the [demo-react-chat repository](https://github.com/voiceflow/demo-react-chat) to your local machine.
2. Follow the set-up steps in the main directory's README.
3. Navigate to the server directory. (This directory contains a sample Web Socket server with some basic integrations.)
4. Follow the set-up steps in the server directory README. See the next section for steps on how to obtain an Intercom app access token.

## Voiceflow <<glossary:agent>> configuration

[Import](https://learn.voiceflow.com/hc/en-us/articles/6156731370381-Importing-Voiceflow-Files) the `example_project.vf` file in the demo-react-chat repository to your Voiceflow workspace. You can find the escalation flow under the “FAQ” [Topic](https://learn.voiceflow.com/hc/en-us/articles/12577894470029-What-are-Topics).

Once the example project is imported:

1. Open the project.
2. [Train](https://learn.voiceflow.com/hc/en-us/articles/6199790422285-Training-Prototype-NLU) your <<glossary:agent>> (the example project contains sample NLU training data).
3. Click “Publish”.
4. Copy the project's [Dialog Manager API Key](ref:project).

> 📘 The `talk_to_agent` Custom Action's "Stop on action" toggle must remain enabled.
> 
> When this Step is reached, the conversation with the <<glossary:agent>> will stop. This allows your custom app to initiate a conversation with the live chat platform.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f3e8df5-Screenshot_2023-08-21_at_10.43.21_AM.png",
        "",
        "Custom Action step with \"Stop on action\" enabled."
      ],
      "align": "center",
      "border": true,
      "caption": "Custom Action step with “Stop on action” enabled."
    }
  ]
}
[/block]


## Create an Intercom app and obtain an access token

We recommend using a test workspace in Intercom so that test conversations are separate from your active inboxes.

Logged in as an admin in your Intercom instance:

1. Navigate to the Intercom Developer Hub.
2. Create a new app.
3. Copy the app's access token to your clipboard.

In your demo-react-chat project:

1. Navigate to the .env file that you created under demo-react-chat/server in a previous step.
2. Set the access token you copied from Intercom as the `INTERCOM_TOKEN` value.

## Configure your test webhook

In your demo-react-chat project:

1. Under demo-react-chat/server, use `yarn dev` to run your server.
2. Since we are testing this locally, create a secure tunnel with a tool like ngrok so that your local server can interact with your Intercom app ([see this ngrok guide to learn more](https://ngrok.com/docs/secure-tunnels/tunnels/http-tunnels/)). Use port `9099`.
3. Copy the secure tunnel's forwarding address (e.g. `https://demo.ngrok-free.app`).

In your Intercom app's Webhooks tab:

1. Paste the forwarding address into the Endpoint URL field appended with `/intercom/webhook` (the full test Endpoint URL might look something like `https://demo.ngrok-free.app/intercom/webhook`).
2. Subscribe to the following Topics so that your app gets notified of key Intercom events:
   1. `conversation.admin.assigned`
   2. `conversation.admin.closed`
   3. `conversation.admin.replied`
3. Select “Send a test request” to confirm that your test webhook will receive events from Intercom as expected.

> 🚧 Please note that the demo-react-chat code is not production safe as-is. [Learn more here](https://github.com/voiceflow/demo-react-chat/tree/3b53dbf6590fdc9c9554689066baeaef46f5326b#-not-production-safe-).

# Time to test

In your demo-react-chat project:

- Under the main demo-react-chat directory, run `yarn dev`. Your demo app will be available locally at `http://127.0.0.1:3006`.

In your browser with your demo app open:

1. Click on the launch icon to open the Web Chat widget.
2. Enter “talk to human” to trigger the escalation flow.
3. Follow any prompts in the Web Chat widget.

In your Intercom test Workspace inbox:

1. Assign yourself to the new conversation. A system message should appear in Web Chat indicating that an agent has been assigned.
2. Send a few messages to ensure that user and agent inputs are sent back and forth between the systems.
3. Close the Intercom conversation. A system message should appear in Web Chat indicating that the agent has closed the conversation and that you will be returned to the Voiceflow bot.

> 📘 For a detailed walkthrough of the demo project code, watch our [How to integrate Voiceflow with Intercom](https://youtu.be/aee69aOnjSw) tutorial.

That's it! We are excited to see what you build from here! :tada: