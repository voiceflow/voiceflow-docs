---
title: Importing data
excerpt: >-
  Enhance agent capabilities by importing data into its knowledge base for
  tailored and relevant responses.
deprecated: false
hidden: false
metadata:
  title: Importing data to Voiceflow's Knowledge Base
  robots: index
---
Supercharge your Voiceflow agent by importing content from websites, documents, and support articles- giving it the context it needs to respond with real, reliable information.

<Video src="https://yz5du1veb1.ufs.sh/f/9fKud4NeF5NS3UKNJ6HEN5yeFarYBh6C7SkfDcgJOXVT3zqL" />

## Supported data sources

Voiceflow supports five different data sources:

| **Source**      | **Description**                                                                                                                                                     |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **URL(s)**      | Paste one or more URLs to import the content from those pages. Use `sitemap.xml` to bulk import entire websites. You can only import publicly accessible URLs.      |
| **Sitemap**     | Import all pages from a website into your knowledge base, ideal for full-site crawls. For most websites, the sitemap is found at `https://website.com/sitemap.xml`. |
| **Upload file** | Upload `.pdf`, `.txt`, or `.docx` files (Max 10 mb). Only text can be imported into the knowledge base.                                                             |
| **Plain text**  | Paste raw content directly. Great for fast prototyping or testing.                                                                                                  |
| **Zendesk**     | Import data from your Zendesk knowledge base. Requires Zendesk admin access.                                                                                        |

On the **pro plan**, each project can support up to 3,000 different sources (URLs, documents, etc) of knowledge base content.

> ℹ️ Heads up!
>
> Make sure you don't import confidential or proprietary data unless your use case allows it. Any data that you import may be included in LLM-generated responses.

<br />

## Refresh rate settings

When importing data from a URL or sitemap, you can optionally set a refresh rate. This allows your project to periodically re-sync in content from your website, keeping your knowledge base up to date.

| **Option**  | **Best for...**                                      |
| ----------- | ---------------------------------------------------- |
| **Never**   | Static content that doesn't need refreshing          |
| **Daily**   | Frequently updated content (e.g., blogs, news sites) |
| **Weekly**  | Occasionally updated info (e.g., support centers)    |
| **Monthly** | Stable content (e.g., product policies, pricing)     |

> ⚠️ Be careful with refresh rates!
>
> When an LLM chunking strategy is **enabled**, every re-sync will consume credits. If your content doesn't change often, we'd recommend you reduce your refresh rate frequency. When LLM chunking strategies are **disabled**, re-syncs _don't_ consume any credits.

## LLM chunking strategies

You can use LLM chunking strategies to optimize the data in your agent's knowledge base. The chunking strategies use AI to process your data in various ways, optimizing it for agent. The quality of your content directly impacts your agent's ability to answer user questions.

Voiceflow supports five different chunking strategies:

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
        Breaks and clusters content into topic-based sections.

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

We recommend experimenting with various combinations of chunking strategies to see which best fits your use-case.

## Troubleshooting data imports

If something goes wrong when importing your data, hover over the❗ icon to learn why.

<Image border={false} src="https://files.readme.io/3b34073cf8fd2fd68e0752ea707c17eb8859ed5966d2e8c03e66715d5bbafdcd-image.png" />

Import errors are handled gracefully. Failed files won’t break your project - the remaining files will be processed.

## Advanced: importing data using Voiceflow's API

Voiceflow's <Anchor label="Knowledge Base API" target="_blank" href="https://docs.voiceflow.com/reference/knowledge-overview#/">Knowledge Base API</Anchor> allows you to manage your Knowledge base programmatically. Common API use cases include:

* Importing content from Notion, Google Docs, or Airtable via an SDK or API request
* Managing KB entries dynamically across multiple workspaces, outside of the Voiceflow Creator
* Debugging & testing chunk processing behind the scenes

<LinkCard type="Doc" title="Document API reference" description="Upload files and content from websites using the Document API." href="https://docs.voiceflow.com/reference/post_v1-knowledge-base-docs-upload-url#/" />
