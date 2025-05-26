---
title: Fetch Project
excerpt: >-
  Retrieve your Voiceflow project files. It will either be a:
    - `.vf` file which contains all the information of a project including details about blocks and steps in the diagrams.
    - `.vfr` file which includes a more concise version of the project in the `programs` property. We recommend to use this file for any programmatic analysis or integrating with third-party tooling.

  In order to reliably use the `.vfr` file's `programs` property, we recommend
  selecting the "Publish" or "Run" button from the canvas after any updates to
  the project to ensure it is reflected in the file.
api:
  file: project-api-1.json
  operationId: fetchProject
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---