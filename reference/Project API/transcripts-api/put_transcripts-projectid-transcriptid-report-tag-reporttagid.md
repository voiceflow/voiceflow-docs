---
title: Create Transcript Tag
excerpt: Add a tag to a transcript
api:
  file: project-api.json
  operationId: put_transcripts-projectid-transcriptid-report-tag-reporttagid
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

## Examples

This creates a tag that can be applied to your transcripts.

```Text JSON
curl --request PUT  
  --url <https://api.voiceflow.com/v2/projects/66667c820c5aef4fa4bc173a/tags>  
  --header 'Authorization: VF.DM.XYZ'  
  --header 'content-type: application/json'  
  --data '{"label":"your tag"}'
```

This lists returns all tags available in your project

```Text JSON
curl --request GET  
  --url <https://api.voiceflow.com/v2/projects/66667c820c5aef4fa4bc173a/tags>  
  --header 'Authorization: VF.DM.XWZ'
```