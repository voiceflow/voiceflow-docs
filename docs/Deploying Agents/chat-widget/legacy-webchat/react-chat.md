---
title: Open sourced react-chat
excerpt: >-
  We've open sourced our Web Chat widget so that you can make any modifications
  you want to it.
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
      slug: chat-widget
      title: Web Chat (Basic)
    - type: basic
      slug: custom-actions
      title: Custom Actions
---
# Overview

With Voiceflow’s Chat UI Kit (`react-chat`), you can customize the visual elements of your chat <<glossary:Agent>> like the font and colors or build a custom component for a [Custom Action](ref:custom-actions-1) step.

Our `react-chat` library is built in React and [available through npm](https://www.npmjs.com/package/@voiceflow/react-chat). The library provides access to:

- Voiceflow’s React chat UI elements, which you can customize or re-use to display other custom chat components.
- A `useRuntime` hook to interact with your agent's flows and manage conversation turns.

## When to use `@voiceflow/react-chat`

- If you want to launch a chat experience in a `react` application.
- If you want to integrate a custom chat experience with custom message types or components, such as (and not limited to) the following:
  - Calendar widget
  - [Live Chat Handoff](doc:live-chat-handoff)

> 📘 Use [Custom Actions](doc:custom-actions) in your agent's design to help build custom components like the ones listed above.

# Demo

In this video, we will show you how to get started with our Web Chat UI Kit and what a Custom Action might look like.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=http%3A%2F%2Fwww.youtube.com%2Fembed%2Fvideoseries%3Flist%3DPLKYemGIohRgAV1_H2qxZdG13ajdPjfz_h&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fplaylist%3Flist%3DPLKYemGIohRgAV1_H2qxZdG13ajdPjfz_h&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FSJ4vWLt1b6M%2Fhqdefault.jpg%3Fsqp%3D-oaymwEXCOADEI4CSFryq4qpAwkIARUAAIhCGAE%3D%26rs%3DAOn4CLDbtW7pwFCnw6wsCSvcQdLCbclt5w%26days_since_epoch%3D19979&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"853\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/playlist?list=PLKYemGIohRgAV1_H2qxZdG13ajdPjfz_h",
  "title": "Web Chat UI Kit",
  "favicon": "https://www.youtube.com/s/desktop/59ec15cc/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/SJ4vWLt1b6M/hqdefault.jpg?sqp=-oaymwEXCOADEI4CSFryq4qpAwkIARUAAIhCGAE=&rs=AOn4CLDbtW7pwFCnw6wsCSvcQdLCbclt5w&days_since_epoch=19979",
  "provider": "http://youtube.com",
  "href": "https://www.youtube.com/playlist?list=PLKYemGIohRgAV1_H2qxZdG13ajdPjfz_h",
  "typeOfEmbed": "youtube"
}
[/block]


# Before you begin

- [Create a Voiceflow project](https://learn.voiceflow.com/hc/en-us/articles/15965489787789-Step-1-Create-a-Project) and
- [Get your Voiceflow agent's Dialog Manager API key](https://learn.voiceflow.com/hc/en-us/articles/13619375958413)

# Instructions & Code Repositories

You can find our open-source code and simple demo project repository with further instructions below:

- [react-chat package on npm](https://www.npmjs.com/package/@voiceflow/react-chat)

## `react-chat`

`react-chat` (<https://github.com/voiceflow/react-chat>) is a repository that contains:

### `packages/react-chat`

`packages/react-chat` is the application code for webchat. It manages the client conversation state and can be customized with various configurations.

This library is bundled and distributed to the Voiceflow CDN. It is intended to be loaded by a simple JavaScript snippet (see [Web Chat (Basic)](doc:chat-widget)). This is the primary method of consuming this widget in production.