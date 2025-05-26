---
title: Train NLU
excerpt: Uses utterances and entities from your project
api:
  file: nlu-training.json
  operationId: post_publish-projectid
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: Run inference on your NLU with NLU Inference API
---
# What is a NLU?

A NLU is a Machine Learning model that powers conversational assistants. 

# What is Voiceflow NLU?

Voiceflow NLU is a powerful model that is quick to train and supports 30+ languages. Just add data, and train in the UI or API and you'll have a strong model that will power your chatbot. Use it with your Voiceflow project, DM API or any API accessible system to do intent and entity classification.

# Steps to train the NLU

1. Create a project in Voiceflow
2. Add your intents, utterances and entities.
   1. You can add them by importing a .vf file
   2. Manually adding via the GUI
3. Use this end point to train the project
4. Poll the API for the job status to see when the NLU is done training
5. Call the Inference API to see the results

# Benchmarking the VFNLU

If you're interested in comparing the VFNLU to other vendors, you can run your own projects through this api or with some helper code at [https://github.com/voiceflow/vfnlu-tests/tree/main/src/benchmarks](https://github.com/voiceflow/vfnlu-tests/tree/main/src/benchmarks)

![](https://files.readme.io/f288eda-image.png)
