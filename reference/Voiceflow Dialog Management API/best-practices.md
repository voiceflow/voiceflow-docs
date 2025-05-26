---
title: Best Practices
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
There are a number of best practices when working with the DM API:

### Use version aliases

In previous iterations of the DM API, you needed to specify the explicit `versionID` to interact\
with a particular version of the Voiceflow project. With the introduction of version aliases, this is unnecessary.

A version alias will always refer to whichever version occupies its corresponding slot and you can avoid the hassle of updating an explicit version ID by simplying pushing a new version into the slot.

For the `production` alias, you can update its slot by pressing the Publish button on the Voiceflow canvas. See the Production section for further details.

For the `development` alias, the version's diagram is updated as you edit on the canvas and the associated NLU is updated when you press "Train Assistant" in the Prototyping tool.

### Use Dialog Manager API Keys

Workspace and legacy Workspace API keys do not support version aliases, and so, code using Workspace keys will need to manually update `versionID` in their DM API calls. This leads to tedious to maintain code.

### Avoid the Stateless API

Previously, the Dialog Manager API had an older version named the Stateless API. This API is now deprecated in favour of the current "State API". It is **strongly recommended** to move away from the Stateless API for production code.

### Avoid security violations in `userId`

The `userId` can be used to identify the conversation session of your Voiceflow application with one of your customers. **Resist the temptation to use identifying information** like real names, emails, telephone numbers, or other identifying information in the `userId`. 

While this may seem convenient, it is a potential security hazard. If your app is compromised by a cyber attack, then it may be possible for attackers to scrape personal information off of the `userId`.

Additionally, you should **avoid any`userId` collisions**. Since the `userId` identifies a conversation, if\
two users have the same `userId`, then their conversation data may become mixed and leak information about one user to another. If one user gave sensitive information over their conversation, this may lead to a privacy leak.

### Use the `'production'` alias for production apps

The `'development'` alias points to the version on your canvas and this version's data updates in real-time as you modify it on canvas. Therefore, if you use the `'development'` alias on your live application, users may see your incomplete changes as you modify the diagram.

Use the `'production'` alias for live apps instead, as this version will only update when you explicitly press the Publish button on canvas.
