---
title: Developer Documentation for voiceflowToLexIntent function
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
The voiceflowToLexIntent function is used to convert Voiceflow intents to Lex V1 intents. This is accomplished by mapping the inputs, outputs, and slots of a Voiceflow intent to their corresponding Lex V1 intent properties.

Usage  
typescript  
Copy code  
const lexIntent = voiceflowToLexIntent(  
  intent: BaseModels.Intent,  
  slotsByID: Map\<string, BaseModels.Slot>  
): LexV1Intent;  
Parameters  
intent: A Voiceflow intent object.  
slotsByID: A Map containing Voiceflow slot objects, keyed by their id.  
Return Value  
The voiceflowToLexIntent function returns a LexV1Intent object.

Properties Mapped  
The voiceflowToLexIntent function maps the following properties from a Voiceflow intent to a Lex V1 intent:

name: The sanitized name of the intent.  
description: An empty string.  
fulfillmentActivity: An object with the type property set to "ReturnIntent".  
parentIntentSignature: The Amazon intent name of the intent.  
sampleUtterances: An array of utterances with slot names substituted in.  
slots: An array of slots, where each slot has the following properties:  
name: The name of the slot.  
sampleUtterances: An array of utterances with slot names substituted in.  
slotType: The name of the custom slot type, or the type of the built-in slot type.  
obfuscationSetting: "NONE".  
description: The name of the slot.  
slotConstraint: "Required" or "Optional".  
valueElicitationPrompt: An object containing an array of messages to prompt the user for the slot value and the maxAttempts to prompt the user. If no prompts are required, this property is undefined.  
priority: The priority of the slot.  
slotTypes: An array of custom slot type objects, where each object has the following properties:  
name: The name of the custom slot type.  
enumerationValues: An array of objects, where each object has the value property set to a unique sample from the slot type, and the synonyms property set to an array of synonyms for the sample.  
valueSelectionStrategy: "TOP_RESOLUTION".  
conclusionStatement: An empty array of messages.  
Related Functions  
sanitizeResourceName: Sanitizes a string to conform to the requirements of a Lex resource name.  
getAmazonIntentName: Returns the Amazon intent name of a Voiceflow intent.  
isCustomType: Determines if a slot type is a custom type.  
promptToString: Converts a prompt object to a string.  
getUtterancesWithSlotNames: Returns an array of utterances with slot names substituted in.  
Utils.array.inferUnion: Infers the union type of an array of objects.