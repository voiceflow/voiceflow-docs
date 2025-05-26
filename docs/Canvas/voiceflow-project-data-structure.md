---
title: Project Data Structure
excerpt: Learn the structure of a Voiceflow project file
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
In his guide, we will cover the composition of the ***Voiceflow Project*** file (`.vf` file)

It's broken up into 3 parts: **Project**, **Version**, and **Diagram**, each of which will be covered here.

<Image title="Frame 18.png" alt={2610} src="https://files.readme.io/4fe9be0-Frame_18.png">
  Voiceflow project file export
</Image>

## Project

**Project** metadata, associated with a particular **team/workspace** 

![2670](https://files.readme.io/ecc700f-project.png "project.png")

* `_id` unique ObjectId Identifying this particular **project**
* `name` name of the project
* `teamID` **team/workspace** that this project belongs to, hash-id string
* `devVersion` ObjectId pointer to the main working **version** on the project
* `platform` the channel of the project *(alexa, google, chatbot, twilio, etc...)*
* `platformData` project metadata for the particular platform type
* `members` distinct metadata for members working on the project -(configurations or settings that different members might have)

...other fields with more additional metadata for various functions

## Version

A **project** can contain many versions, the `devVersion` is the main working version. Versions can be used for staging as well as backups.

![2810](https://files.readme.io/5a1a8d8-versions.png "versions.png")

* `_id` unique ObjectId Identifying this particular version
* `name` name of the version (i.e. "backup save before change X")
* `projectID` project that this version belongs to
* `rootDiagramID` ObjectId pointer to the **home/root diagram**. This is the starting point.
* `platformData` version metadata for the particular platform type
  * `intents`
  * `slots`
* `variables` array of global variable names\
  ...other fields with more additional metadata for various functions

## Diagrams (Topics and Flows)

**Version**: A version contains many diagrams, with the rootDiagram being the entry point during runtime.\
Can find all diagrams of a version searching against the versionID index.

These might also be referred to as topic, or component. Both are types of diagrams. An older name for diagrams is "flow"

**Topics**: topics are all on the same level. Can be thought of as extensions of the home diagram. On runtime they blend together like one giant diagram.

**Components**: components are modular, reusable pieces. You can think of components similar to functions in programming. When a component gets called, it is added to the "call stack", and pops off when it is finished.

* `_id` unique ObjectId Identifying this particular **diagram**
* `name` name of the diagram
* `type` type of diagram: `TOPIC` or `COMPONENT`
* `versionID` **version** that this **diagram** belongs to
* `nodes` dictionary of all the **nodes** in the diagram, referenced by their `nodeID`. This is where most of the data lives.
* `variables` array of diagram-level variable names (local variables)\
  ...other fields with more additional metadata

### Nodes

Every node has:

* unique `nodeID` (only needs to be unique per diagram)
* `type` canonical type of node
* `data` that houses metadata for the node.

> **blocks** or **steps** are types of **nodes**

<Image width="smart" src="https://files.readme.io/be327a6-nodes.png" />

A **block** is comprised of **steps**, and usually, the last **step** in the **block** will have **ports**. There are "implicit" **ports** between **steps** within the same **block**.

A line coming out of a **port** can be connected to another block or **step**.

Special steps might have no ports, or can not be connected to (they are a triggered event)

Markup, images + text on canvas with no functional purpose, are special types of nodes.

#### Blocks

**Blocks** contain a `steps` property in `data` that references their children steps, in this case, a speak step + a choice step are always of `type: block`.

<Image width="smart" src="https://files.readme.io/ebb4e97-block.png" />

Below is what the above "Greetings" block looks like in JSON form.

```json json
"619a67a19eb63ecb29430946": {
  "nodeID": "619a67a19eb63ecb29430946",
  "type": "block",
  "coords": [
    764.7499999999999,
    125
  ],
  "data": {
    "name": "Greetings",
    "color": "blue",
    "steps": [
      "619a67a19eb63ecb29430943",
      "619a67b59eb63ecb2943094f"
    ]
  }
},
```

#### Steps

<Image className="border" width="80%" border={true} src="https://files.readme.io/265607d-Screen_Shot_2021-11-21_at_5.09.16_PM.png" />

See what the "choice" step looks like in JSON form below:

```json json
// simplified version
"619a67b59eb63ecb2943094f": {
  "nodeID": "619a67b59eb63ecb2943094f",
  "type": "interaction",
  "data": {
    "choices": [{
        "intent": "VF.YES", "action": "PATH"
      },{
        "intent": "VF.NO", "action": "PATH"
      }],
    "ports": [{
        "type": "else",
        "target": null,
      },{
        "target": "619a67bc9eb63ecb29430959",
      },{
        "target": "619a67bf9eb63ecb29430967",
      }
    ]
  }
}
```

`type` is the canonical type of the step. There will always be `ports` under the `data`, which target another node. 

Everything else in the `data` is metadata dependent on the particular step type.

## Required Fields

Below are the required fields in the VF file that are needed for successful import.

```json
{
  "project": [
    "name",
    "creatorID",
    "teamID",
    "platform",
    "platformData",
    "members"
  ],
  "version": [
    "creatorID",
    "projectID",
    "name",
    "rootDiagramID",
    "platformData",
    "variables"
  ],
  "diagrams": {
    "[DIAGRAM ID]": [
      "name",
      "versionID",
      "creatorID",
      "variables",
      "offsetX",
      "offsetY",
      "zoom",
      "nodes",
      "modified"
    ]
  }
}
```
