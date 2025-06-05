---
title: Blocks
excerpt: Group related steps into organized sections.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Blocks are used to group multiple [steps](doc:steps-1) together on the canvas. They help keep your assistant organized and make it easier to manage complex workflows. Each block has a name and colour, and can contain any number of steps.

<Image align="center" src="https://files.readme.io/4eb6944a9c97e5bc428b115c657609bf33e6ad20b6c3e31ce6243d0aef2a39b2-Message_1.png" />

Blocks are especially useful when:

* Structuring your conversation into logical sections (e.g. onboarding, booking, support)
* Jumping between parts of the project using [Actions](doc:actions)
* Reusing flow structures with the [Template library](doc:templates)

<br />

## Creating and editing blocks

You can create a block in two ways:

* Drag a step onto an empty area of the canvas - this automatically creates a new block.
* Drag a step into an existing block to add it to that block.

You can rename a block by clicking its label and entering a new name. Use colours to visually group sections of your project.

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSxE2EkKimEag8BWSoQbTdFYpDN5wRPeli0j21" />

<br />

## Deleting blocks

To delete a block:

* Right-click on the block's background and select **delete**
* Select the block and press `Delete` or `Backspace` on your keyboard.

Deleting a block will also remove all steps inside it, unless you move them out first.

<br />

## Connecting blocks

You can connect a path to an entire block or to a specific step inside a block.

* If you connect to a block, the conversation will run through all its steps in order.
* If you connect to a step inside a block, the conversation will jump to that specific step and continue from there

To create a connection, click the port (circle) on the right side of a step, then drag the path to your target block or step.

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NSlEuXOr094EsumPty2pBL3kDrzTnQ6SWYIVNH" />