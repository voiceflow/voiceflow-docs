---
title: Authorization
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Overview

Dialog Manager API Keys are currently the only supported format for API Keys that the Dialog Manager accepts.

# Dialog Manager API Keys

It is **required** to use a **Dialog Manager API Key** to access the Dialog Manager API. A DM API key has the prefix `VF.DM.` and provides the most up-to-date features such as version aliasing.

You need to pass this key in the Authorization header of each request.

```
Authorization: VF.DM.XXXXXXXXX
```