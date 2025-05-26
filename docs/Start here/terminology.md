---
title: Terminology
excerpt: Learn the terms used in these docs.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Industry Terms

### Dialog Manager



### Utterance

An utterance is a phrase that a user might say (or type) to interact with an Assistant.

The following are all examples of utterances for an `order_food` intent.

```yaml
INTENT: "order_food"
	- "i am feeling hungry"
	- "i want takeout"
	- "i would like {food}"
```



### Intent

An intent represents an action that a user might want to take. Each intent includes a collection of associated utterances. These utterances will be analyzed to determine whether a user triggers the associated intent with any of their interactions.

In the following example the user has used one of the utterances of an `order_food` intent and the system responds accordingly.

```yaml
USER: "i want takeout"
* SYSTEM has recognized this utterance as part of the "order_food" intent *
SYSTEM: "what kind of food would you like?"
```



### Entity

Used to builds an utterances that can resolve a dynamic value. Entities represent a value that can be provided by the user during their interaction with the system.

In the following example, the entity `{food}` is being matched from the `order_food` intent with what the user said. This value can be extracted for the system to user later during the interaction, such as when responding.

```yaml
USER: "i would like a burrito"
* SYSTEM has recognized "burrito" as a valid value for the "food" entity *
SYSTEM: "what do you want in your burrito?"
```



### Interaction Model

This represents the overall model for all paths that can be taken for designed conversation. It contains the definitions for all intents, utterances and entities.

In essence this is a large state diagram that can be executed to drive a conversational experience.

![](https://files.readme.io/5106d22-interactionmode.png "interactionmode.png")

## Voiceflow-Specific Terms

### Workspace

A collection of _Projects_ shared between multiple collaborators. Each collaborator has their own role within a _Workspace_ which applies to all contained _Projects_.

### Project

A "codebase" for a Voiceflow application. Different types of _Projects_ are limited to target deployment to specific platforms (such as Google Actions and Alexa). Each _Project_ is made up of multiple flows (legacy) as well as topics (new) and components (new).

### Diagram

Each _Diagram_ can contain references to multiple _Blocks_, _Steps_, _Links_ and _Ports_. This graph structure is used as the basis for more concrete concepts such as _Topics_ and _Components_. _Diagrams_ can be referenced by the _Steps_ that appear within them or other _Diagrams_ in the same _Project_.

### Flow (Legacy)

_Flows_ are a type of _Diagram_.

_Flows_ are used for organizing _Projects_ as well as for encapsulation. Every _Flow_ other than the "Home" _Flow_ has its own separate set of variables. The “Home” _Flow_ must contains a start _Block_ which is the entry point for the conversation.

### Topic

_Topics_ are a type of _Diagram_.

_Topics_ are used for organizing the logic in _Projects_ into related collections of functionality. This paradigm is meant to encourage users to design projects with multiple top-level intents.

### Component

_Components_ are a type of _Diagram_.

_Components_ are used for creating reusable logic and functionality. A single _Component_ can be referenced multiple times throughout a _Project._

### Diagrams vs. Programs

_Diagrams_ can be thought of as the "uncompiled" code of a _Project_. A _Project_ is visually represented in the _Canvas_ as linked _Blocks_ and _Steps._ A _Diagram_ is the data structure behind this view and is stored in _MongoDB_.

_Programs_ can be thought of as the "compiled" code of a _Project_, which gets executed by our `runtime` services. As an analogy, in C++, _Diagrams_ are like `.cc` source code files and _Programs_ are the compiled `.exe` executables.

### Variable

Used to store any runtime information for the connected assistant. It can be accessed from the code _Step_ for direct manipulation, or through the set and condition _Steps_ for simpler operations.

## Canvas

The container that renders all of the _Blocks_, _Steps_, _Links_ and _Ports_. It allows panning and zooming and many more advanced interactions.

![](https://files.readme.io/ce65701-Screen_Shot_2022-02-23_at_1.44.37_PM.png "Screen Shot 2022-02-23 at 1.44.37 PM.png")

### Block

A container for one or more _Steps_. Each _Step_ is implicitly linked to the next one to form a sequence of operations.

### Step

The smallest unit of user-defined functionality in the platform. Each _Step_ along a path will be executed sequentially during a conversation.

### Port

The starting point for drawing _Links_ between _Steps_. Some _Steps_ have a configurable number of _Ports_ while others have no _Ports_ at all.

![](https://files.readme.io/b03f76a-Screen_Shot_2022-02-23_at_1.51.51_PM.png "Screen Shot 2022-02-23 at 1.51.51 PM.png")

### Link

Used to connect a _Port_ to another _Step_ or _Block_. Links allows _Steps_ that are not in the same _Block_ to be executed in sequence. Some _Steps_ have logic that allow for multiple _Links_ to be defined, each with its own target _Step_.

![](https://files.readme.io/cd6e1a4-Screen_Shot_2020-06-24_at_7.37.42_PM.png "Screen_Shot_2020-06-24_at_7.37.42_PM.png")