---
title: Create Transcript
excerpt: >-
  Creates a transcript recording the conversation between the user with `userID`
  and your Voiceflow assistant corresponding to the version with `versionID`.



  A transcript includes three fields: `os`, `browser`, `device`, which accept
  any string value. You can use these properties to record additional metadata
  about the conversations.
api:
  file: project-api.json
  operationId: put_transcripts
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