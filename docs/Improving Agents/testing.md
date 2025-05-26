---
title: Testing Intents and Entities
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
![](https://files.readme.io/9b9f520-image.png)

In this tutorial you'll learn how to test your NLU focused on intent and entities.

### Step 0 - Clone your repo

Clone the [nlu-testing-example](https://github.com/voiceflow/nlu-testing-example)

### Step 1 - Create your <Glossary>agent</Glossary>

Create your agent, through scratch or the [NLU\_test\_v1.vf](https://github.com/voiceflow/nlu-testing-example/blob/master/examples/NLU_test_v1.vf)

![](https://files.readme.io/617e57c-image.png)

### Step 2 - Train your model

Navigate to the prototype on the right hand side, and train your model.

![](https://files.readme.io/0b257e4-image.png)

### Step 3 - Create your dialog manager api key

Create your DM API key

![](https://files.readme.io/7c7b267-image.png)

### Step 4 - Open examples/voiceflow\.py

Paste your key and run the file

![](https://files.readme.io/81f50d8-Screen_Shot_2022-09-01_at_6.48.56_PM.png)

### Step 5 - Check your results

Open the `examples/utterance_results.csv` and `examples/entity_results.csv`to see your results.

![](https://files.readme.io/237509e-Screen_Shot_2022-09-01_at_7.40.01_PM.png)

### Step 6 - Update your training data and retrain

Add utterances to address the *poutine test* example and the *assist me* example. You can also just upload [NLU\_test\_v2.vf](https://github.com/voiceflow/nlu-testing-example/blob/master/examples/NLU_test_v2.vf) as a new project and create the new dialog manager api key.

![](https://files.readme.io/8bb54f8-image.png)

All your test cases pass!

### Video Tutorial

<HTMLBlock>{`
<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/83f26874d5e74429bce69a4406b406ef" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>
