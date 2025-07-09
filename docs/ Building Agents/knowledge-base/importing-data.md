---
title: Importing Data
deprecated: false
hidden: false
metadata:
  robots: index
---
# 🚪 Ways to Import

Voiceflow supports **5 main import types**:

| **Source**     | **Description**                                                                 | **Notes**                                 |
|----------------|---------------------------------------------------------------------------------|-------------------------------------------|
| **URL(s)**     | Paste one or more URLs. Use `sitemap.xml` to bulk import entire websites.       |                                           |
| **Sitemap**    | A structured list of all pages on a site. Ideal for full-site crawls.            |                                           |
| **Upload file**| Upload `.pdf`, `.txt`, or `.docx` files (Max 10MB). Good for internal docs.      |                                           |
| **Plain text** | Paste raw content directly. Great for fast prototyping.                         |                                           |
| **Zendesk**    | Import articles from your Zendesk instance. Admin access required.               | Requires Zendesk admin permissions         |

---

### ⚠️ Warning: Be cautious with sensitive content

- Anything you upload **may be included in LLM responses**.  
- Avoid uploading confidential or proprietary information unless your use case allows it.

---

### ⚠️ Zendesk Admin Required

To import from Zendesk:

- Paste your Zendesk instance URL (e.g., `https://yourorg.zendesk.com`)  
- Ensure you have **admin permissions** on the Zendesk instance.  
- Without admin rights, the import will fail.
