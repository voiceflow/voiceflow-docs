---
title: Authorization
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
# Overview

There are two API key formats that can be used to access the Dialog Manager API.

1. Dialog Manager API keys
2. Workspace API keys 

# Dialog Manager vs. Workspace API Keys

It is **recommended** to use a **Dialog Manager API Key** to access the Dialog Manager API. A DM API key has the prefix `VF.DM.` and provides the most up-to-date features such as version aliasing.

For backwards compatibility reasons, the DM API key accepts Workspace API keys (`VF.WS`) and legacy Workspace API keys (`VF.`). However, the usage of Workspace keys with the DM API key is considered **deprecated** behaviour.

Workspace API keys are unable to resolve version aliases, i.e, passing a string like `'development'` or `'production'` into the `versionID` parameter of DM API endpoints. You would need to provide an explicit version ID, which is harmful for maintainability, because each time your Voiceflow app updates a version, you must manually update to the newest version's ID in your Voiceflow integration.
