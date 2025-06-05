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

Voiceflow's Knowledge Base supports various data types, but for optimal performance, consider the following recommendations:

* Text-based Documents: These are the most preferred format for the Knowledge Base.
  * Plain text (.txt) files are also excellent choices.
* Web Documents: HTML and other web-based formats are generally well-parsed and can be good options.
* PDFs: While PDFs are supported, they are not the ideal format for the Knowledge Base.
  * PDF parsers generally don't perform as well as text-based document parsers.
  * When possible, convert PDF content to plain text before uploading.

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

## Five Knowledge Base Optimization Practices

1. **Use Markdown and Keep It Simple:**

* Format your documents in markdown for better structure and easier parsing.
* Stick to simple, clear formatting to aid in parsing.\*\*
* Note: Voiceflow also uses Markdown to format its text responses, ensuring consistency across your agent.

2. **Organize Content Effectively:**

* Break down large documents into smaller, topic-focused files.
* Maintain consistent formatting and structure across your documents.
* For structured data, use the tabular format to allow for more precise querying and filtering.

3. **Optimize Searchability:**

* Make fields searchable if users are likely to query that information directly.
* Include frequently asked questions (FAQs) as searchable terms to improve information discovery.
* Use meaningful tags (like "userType") to categorize information for easy filtering.

4. **Enhance with Metadata:**

* Include relevant metadata that adds value, such as "lastUpdated" for content freshness and "pageLink" for navigation. For instance, you could use page link with a function to enable a user to click off to another webpage.

5. **User-Centric Approach:**

* Structure your data with the end-user in mind, anticipating how they might search for information.
* Regularly update and review your Knowledge Base to ensure content remains current and relevant.
* Test your Knowledge Base with various user queries to ensure it provides accurate and helpful responses.

By focusing on these key practices, you can significantly enhance the effectiveness of your Voiceflow Knowledge Base, making it more accessible, accurate, and user-friendly.

Next, lets look at the Workflow Builder.