---
title: How to get your Voiceflow Project API key
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

To use the Voiceflow APIs, the first thing you need is your API key. It's specific to each agent instead of for your whole account.

First, open your agent. Then go to Integrations > API Keys and copy your API key.

![](https://files.readme.io/e81b40a-CleanShot_2024-07-15_at_14.47.382x.png)

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