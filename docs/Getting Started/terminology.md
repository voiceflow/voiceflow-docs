---
title: Key concepts and terms
excerpt: Learn the terms used in these docs and in Voiceflow.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Industry terms

### Dialog Management

A design system that offers a flexible way to design customer-centric, conversational experiences. This system involves designing and managing the state of the dialog between your <Glossary>Agent</Glossary> and customer.

### Utterance

An utterance is a phrase that a user might say (or type) to interact with an agent.

The following are all examples of utterances for an `order_food` intent.

```yaml
INTENT: "order_food"
	- "i am feeling hungry"
	- "i want takeout"
	- "i would like {food}"
```

### Intent

An intent represents an action that a user might want to take. Each intent includes a collection of associated utterances. These utterances will be analyzed to determine whether a user triggers the associated intent with any of their interactions.

In the following example, the user has used one of the utterances of an `order_food` intent and the system responds accordingly.

```yaml
USER: "i want takeout"
* SYSTEM has recognized this utterance as part of the "order_food" intent *
SYSTEM: "what kind of food would you like?"
```

### Entity

Used to builds an utterance that can resolve a dynamic value. Entities represent a value that can be provided by the user during their interaction with the system.

In the following example, the entity `{food}` is being matched from the `order_food` intent with what the user said. This value can be extracted for the system to user later during the interaction, such as when responding.

```yaml
USER: "i would like a burrito"
* SYSTEM has recognized "burrito" as a valid value for the "food" entity *
SYSTEM: "what do you want in your burrito?"
```

### Interaction Model

This represents the overall model for all paths that can be taken for designed conversation. It contains the definitions for all intents, utterances, and entities.

In essence, this is a large state diagram that can be executed to drive a conversational experience.

![](https://files.readme.io/5106d22-interactionmode.png "interactionmode.png")

## Voiceflow specific terms

### Workspace

A collection of *agents* shared between multiple collaborators. Each collaborator has their own role within a *Workspace* which applies to all contained *agents*.

### Agent

Refers to one project in your Workspace. Also used interchangeably with the term “assistant” and “project”. A “codebase” for a Voiceflow application. Each *Project* is made up of NLU training, response and logic data. Response and logic data are represented by flows, topics, and components.

### Diagram

The technical word for the flows that your agent contains. Each *Diagram* can contain references to multiple *Blocks*, *Steps*, *Links,* and *Ports*. This graph structure is used as the basis for more concrete concepts, such as *Topics* and *Components*. *Diagrams* can be referenced by the *Steps* that appear within them or other *Diagrams* in the same *Project*.

### Workflow

*Workflows* are the non-technical word for *Diagram*.

*Workflows* are used for organizing *agents* as well as for encapsulation. Every *Workflow* other than the “Home” *Workflow* has its own separate set of variables. The “Home” *workflow* must contain a start *Block* which is the entry point for the conversation.

### Component

*Components* are a type of *Diagram*.

*Components* are used for creating reusable logic and functionality. A single *Component* can be referenced multiple times throughout a *Project.*

### Diagrams vs. Programs

*Diagrams* can be thought of as the source code of a *Project*. A *Project* is visually represented in the *Canvas* as linked *Blocks* and *Steps.* A *Diagram* is the data structure behind this view and is stored in *MongoDB*.

*Programs* can be thought of as the “compiled” code of a *Project*, which gets executed by our `runtime` services. As an analogy, in C++, *Diagrams* are like `.cc` source code files and *Programs* are the compiled `.exe` executables.

### Variable

Used to store any runtime information for the connected agent. It can be accessed from the code *Step* for direct manipulation, or through the set and condition *Steps* for simpler operations.

## Canvas

The container that renders all the *Blocks*, *Steps*, *Links*, and *Ports*. It allows panning and zooming and many more advanced interactions.

![](https://files.readme.io/ce65701-Screen_Shot_2022-02-23_at_1.44.37_PM.png "Screen Shot 2022-02-23 at 1.44.37 PM.png")

### Block

A container for one or more *Steps*. Each *Step* is implicitly linked to the next one to form a sequence of operations.

### Step

The smallest unit of user-defined functionality in the platform. Each *Step* along a path will be executed sequentially during a conversation.

### Port

The starting point for drawing *Links* between *Steps*. Some *Steps* have a configurable number of *Ports* while others have no *Ports* at all.

![](https://files.readme.io/b03f76a-Screen_Shot_2022-02-23_at_1.51.51_PM.png "Screen Shot 2022-02-23 at 1.51.51 PM.png")

### Link

Used to connect a *Port* to another *Step* or *Block*. Links allows *Steps* that are not in the same *Block* to be executed in sequence. Some *Steps* have logic that allow for multiple *Links* to be defined, each with its own target *Step*.

![](https://files.readme.io/cd6e1a4-Screen_Shot_2020-06-24_at_7.37.42_PM.png "Screen_Shot_2020-06-24_at_7.37.42_PM.png")
