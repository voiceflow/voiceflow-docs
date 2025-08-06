---
title: How to get your Voiceflow API key
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
> 📘 This article is part of a guide on getting started with Voiceflow APIs
>
> Start from the [beginning](https://docs.voiceflow.com/reference/api-guide-start) here.

To use Voiceflow APIs, the first thing you need is your API key. The same Voiceflow Project API key can be used for all Voiceflow APIs.

<Callout icon="❗️">
  Every Voiceflow Project has its own unique API key.
</Callout>

### Find your Voiceflow API Key

1. Open your Voiceflow Project
2. Open 'Settings', then go to 'API Keys'
3. Your 'primary key' is your Project's API key
4. Copy it - and you're good to go!

<Image align="center" src="https://files.readme.io/daa782632b0a50a4ca43f97ee6db8ba4e77db04d7f90208aa983f432a265c175-Screenshot_2025-08-06_at_12.02.26_AM.png" />

<br />

To learn more about API keys, see this [article](https://developer.voiceflow.com/reference/authentication) about authentication.

👉 Copy your API key and add it as a constant at the top of your Python file.

```python
import requests

api_key = 'YOUR_API_KEY_HERE' # it should look like this: VF.DM.XXXXXXX.XXXXXX... keep this a secret!
```
```javascript
const axios = require('axios');

const api_key = 'YOUR_API_KEY_HERE'; // it should look like this: VF.DM.XXXXXXX.XXXXXX... keep this a secret!
```

> 📘 Next up: [Using the Dialog Manager API (DM API)](https://docs.voiceflow.com/reference/api-guide-dmapi-setup)