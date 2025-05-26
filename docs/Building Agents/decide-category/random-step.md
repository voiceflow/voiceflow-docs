---
title: Random step
excerpt: How do I present random or randomize paths to my users?
deprecated: true
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
If you want to add some variation or unpredictability in your conversation design and want the user to have a unique experience, you may want to consider the Random Step. It's also commonly used for teams doing A/B testing.

The Random step allows you to randomize the conversation paths to be taken at a specific point in your conversation. This allows the user to take a randomized path defined in your conversation. All the outputs of the random step are equally probable. To change probabilities, consider using some simple code in the [JavaScript](https://developer.voiceflow.com/docs/javascript-step) step.

![](https://files.readme.io/d49610b-image.png)

## Creating Random Paths

The Random step, operates similarly to configuring paths on Choice/Buttons and/or Condition Step(s).

Creating and deleting random paths can be done by clicking **Add path** within the Random step's editor.

## Limit/Prohibit Duplicate Random Paths

The **No duplicates** toggle ensures that the user does not go down the same path twice, even if the same Random step is activated multiple times.

Once all the options have been hit, the Random step will reset.

Ex. If there are 3 random options, the no duplicates option will not activate the same path twice in a row until all the options have been taken. Once all the options have been hit, the Random step will reset.
