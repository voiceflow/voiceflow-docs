---
title: Importing Data
deprecated: false
hidden: false
metadata:
  robots: index
---
## Supported data sources

Voiceflow supports five different data sources:

| **Source**      | **Description**                                                                                                                                                     |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **URL(s)**      | Paste one or more URLs to import the content from those pages. Use `sitemap.xml` to bulk import entire websites.                                                    |
| **Sitemap**     | Import all pages from a website into your knowledge base, ideal for full-site crawls. For most websites, the sitemap is found at `https://website.com/sitemap.xml`. |
| **Upload file** | Upload `.pdf`, `.txt`, or `.docx` files (Max 10 mb). Only text can be imported into the knowledge base.                                                             |
| **Plain text**  | Paste raw content directly. Great for fast prototyping or testing.                                                                                                  |
| **Zendesk**     | Import data from your Zendesk knowledge base. Requires Zendesk admin access.                                                                                        |

<br />

> ℹ️ Heads up!
>
> Make sure you don't import confidential or proprietary data unless your use case allows it. Any data that you import may be included in LLM-generated responses.

# 🔁 Sync Settings

Voiceflow lets you **auto-refresh imported URLs and sitemaps** based on how frequently the content changes.

| **Option**  | **Best for...**                                      |
| ----------- | ---------------------------------------------------- |
| **Never**   | Static content that doesn't need refreshing          |
| **Daily**   | Frequently updated content (e.g., blogs, news sites) |
| **Weekly**  | Occasionally updated info (e.g., support centers)    |
| **Monthly** | Stable content (e.g., product policies, pricing)     |

> 🚧 Be careful with refresh rates!
>
> When an LLM chunking strategy is enabled, every re-sync will consume credits. If your content doesn't change often, we'd recommend you reduce your refresh rate frequency. When LLM chunking strategies are disabled, re-syncs don't consume any credits.