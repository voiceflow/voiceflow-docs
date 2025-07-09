---
title: Importing Data
deprecated: false
hidden: false
metadata:
  robots: index
---
Importing data lets you bring external content- like websites, documents, and support articles- into your Voiceflow assistant workspace for AI to reference during conversations with users.

![](https://files.readme.io/74e3fbe366072c370e2ecb1cb901867afdcf060e0c9913798b353095b36cfb7d-CleanShot_2025-07-09_at_15.58.03.gif)

<br />

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

## Refresh rate settings

When importing data from URLs or sitemaps, you can schedule a refresh rate to automatically re-sync your content

| **Option**  | **Best for...**                                      |
| ----------- | ---------------------------------------------------- |
| **Never**   | Static content that doesn't need refreshing          |
| **Daily**   | Frequently updated content (e.g., blogs, news sites) |
| **Weekly**  | Occasionally updated info (e.g., support centers)    |
| **Monthly** | Stable content (e.g., product policies, pricing)     |

> ⚠️ Be careful with refresh rates!
>
> When an LLM chunking strategy is **enabled**, every re-sync will consume credits. If your content doesn't change often, we'd recommend you reduce your refresh rate frequency. When LLM chunking strategies are **disabled**, re-syncs *don't* consume any credits.

## LLM chunking strategies

LLM chunking strategies help optimize an LLM's access to information in your knowledge base by processing them in various ways to optimize your for your case. Your content quality directly impacts LLM performance.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Strategy name
      </th>

      <th>
        Ideal use case
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Smart chunking
      </td>

      <td>
        Breaks and clusters content into topic-based sections

        > Example use cases:
        >
        > * Long policy documents (Legal, HR)
        > * Real estate listings by region
        > * Educational course catalogs
      </td>
    </tr>

    <tr>
      <td>
        FAQ optimization
      </td>

      <td>
        Converts structured data into question-and-answer pairs to help the LLM handle direct user queries.

        > Example use cases:
        >
        > * Product or service information
        > * Help center FAQ
      </td>
    </tr>

    <tr>
      <td>
        Remove HTML and noise
      </td>

      <td>
        Strips out excess formatting, inline code, and markdown artifacts that may confuse the LLM.

        > Example use cases:
        >
        > * Blog posts with embed-heavy formatting
        > * Markdown-heavy documents
        > * Notion/CMS site exports
      </td>
    </tr>

    <tr>
      <td>
        Add topic headers
      </td>

      <td>
        Prepends each chunk with a short summary line and header to signpost the LLM on available information.

        > Example use cases:
        >
        > * Company policy manuals
        > * Research whitepapers
        > * Developer onboarding guides
      </td>
    </tr>

    <tr>
      <td>
        Summarize
      </td>

      <td>
        Automatically extracts the most important ideas or paragraphs from large, verbose documents.

        > Example use cases:
        >
        > * Investor decks
        > * Legal agreements
        > * Long reports or strategy briefs
      </td>
    </tr>
  </tbody>
</Table>

> 👍 Pro tip: Experiment with strategies for better results.
>
> Combining strategies may optimize both chunk structure and clarity for improved LLM performance:
>
> * `Smart Chunking` + `Add Topic Headers` → Context-rich structured responses (ideal for Internal Tools & HR Agents)
> * `FAQ Optimization` + `Summarize `→ Compact, efficient answers (ideal for Customer Support Agents)
> * `Smart Chunking` + `Remove HTML/Noise` → Clean, readable chunks from web docs (ideal for Web-based Documentation Agents)

## Troubleshooting data imports

If something goes wrong with your data imports, here’s some common approaches to debug:

* Hover over the ❗ icon beside a failed import to view why it failed.

> <Image align="center" border={false} caption="Example error message from failed import." src="https://files.readme.io/94f4e98329a3de393df0b90a46011518a080072a962c7e2618d56362201994af-image.png" />
>
> <br />

* Ensure your URL or sitemap is public and not gated by auth/logins.
* Smart Chunking may fail for large files. Try reducing file size or selecting another chunking method.

> ℹ️ Failed data imports
>
> Import errors are handled gracefully. Failed files won’t break your project - the remaining files will be processed. Delete the failed file, resolve the issue and re-upload again to your knowledge base.

## Using the Knowledge Base REST API

Voiceflow's <Anchor label="Knowledge Base REST API" target="_blank" href="https://docs.voiceflow.com/reference/knowledge-overview#/">Knowledge Base REST API</Anchor> allows you to manage your KB programmatically.

> Common API use cases:
>
> * Importing content from Notion, Google Docs, or Airtable via an SDK or API request
> * Managing KB entries dynamically across multiple workspaces, outside of the Voiceflow Creator
> * Debugging & testing chunk processing behind the scenes