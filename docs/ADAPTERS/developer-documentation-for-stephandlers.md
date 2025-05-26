---
title: Developer Documentation for StepHandlers
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
Overview  
This companion file provides a set of StepHandlers that can be used to convert a Voiceflow project into a LexV1Intent. Each StepHandler function takes in a step of a specific type from a Voiceflow project and a LexV1Intent object. The StepHandler updates the LexV1Intent object with the necessary data from the Voiceflow step and returns the next target in the Voiceflow project.

Usage  
StepHandlers  
There are four StepHandlers provided in this file:

IntentHandler: Used for handling Intent nodes in a Voiceflow project.  
SpeakHandler: Used for handling Speak nodes in a Voiceflow project.  
TextHandler: Used for handling Text nodes in a Voiceflow project.  
CardHandler: Used for handling Card nodes in a Voiceflow project.  
StepHandlerMap  
This file also exports a StepHandlerMap object that maps each node type to its corresponding StepHandler function. The StepHandlerMap can be used in combination with a Program object from the @voiceflow/voice-types package to iterate through each step in the program and apply the appropriate StepHandler function.

Functions  
IntentHandler(step: BaseNode.Intent.Step, lexIntent: LexV1Intent, context: { groupNumber: number }): string  
This function takes in a BaseNode.Intent.Step object, a LexV1Intent object, and a context object containing the groupNumber. The function updates the LexV1Intent object with the appropriate data from the BaseNode.Intent.Step object and returns the next target in the Voiceflow project.

SpeakHandler(step: VoiceNode.Speak.Step, lexIntent: LexV1Intent, context: { groupNumber: number }): string  
This function takes in a VoiceNode.Speak.Step object, a LexV1Intent object, and a context object containing the groupNumber. The function updates the LexV1Intent object with the appropriate data from the VoiceNode.Speak.Step object and returns the next target in the Voiceflow project.

TextHandler(step: BaseNode.Text.Step, lexIntent: LexV1Intent, context: { groupNumber: number }): string  
This function takes in a BaseNode.Text.Step object, a LexV1Intent object, and a context object containing the groupNumber. The function updates the LexV1Intent object with the appropriate data from the BaseNode.Text.Step object and returns the next target in the Voiceflow project.

CardHandler(step: BaseNode.CardV2.Step, lexIntent: LexV1Intent): string  
This function takes in a BaseNode.CardV2.Step object and a LexV1Intent object. The function updates the LexV1Intent object with the appropriate data from the BaseNode.CardV2.Step object and returns the next target in the Voiceflow project.

StepHandlerMap: Record\<string, StepHandler>  
This object maps each node type to its corresponding StepHandler function. The keys of the object correspond to the type property of each node in a Voiceflow program, and the values correspond to the appropriate StepHandler function for that node type. This object can be used to iterate through a Voiceflow program and apply the appropriate StepHandler function to each step.