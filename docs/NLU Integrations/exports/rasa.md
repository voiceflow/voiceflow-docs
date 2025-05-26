---
title: Rasa
excerpt: Learn how to use our NLU export with Rasa
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
[block:api-header]
{
  "title": "Quick Reference"
}
[/block]

[block:parameters]
{
  "data": {
    "0-0": "File format",
    "0-1": "YAML and PY",
    "1-0": "**Data Support**",
    "2-0": "Intents",
    "2-1": "✅",
    "3-1": "✅",
    "4-1": "✅",
    "5-1": "✅",
    "3-0": "Training Phrases",
    "4-0": "Entities",
    "5-0": "Synonyms",
    "6-0": "**Import Type** ",
    "7-0": "Modify",
    "7-1": "✅",
    "h-0": "Data",
    "h-1": "Support",
    "8-0": "Overwrite",
    "8-1": "✅"
  },
  "cols": 2,
  "rows": 9
}
[/block]

[block:api-header]
{
  "title": "Video Walkthrough"
}
[/block]

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2Fwq7ca-NvsrA%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3Dwq7ca-NvsrA&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2Fwq7ca-NvsrA%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=wq7ca-NvsrA&feature=youtu.be",
  "title": "Voiceflow Tutorials | RASA Export",
  "favicon": "https://www.youtube.com/s/desktop/ecd7151d/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/wq7ca-NvsrA/hqdefault.jpg"
}
[/block]

[block:api-header]
{
  "title": "Sample Intent Export"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "nlu:\n  - intent: spell_intent\n    examples: |\n      - sure [DOG](spell)\n      - sure [CAR](spell)\n      - sure [HOUSE](spell)\n      - sure [ROCK](spell)\n      - sure [PIZZA](spell)\n      - sure [FRIDGE](spell)\n      - its [DOG](spell)\n      - its [CAR](spell)\n      - its [HOUSE](spell)\n      - its [ROCK](spell)\n      - its [PIZZA](spell)\n      - its [FRIDGE](spell)\n  - intent: noanswer_intent\n    examples: |\n      - it's too hard\n      - I can't spell that word\n      - I don't know how to spell it\n  - intent: VF.NO\n    examples: |\n      - no\n      - nope\n      - nay\n      - nah\n      - no way\n      - negative\n  - intent: VF.YES\n    examples: |\n      - yes\n      - yea\n      - ok\n      - okay\n      - yup\n      - ya\n      - sure\n  - synonym: DOG\n    examples: |\n      - d. o. g.\n      - d o g\n  - synonym: CAR\n    examples: |\n      - c. a. r.\n      - c a r\n  - synonym: HOUSE\n    examples: |\n      - h. o. u. s. e.\n      - h o u s e\n  - synonym: ROCK\n    examples: |\n      - r. o. c. k.\n      - r o c k\n  - synonym: PIZZA\n    examples: |\n      - p. i. z. z. a.\n      - p i z z a\n  - synonym: FRIDGE\n    examples: |\n      - f. r. i. d. g. e.\n      - f r i d g e",
      "language": "yaml",
      "name": "intent.yaml"
    }
  ]
}
[/block]