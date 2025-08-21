---
title: Create Utterance Annotation
excerpt: >-
  Marks a "no match" intent as being fixed by signaling that a new utterance has
  been aded to the given intent
api:
  file: project-api.json
  operationId: put_transcripts-projectid-transcriptid-annotation-utteranceaddedto
deprecated: true
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<Callout icon="❗️" theme="error">
  We don't recommend building new tooling with this API endpoint as it's for the old transcripts system. Voiceflow released a new transcript system on July 28th, 2025.

  While this endpoint will remain available in the immediate future, allowing you to pull previously generated transcripts, all new transcripts are available via the new [Transcripts API](ref:transcripts-api).
</Callout>