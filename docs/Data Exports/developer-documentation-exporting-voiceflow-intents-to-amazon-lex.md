---
title: 'Developer Documentation: Exporting Voiceflow Intents to Amazon Lex'
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The code example provided is a Node.js script that exports Voiceflow intents to Amazon Lex. The script takes in a Voiceflow project file (.vf) as input and generates a zip file containing the Lex intents. The zip file can then be imported into Amazon Lex to create the corresponding intents.

Dependencies\
The script relies on the following dependencies:

@voiceflow/voiceflow-types: Voiceflow platform types.\
@voiceflow/base-types: Base types used across Voiceflow.\
fs: Node.js file system module for reading and writing files.\
path: Node.js module for working with file paths.\
./types: Custom type definitions for the project.\
./diagram: A function that extracts the steps from a Voiceflow diagram.\
./intent: A function that converts a Voiceflow intent to a Lex intent.\
./steps: An object that maps Voiceflow step types to functions that handle the steps.\
./zip: A function that zips the Lex intents.\
./utils: Utility functions used across the script.\
Usage\
The script can be run with the following command:

arduino\
Copy code\
node export.js [inputFilePath]\
where inputFilePath is the path to the Voiceflow project file (.vf). If inputFilePath is not provided, the script will default to "project.vf".

Steps\
The script performs the following steps:

Reads the input Voiceflow project file and extracts the platform data and diagrams.\
Creates a map of Voiceflow intents and slots from the platform data.\
Loops over all diagrams and their steps, and for each intent step, converts the Voiceflow intent to a Lex intent and applies the relevant slot mappings.\
Zips the Lex intents into a file and saves it to the same directory as the input file.\
Variables\
The script uses the following variables:

args: An array of command-line arguments.\
readFilePath: The path to the input file.\
readFileDirectory: The directory of the input file.\
readFileName: The name of the input file.\
content: The contents of the input file.\
platformData: The platform data from the input file.\
diagrams: The diagrams from the input file.\
intentMap: A map of Voiceflow intents.\
slotMap: A map of Voiceflow slots.\
lexIntents: An array of Lex intents.\
exportFileName: The name of the output file.\
writePathName: The path of the output file.\
Functions\
The script uses the following functions:

JSON.parse: Parses a JSON string into a JavaScript object.\
fs.readFileSync: Reads a file synchronously.\
path.parse: Parses a file path into an object containing the file's directory, name, and extension.\
console.log: Logs a message to the console.\
Map: A built-in JavaScript object that maps keys to values.\
Object.values: Returns an array of the object's values.\
forEach: Calls a function for each element in an array.\
getSteps: Extracts the steps from a Voiceflow diagram.\
voiceflowToLexIntent: Converts a Voiceflow intent to a Lex intent.\
StepHandlerMap: A map of Voiceflow step types to functions that handle the steps.\
zipIntents: Zips the Lex intents into a file.\
generateNodeStream: Generates a readable stream of the zip file.\
fs.createWriteStream: Creates a writable stream to write the zip file.

Outputs

This script generates a .zip file containing the exported Amazon Lex intents. The name of the zip file is the same as the name of the input .vf file, with a .zip extension appended to it. The .zip file is saved in the same directory as the input file.
