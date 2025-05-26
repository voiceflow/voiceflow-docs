---
title: Authentication
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
# Agent API key

A Dialog Manager API key is a key with the prefix `VF.DM.`. These keys are the recommended way to access our Dialog Manager API.

# Obtaining an Agent API key

To access the `API key` for a specific agemt:

1. Open the agent you want to connect with
2. Select on the **Integrations** tab (shortcut: `3`)
3. Copy the API key.

# Using a Version Alias

For the `versionID` header, you should pass in the value:

1. `'development'` for **testing** and **development** purposes
2. `'production'` for **live apps** and **production deployments**