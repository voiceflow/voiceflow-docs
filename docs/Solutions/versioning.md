---
title: Version Management
excerpt: Push your design to a production environment
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
Voiceflow supports two workflow states in your project: `draft` and `production`. In this guide, we will be showing how the Dialog Manager API interacts with your project depending on the state. 

By default, 

> 🚧 * You must authenticate your request with the Project API to access your production version

```curl
--header 'versionID: production'
```

This will also save an instance of your Microsoft LUIS instance for use with your production assistant so you can continue making adjustments in your own Dev
