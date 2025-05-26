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

* Voiceflow’s React chat UI elements, which you can customize or re-use to display other custom chat components.
* A `useRuntime` hook to interact with your assistant's flows and manage conversation turns.

## When to use `@voiceflow/react-chat`

* If you want to launch a chat experience in a `react` application.
* If you want to integrate a custom chat experience with custom message types or components such as (and not limited to) the following:
  * Calendar widget
  * [Live Chat Handoff](doc:live-chat-handoff)

> 📘 Use [Custom Actions](doc:custom-actions) in your assistant's design to help build custom components like the ones listed above.

# Demo

In this video, we will show you how to get started with our Web Chat UI Kit and what a Custom Action might look like.

<Embed url="https://www.youtube.com/playlist?list=PLKYemGIohRgAV1_H2qxZdG13ajdPjfz_h" title="Web Chat UI Kit" favicon="https://www.youtube.com/s/desktop/3587622d/img/favicon.ico" image="https://i.ytimg.com/vi/SJ4vWLt1b6M/hqdefault.jpg?sqp=-oaymwEWCKgBEF5IWvKriqkDCQgBFQAAiEIYAQ==&rs=AOn4CLD3C3QD1dvk9htYi0TIRZRGWXU4Nw&days_since_epoch=19578" provider="youtube.com" href="https://www.youtube.com/playlist?list=PLKYemGIohRgAV1_H2qxZdG13ajdPjfz_h" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttp%253A%252F%252Fwww.youtube.com%252Fembed%252Fvideoseries%253Flist%253DPLKYemGIohRgAV1_H2qxZdG13ajdPjfz_h%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fplaylist%253Flist%253DPLKYemGIohRgAV1_H2qxZdG13ajdPjfz_h%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FSJ4vWLt1b6M%252Fhqdefault.jpg%253Fsqp%253D-oaymwEWCKgBEF5IWvKriqkDCQgBFQAAiEIYAQ%253D%253D%2526rs%253DAOn4CLD3C3QD1dvk9htYi0TIRZRGWXU4Nw%2526days_since_epoch%253D19578%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22853%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

# Before you begin

* [Create a Voiceflow project](https://learn.voiceflow.com/hc/en-us/articles/15965489787789-Step-1-Create-a-Project) and
* [Get your Voiceflow assistant's Dialog API key](https://learn.voiceflow.com/hc/en-us/articles/13619375958413)

# Instructions & Code Repositories

You can find our open-source code and simple demo project repository with further instructions below:

* [react-chat package on npm](https://www.npmjs.com/package/@voiceflow/react-chat)
* [Demo React project](https://github.com/voiceflow/demo-react-chat) that uses the react-chat package and includes Custom Action demos

## `react-chat`

`react-chat` ([https://github.com/voiceflow/react-chat](https://github.com/voiceflow/react-chat)) is a repository that contains two packages:

### `packages/react-chat`

`packages/react-chat` is a component library that contains all of the Voiceflow Web Chat's out-of-the-box user interface elements like buttons, message bubbles and other building blocks that can be composed together to build a chat interface. You can inspect all of the available components in our [Storybook](https://voiceflow.github.io/react-chat/?path=/story/components-chat-assistantinfo--default).

This library is published to [npm](https://www.npmjs.com/package/@voiceflow/react-chat) as `@voiceflow/react-chat` and is bundled and distributed to the Voiceflow CDN. It can be used in other codebases, such as the `widget` package (found in the `react-chat` repository) or the `demo-react-chat` demo application.

### `packages/widget`

`packages/widget` is the wrapper code that fetches the latest artifacts of `packages/react-chat` from our CDN and renders it as a widget in an `<iframe>`. It also creates a two-way message bus to communicate with the widget.

This code is also bundled and distributed to our CDN, and is intended to be loaded by a simple JavaScript snippet (see [Web Chat (Basic)](doc:chat-widget)). This is the primary method of consuming this widget in production.

## `demo-react-chat`

`demo-react-chat` ([https://github.com/voiceflow/demo-react-chat](https://github.com/voiceflow/demo-react-chat)) is a repository that contains a basic `react` application. It holds examples of how to customize the chat experience in a number of ways to demonstrate the flexibility of the `@voiceflow/react-chat` library. This is the example application that we use for our [tutorials](https://youtube.com/playlist?list=PLKYemGIohRgAV1_H2qxZdG13ajdPjfz_h).
