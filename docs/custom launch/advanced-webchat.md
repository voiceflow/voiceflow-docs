---
title: Web Chat (Advanced)
excerpt: >-
  We've open sourced our Web Chat widget so that you can make any modifications
  you want to it.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
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

With Voiceflow’s Chat UI Kit (`react-chat`), you can customize your chat assistant’s visual elements like the font and colors or build a custom component for a [Custom Action](ref:custom-actions-1) step.

Our `react-chat` library is built in React and [available through npm](https://www.npmjs.com/package/@voiceflow/react-chat). The library provides access to:

- Voiceflow’s React chat UI elements, which you can customize or re-use to display other custom chat components.
- A `useRuntime` hook to interact with your assistant's flows and manage conversation turns.

## When to use `@voiceflow/react-chat`

- If you want to launch a chat experience in a `react` application.
- If you want to integrate a custom chat experience with custom message types or components such as (and not limited to) the following:
  - Calendar widget
  - [Live Chat Handoff](doc:live-chat-handoff)

> 📘 Use [Custom Actions](doc:custom-actions) in your assistant's design to help build custom components like the ones listed above.

# Demo

In this video, we will show you how to get started with our Web Chat UI Kit and what a Custom Action might look like.


[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=http%3A%2F%2Fwww.youtube.com%2Fembed%2Fvideoseries%3Flist%3DPLKYemGIohRgAV1_H2qxZdG13ajdPjfz_h&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fplaylist%3Flist%3DPLKYemGIohRgAV1_H2qxZdG13ajdPjfz_h&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FSJ4vWLt1b6M%2Fhqdefault.jpg%3Fsqp%3D-oaymwEWCKgBEF5IWvKriqkDCQgBFQAAiEIYAQ%3D%3D%26rs%3DAOn4CLD3C3QD1dvk9htYi0TIRZRGWXU4Nw%26days_since_epoch%3D19578&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"853\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/playlist?list=PLKYemGIohRgAV1_H2qxZdG13ajdPjfz_h",
  "title": "Web Chat UI Kit",
  "favicon": "https://www.youtube.com/s/desktop/3587622d/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/SJ4vWLt1b6M/hqdefault.jpg?sqp=-oaymwEWCKgBEF5IWvKriqkDCQgBFQAAiEIYAQ==&rs=AOn4CLD3C3QD1dvk9htYi0TIRZRGWXU4Nw&days_since_epoch=19578",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/playlist?list=PLKYemGIohRgAV1_H2qxZdG13ajdPjfz_h",
  "typeOfEmbed": "youtube"
}
[/block]


# Before you begin

- [Create a Voiceflow project](https://learn.voiceflow.com/hc/en-us/articles/15965489787789-Step-1-Create-a-Project) and
- [Get your Voiceflow assistant's Dialog API key](https://learn.voiceflow.com/hc/en-us/articles/13619375958413)

# Instructions & Code Repositories

You can find our open-source code and simple demo project repository with further instructions below:

- [react-chat package on npm](https://www.npmjs.com/package/@voiceflow/react-chat)
- [Demo React project](https://github.com/voiceflow/demo-react-chat) that uses the react-chat package and includes Custom Action demos

## `react-chat`

`react-chat` (<https://github.com/voiceflow/react-chat>) is a repository that contains two packages:

### `packages/react-chat`

`packages/react-chat` is a component library that contains all of the Voiceflow Web Chat's out-of-the-box user interface elements like buttons, message bubbles and other building blocks that can be composed together to build a chat interface. You can inspect all of the available components in our [Storybook](https://voiceflow.github.io/react-chat/?path=/story/components-chat-assistantinfo--default).

This library is published to [npm](https://www.npmjs.com/package/@voiceflow/react-chat) as `@voiceflow/react-chat` and is bundled and distributed to the Voiceflow CDN. It can be used in other codebases, such as the `widget` package (found in the `react-chat` repository) or the `demo-react-chat` demo application.

### `packages/widget`

`packages/widget` is the wrapper code that fetches the latest artifacts of `packages/react-chat` from our CDN and renders it as a widget in an `<iframe>`. It also creates a two-way message bus to communicate with the widget.

This code is also bundled and distributed to our CDN, and is intended to be loaded by a simple JavaScript snippet (see [Web Chat (Basic)](doc:chat-widget)). This is the primary method of consuming this widget in production.

## `demo-react-chat`

`demo-react-chat` (<https://github.com/voiceflow/demo-react-chat>) is a repository that contains a basic `react` application. It holds examples of how to customize the chat experience in a number of ways to demonstrate the flexibility of the `@voiceflow/react-chat` library. This is the example application that we use for our [tutorials](https://youtube.com/playlist?list=PLKYemGIohRgAV1_H2qxZdG13ajdPjfz_h).