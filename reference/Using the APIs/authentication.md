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

An Agent API key (also sometimes referred to as a Dialog Manager API key) is a key with the prefix `VF.DM.`. These keys are how you can access all the APIs related to your project.

# Obtaining an Agent API key

To access the Agent API key for a specific project:

1. Open the agent you want to connect with
2. Click on the **Settings** icon (shortcut: `7`)
3. Click on the **API keys** section
4. Copy the key.
   1. You can also generate secondary Agent API keys for API key rotations (so you can always have one valid key up). After rotating your API keys, you should immediately **promote** the secondary key to primary.

<Image align="center" border={false} src="https://files.readme.io/acbdcf799c7c93597dae3e53d1423a99a1e76c6bc561553846ba2ce32b483173-CleanShot_2025-10-07_at_14.24.512x.png" />

> 📘 Remember, you can always revoke and re-generate a new Agent API key from this same integrations tab in case it's exposed.

# Using a Version Alias

For the `versionID` header, you should pass in the value:

1. `'development'` for **testing** and **development** purposes
2. `'production'` for **live apps** and **production deployments**
