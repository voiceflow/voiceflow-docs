---
title: Get Transcript Dialog
excerpt: >-
  Get the transcript dialogs for the given projectID/transcriptID. This holds
  all the traces of the conversation that have been generated. The `limit` and
  `offset` parameters can be used to paginate the results.
api:
  file: project-api.json
  operationId: get_transcripts-projectid-transcriptid
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