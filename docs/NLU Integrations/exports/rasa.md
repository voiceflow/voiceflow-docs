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
## Quick Reference

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Data
      </th>

      <th style={{ textAlign: "left" }}>
        Support
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        File format
      </td>

      <td style={{ textAlign: "left" }}>
        YAML and PY
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **Data Support**
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Intents
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Training Phrases
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Entities
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Synonyms
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **Import Type** 
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Modify
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Overwrite
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>
  </tbody>
</Table>

## Video Walkthrough

<Embed url="https://www.youtube.com/watch?v=wq7ca-NvsrA&feature=youtu.be" title="Voiceflow Tutorials | RASA Export" favicon="https://www.youtube.com/s/desktop/ecd7151d/img/favicon.ico" image="https://i.ytimg.com/vi/wq7ca-NvsrA/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=wq7ca-NvsrA&feature=youtu.be" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252Fwq7ca-NvsrA%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253Dwq7ca-NvsrA%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252Fwq7ca-NvsrA%252Fhqdefault.jpg%26key%3Df2aa6fc3595946d0afc3d76cbbd25dc3%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## Sample Intent Export

```yaml intent.yaml
nlu:
  - intent: spell_intent
    examples: |
      - sure [DOG](spell)
      - sure [CAR](spell)
      - sure [HOUSE](spell)
      - sure [ROCK](spell)
      - sure [PIZZA](spell)
      - sure [FRIDGE](spell)
      - its [DOG](spell)
      - its [CAR](spell)
      - its [HOUSE](spell)
      - its [ROCK](spell)
      - its [PIZZA](spell)
      - its [FRIDGE](spell)
  - intent: noanswer_intent
    examples: |
      - it's too hard
      - I can't spell that word
      - I don't know how to spell it
  - intent: VF.NO
    examples: |
      - no
      - nope
      - nay
      - nah
      - no way
      - negative
  - intent: VF.YES
    examples: |
      - yes
      - yea
      - ok
      - okay
      - yup
      - ya
      - sure
  - synonym: DOG
    examples: |
      - d. o. g.
      - d o g
  - synonym: CAR
    examples: |
      - c. a. r.
      - c a r
  - synonym: HOUSE
    examples: |
      - h. o. u. s. e.
      - h o u s e
  - synonym: ROCK
    examples: |
      - r. o. c. k.
      - r o c k
  - synonym: PIZZA
    examples: |
      - p. i. z. z. a.
      - p i z z a
  - synonym: FRIDGE
    examples: |
      - f. r. i. d. g. e.
      - f r i d g e
```
