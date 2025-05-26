---
title: Production
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
Voiceflow allows to publish a version of your project to a production slot. Publishing "freezes" a version of your project, so that you have a stable copy of the project to serve to your users.

To publish a project through the Voiceflow Creator, see the following [documentation](https://www.voiceflow.com/docs/documentation-project-versioning#toc-2).

You can access this production version through the DM API, by setting your `versionID` header to the string `'production'`. 

Once this is done, you can freely edit the diagram on canvas, without affecting the version that users see on your live application. If you want to update the production version, click the Publish button on the Voiceflow Creator again as described in the documentation linked above. This will replace the previous production version with the version displayed on your canvas.

**NOTE**: For the `'development'` alias, you must hit the Run button to compile the version and click the "Train Assistant" button in the Prototype tool to update the project's NLU. For `'production'`, doing all of this is unnecessary. The Publish button is a one-click flow that includes the compilation and training steps so that your live app will have the most recent diagram structure and NLU model.
