---
title: Amazon Lex V1
excerpt: Overview of sample Amazon Lex connector
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Building a Connector

Connectors are used to convert a Voiceflow project into a format that can be used in other platforms. To build a connector, you will need to extract the relevant data from a Voiceflow project (.vf file) and transform it into the desired format.

> 📘 Recommended reading
>
> 1. **Voiceflow Project Data Structure:**[Link](https://developer.voiceflow.com/docs/voiceflow-project-data-structure)
> 2. **Project API:** [Link](https://developer.voiceflow.com/reference/fetchproject)

# Sample Connector

Find the sample Voiceflow to Amazon Lex V1 exporter [here](https://github.com/voiceflow/lex-demo/tree/master/lib/export). **This is a starter template which you can build upon to best suit your conversation design system between Voiceflow and Amazon Lex.**

# Overview

This repo contains a set of functions that allow for exporting an Amazon Lex V1 bot from a Voiceflow project. The process involves reading the project data, parsing the data, and then generating the Lex V1 bot.

# Usage

Please note that this codebase only works for the V1 version of Amazon Lex.

This is a demonstration of translating a Voiceflow project into parameters for a Lex Bot or any other format.

### Setup

Create a Voiceflow project that has intent events and output steps following it (speak, text, or card steps).\
Export the Voiceflow project as a (.vf) file.

![Screen Shot 2023-01-26 at 5 18 36 PM](https://user-images.githubusercontent.com/5643574/214963509-9c5a9b33-d069-41af-9729-1117ac436a2c.png)

You can leave this file where convenient (\~/Desktop, \~/Downloads, \~/Documents etc.).

[NodeJS](https://nodejs.org/en/) and [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm/) are required.

On the root level of this repository,

1. execute `npm install` to install all dependencies
2. execute `npm run export [PATH TO FILE]`

where `[PATH TO FILE]` is where the .vf file was saved earlier.\
If the file was called `project.vf` was on my Desktop, it would be `npm run export ~/Desktop/project.vf`

This will produce a `.zip` file with the same name, for example `project.vf` -> `project.zip`. This file contains various intents that can be added to the Lex bot.

## Files

### `index.ts`

This file is the main entry point for the script. It reads the project data, parses it, and generates the Lex bot.

### `intent.ts`

This file contains functions related to converting Voiceflow intents to Lex intents.

### `types.ts`

This file contains type definitions used throughout the project.

### `diagram.ts`

This file contains functions related to reading and processing the Voiceflow diagram.

### `steps.ts`

This file contains a mapping of Voiceflow step types to functions that process them.

### `zip.ts`

This file contains functions related to generating the zip file containing the Lex V1 intents.

### `utils.ts`

This file contains utility functions used throughout the project.

## Noteworthy functions

### `voiceflowToLexIntent()`

This function is in the `intent.ts` file and converts a Voiceflow intent into an Amazon Lex intent. It takes two arguments: the Voiceflow intent object and a map of all the slots in the Voiceflow project. The function returns an Amazon Lex intent object that can be included in the exported zip file.

### `getSteps()`

This function is in the `diagram.ts` file and extracts all the steps in a Voiceflow diagram. It takes a Voiceflow diagram object as its only argument and returns an array of step objects.

### `zipIntents()`

This function is in the `zip.ts` file and creates a zip file containing all the Amazon Lex intents in a Voiceflow project. It takes an array of Amazon Lex intent objects as its only argument and returns a zip file stream.

### `getUtterancesWithSlotNames`

This function is from the `@voiceflow/common` module and is used to replace slot references in an utterance with the corresponding slot name. It takes in an array of slots and an array of utterances and returns an array of utterances with slot names.

### `promptToString()`

This function, defined in the `utils.ts` file, takes a prompt object and returns a string representing the prompt that can be used in the valueElicitationPrompt property of a Lex slot. This function is used in the `intent.ts` file to generate the prompts for each Lex slot.

### `voiceflowToLexExport()`

This function is in the `index.ts` file and is the main entry point of the application. It reads a Voiceflow project file, extracts the necessary information, and generates a zip file containing the corresponding Amazon Lex intents.
