---
title: Dialogflow ES
excerpt: Overview of sample Dialogflow ES connector
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Building a Connector

Connectors are used to convert a Voiceflow <Glossary>agent</Glossary> into a format that can be used in other platforms. To build a connector, you will need to extract the relevant data from a Voiceflow project (.vf file) and transform it into the desired format.

> 📘 Recommended reading
>
> 1. **Voiceflow Project Data Structure:**[Link](https://developer.voiceflow.com/docs/voiceflow-project-data-structure)
> 2. **Project API:** [Link](https://developer.voiceflow.com/reference/fetchproject)

# Sample Connector

Find the sample Voiceflow to Dialogflow ES exporter [here](https://github.com/voiceflow/dfes-export-script-demo). **This is a starter template which you can build upon to best suit your conversation design system between Voiceflow and Dialogflow ES.**

# Overview

This repo contains a set of functions that allow for exporting a Dialogflow ES agent from a Voiceflow project. The process involves reading the project data, parsing the data, and then generating the Dialogflow ES agent.

## Usage

Create a Voiceflow project that has intent events and output steps following it (speak or text steps).\
Export the Voiceflow project as a `.vf` file.

![Screen Shot 2023-01-26 at 5 18 36 PM](https://user-images.githubusercontent.com/5643574/214963509-9c5a9b33-d069-41af-9729-1117ac436a2c.png)

You can leave this file where convenient (`~/Desktop`, `~/Downloads`, `~/Documents`, etc.).

[Node.js](https://nodejs.org/en/) and [Yarn](https://classic.yarnpkg.com/en/docs/install) are required.

On the root level of this repository,

1. Run `yarn install` to install the dependencies
2. Run `yarn build` to compile the tool
3. Run `yarn start [PATH TO FILE]`, or `yarn start` to convert a `project.vf` file stored in this directory

`[PATH TO FILE]` is where the `.vf` file was saved earlier.\
If the file was called `project.vf` was on my Desktop, it would be `yarn start ~/Desktop/project.vf`

This will produce a `.zip` file with the same name (ex. `project.vf` -> `project.zip`).\
This file contains a DFES export containing entities, intents, and their responses.

## Files

### `index.ts`

This file is the main entry point for the script. It reads the project data, parses it, and generates the Dialogflow agent.

### `intent.ts`

This file contains functions related to converting Voiceflow intents to Dialogflow intents.

### `types.ts`

This file contains type definitions used throughout the project.

### `diagram.ts`

This file contains functions related to reading and processing the Voiceflow diagram.

### `entity.ts`

This file contains a mapping of Voiceflow entities to Dialogflow entities.

### `zip.ts`

This file contains functions related to generating the zip file containing the Dialogflow intents.

### `utils.ts`

This file contains utility functions used throughout the project.

## Noteworthy functions

### `main()`

 The main function of the project. It reads the JSON file, converts the Voiceflow intents and entities into their Dialogflow ES equivalents, and then creates a Dialogflow ES agent using these converted intents and entities.

### `voiceflowToDFESIntent()`

 This function converts a Voiceflow intent into its Dialogflow ES equivalent.

### `generateDFESUtterancesForIntent()`

This function generates Dialogflow ES utterances for a given Voiceflow intent.

### `voiceflowToDFESEntity()`

This function converts a Voiceflow entity into its Dialogflow ES equivalent.

### `getDFESSlotType()`

This function returns the Dialogflow ES slot type for a given Voiceflow slot.

### `sanitizeResourceName()`

This function sanitizes a resource name to remove any invalid characters.
