---
title: Create Transcript Tag
excerpt: Add a tag to a transcript
api:
  file: project-api.json
  operationId: put_transcripts-projectid-transcriptid-report-tag-reporttagid
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
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

<br />