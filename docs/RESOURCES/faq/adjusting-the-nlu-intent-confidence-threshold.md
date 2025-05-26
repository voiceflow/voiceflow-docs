---
title: Adjusting the NLU Intent Confidence Threshold
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
When a NLU matches to an intent it outputs two pieces of information, the main intent it matched to and its confidence. **Confidence** shows how likely a certain intent is, between 0-100%.  

To adjust your Intent Confidence Threshold, head over to the Intent page of the **Agent CMS**. Hit the ⚙️ icon in the header and adjust your threshold.

**A higher threshold** reduces false positives, meaning matches to an unrelated intent.

**A lower threshold** reduces false negatives, meaning missed matches.

![](https://files.readme.io/1392542-image.png)

| 60% Confidence threshold - Match               | 95% Confidence threshold - No Match            |
| :--------------------------------------------- | ---------------------------------------------- |
| ![](https://files.readme.io/a95d19b-image.png) | ![](https://files.readme.io/7dab397-image.png) |
