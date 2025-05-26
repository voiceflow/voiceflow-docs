---
title: Commands (legacy)
excerpt: ''
deprecated: true
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
**What are commands? How do I add commands?**

Commands act as a 'go to and return' function, and are nested in the Home block.

> 🚧 Commands are being phased out, and are not available on newly made projects

Once they’ve completed the flow/command, they’ll be returned to their spot in the original path. Essentially, Commands let your users quickly switch context mid-conversation without the frustration of repeating themselves to get back to their original spot. 

Commands allow for another method for you to design & create non-linear conversations. They let your users interrupt a conversation path and temporarily bounce to a Component flow.

Commands are triggered by a global intent that leads into a component. Once the component is complete, the conversation will continue from wherever the user was before triggering the command.

**Adding & Deleting Commands**

Add and delete Commands in your Home block's editor Command section.

![](https://files.readme.io/dc63048-image.png)

You'll need to define 2 aspects for the Command:

**Intent** - Attaches an intent to the Command, making it triggerable at any point in the conversation.

**Component** - Indicated the Component path that is activated when the above intent is triggered.

![](https://files.readme.io/2fb6503-image.png)

Once you've configured your Commands, they'll be visible in the Home block's content editor.
