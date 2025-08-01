---
title: Best practices
excerpt: Best practices for Voiceflow's Knowledge Base.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Knowledge Base Best Practices

The Knowledge Base is a repository and management system for content that your AI Agent uses to provide accurate and contextually relevant responses. It allows you to:

* Store and organize information your agent can reference
* Provide context for more accurate and relevant responses
* Easily update and maintain your agent's knowledge

## Supported Data Types and Best Practices

| **Source**      | **Description**                                                                                                                                                     |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **URL(s)**      | Paste one or more URLs to import the content from those pages. Use `sitemap.xml` to bulk import entire websites. You can only import publicly accessible URLs.      |
| **Sitemap**     | Import all pages from a website into your knowledge base, ideal for full-site crawls. For most websites, the sitemap is found at `https://website.com/sitemap.xml`. |
| **Upload file** | Upload `.pdf`, `.txt`, or `.docx` files (Max 10 mb). Only text can be imported into the knowledge base.                                                             |
| **Plain text**  | Paste raw content directly. Great for fast prototyping or testing.                                                                                                  |
| **Zendesk**     | Import data from your Zendesk knowledge base. Requires Zendesk admin access.                                                                                        |

On the **pro plan**, each project can support up to 3,000 different sources (URLs, documents, etc) of knowledge base content.

### Advanced Knowledge Base Formats

For users who require more control and flexibility, Voiceflow offers advanced formats for organizing and querying Knowledge Base content. We'll explore these features using a credit card application process example.

#### Using a tabular data format

The tabular data format is useful for structured information and allows for more precise querying and filtering of data. This format is particularly beneficial for organizing complex information like credit card application processes.

**Key Features:**

* Structured data representation in rows and columns
* Ability to add detailed metadata and tags to each entry
* Enhanced control over searchable fields
* Improved precision in data retrieval
* Example Structure: Here's how you might structure credit card application information using the tabular data format:

```json JSON
{  
  "data": {  
    "name": "credit_card_applications",  
    "schema": {  
      "searchableFields": ["cardType", "applicationSteps", "requirements", "faqs"],  
      "metadataFields": ["userType", "lastUpdated", "pageLink"]  
    },  
    "items": [  
      {  
        "cardType": "Personal Rewards Card",  
        "applicationSteps": "1. Fill out personal information. 2. Provide income details. 3. Submit application.",  
        "requirements": "Must be 18 years or older, have a valid SSN, and annual income of at least $30,000",  
        "faqs": "What credit score do I need? How long does the application process take? Is there an annual fee?",  
        "userType": "personal",  
        "lastUpdated": "2024-07-01",  
        "pageLink": "/personal-rewards-card"  
      },  
      {  
        "cardType": "Business Cash Back Card",  
        "applicationSteps": "1. Enter business details. 2. Provide business financial information. 3. Submit application with required documents.",  
        "requirements": "Must have a registered business, EIN, and annual business revenue of at least $50,000",  
        "faqs": "Can I apply as a sole proprietor? What documents do I need? How is the cash back calculated?",  
        "userType": "business",  
        "lastUpdated": "2024-07-15",  
        "pageLink": "/business-cash-back-card"  
      }  
    ]  
  }  
}
```

Using the above data format, you’re able to have much more granular control over what information you retrieve. For example, the FAQs section adds additional vectors that would enhance the Knowledge Base’s ability to find similar information that is similar to what the user has asked.

Similarly, you could dynamically filter searches by things like the “userType” field, to ensure that only information that is related to the user’s query is surfaced, i.e, business or personal.