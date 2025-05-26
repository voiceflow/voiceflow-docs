---
title: Authentication
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
# Dialog Manager API Keys

A Dialog Manager API key is a key with the prefix `VF.DM.`. These keys are the recommended way to access our Dialog Manager API.

# Obtaining a Dialog Manager API Key

To access the `Project API key` for a specific project:

1. Open the project you want to connect with
2. Select on the **Integrations** tab (shortcut: `3`)
3. Copy the Dialog API Key.

<Image title="Screen Shot 2022-02-22 at 9.26.08 AM.png" alt={1919} src="https://files.readme.io/da639c6-Screen_Shot_2022-02-22_at_9.26.08_AM.png">
  Access Project API Key
</Image>

# Using a Version Alias

For the `versionID` header, you should pass in the value:

1. `'development'` for **testing** and **development** purposes
2. `'production'` for **live apps** and **production deployments**
