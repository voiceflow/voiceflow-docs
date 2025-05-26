---
title: Workspace API Key
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
# Workspace API Keys

A Workspace API key has the prefix `VF.` (legacy format) or `VF.WS`. Workspace API keys provide workspace-scoped authentication and can be used to access any Dialog Manager API project, if you have provided the right ID to the `versionID` header.

# Obtaining a Workspace API Key

1. Navigate to **Worksplace Settings** under the ⚙ icon.

<Image title="Screen Shot 2022-02-22 at 8.53.09 AM.png" alt={1922} src="https://files.readme.io/83dbedd-Screen_Shot_2022-02-22_at_8.53.09_AM.png">
  Access Workspace Settings
</Image>

2. Select **Developer** tab in the right-hand pane.
3. Select **Create New API Key** to create a new key.

<Image title="Screen Shot 2022-02-22 at 8.53.30 AM.png" alt={1920} src="https://files.readme.io/2caf39a-Screen_Shot_2022-02-22_at_8.53.30_AM.png">
  Developer Workspace Settings
</Image>

4. Name your API Key. 

<Image title="Screen Shot 2022-02-22 at 8.53.45 AM.png" alt={1920} src="https://files.readme.io/11d64b7-Screen_Shot_2022-02-22_at_8.53.45_AM.png">
  Name API Key
</Image>

5. Copy your API Key

> 🚧 Immediately store your credentials in a safe place
>
> It's very important you save your API key somewhere secure as you won't be able to access it again after creation.

<Image title="Screen Shot 2022-02-22 at 8.54.03 AM.png" alt={1920} src="https://files.readme.io/44d1c77-Screen_Shot_2022-02-22_at_8.54.03_AM.png">
  Capture API Key
</Image>

# Obtaining the Version ID

To point the Dialog Manager at the appropriate project, next you will need to find your `versionID`. 

1. Open the project you want to integrate

![](https://files.readme.io/c9e2525-Screen_Shot_2022-02-22_at_9.16.11_AM.png "Screen Shot 2022-02-22 at 9.16.11 AM.png")

2. Copy the `versionID` from the URL in your address bar. Inside of a Voiceflow project, your address bar has a URL of the form: `https://creator.voiceflow.com/project/{versionID}/...`

![](https://files.readme.io/36e6129-Screen_Shot_2022-02-22_at_9.16.33_AM.png "Screen Shot 2022-02-22 at 9.16.33 AM.png")

# Making a Request

1. Paste your API key in the `Authorization` header of any Dialog Manager requests
2. Paste your project's version ID into the `versionID` header of any Dialog Manager requests

Your requests should now have the proper credentials and produce the responses from your selected project!
