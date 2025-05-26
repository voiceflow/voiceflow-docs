---
title: Integrating ticket management with Zendesk
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Intro

If you're building a complex customer support implementation, using a ticketing system can help you keep track of issues and escalate issues from customers. In this use case walkthrough we show how to integrate Voiceflow with Zendesk.

Voiceflow has a number of capabilities to integrate with Zendesk, in this guide we'll cover how to:

1. Ingest documents
2. Create tickets

## Add documents via Integration Zendesk Help Center

1. On the KB CMS page, click on the 'Add Data Source' button, then select 'Integration'.

![](https://files.readme.io/ce79454-image.png)

<br />

2. Select Zendesk Help Center: From the list of integrations, choose 'Zendesk Help Center’
3. Awaiting Authorization: After selecting Zendesk, you will be prompted to authorize the connection to your Zendesk account.
4. Importing Articles: Post-authorization, the import modal allows you to filter and import only articles that are applicable for your knowledge base. All applicable filter values will be available in the dropdown for selection. 
5. NOTE: only Published articles are available for import. 
6. Filters include:

   - Brand (required): Before importing any articles, you must select the brand which to fetch the articles from. 
     - NOTE: you can run the import operation as many times as necessary from across various brands if necessary.
   - User Segment: This field allows you to filter by user segment.
   - Locale: This field allows you to only import articles for a certain language. You can get the locale from the Zendesk Help Center URL after you've selected a specific language.
   - Categories: If you have multiple categories then you can optionally filter articles for a specific category.
   - Labels: This field allows you to filter by labels applied to your articles.
   - Refresh Rate: Decide how often you want the document to sync with Zendesk, ensuring your AI has the latest information.
   - Import Confirmation: Once you finalize the import filters, you will be shown the number of articles that will be imported in the Import button.

   ### Integration management

   <br />

   ![](https://files.readme.io/bbf45e6-image.png)

<!----->

1. Open Integrations panel: In the Knowledge Base, you can manage your integrations by selecting the Integrations icon in the header of table.
2. Update or remove connection: This will show you a list of all your connected integrations (more coming soon), including Zendesk, with the option to reconnect with a different account or to remove them. 
   1. NOTE: if you delete the connection, any refresh rate assigned to the Zendesk articles will fail unless you reconnect with an account that has access to those same articles.

## Create tickets

You can also create and store tickets in Zendesk via the Voiceflow API step.

```
{
  "ticket": {
    "comment": {
      "html_body": "<h3>Action required: Answer customer's question</h3><br><p></p><b>Customer's question:</b> {customerQuestion}</p><p><b>AI's context question to the customer:</b> {additionalQuestion}</p><p><b>Additional context from customer:</b> {customerAdditionalContext}</p><br><p><b>Goal: Solve the ticket in one reply. How?</b></p><ul><li>Gather additional context from customer past tickets.</li><li>Check if customer raised other tickets and merge them.</li></li><li>Anticipate the next question and resolve it in this reply.</li><li>Keep your response clear and concise.</li></ul></p><hr><p><b>System Message:</b> This ticket was generated through our chatbot. If the information isn't displaying correctly, or if you need different information to complete this request, please contact your Team Leader with suggested changes to this template.</p>",
      "public": false
    },
    "tags": ["{ticketCategory}", "{ticketSubcategory}", "chat_feedback"], 
    "requester": {"name": "{customerName}", "email": "{customerEmail}"},
    "subject": "Chat Support Ticket: {customerName} has a question",
    "priority": "{ticketPriority}"
  }
}
```

### Key componets

Using the Zendesk API has a few key steps, listed within the template.

1. Review Zendesk Dev Docs on how to Create A New Ticket

2. Replace "example" with your domain, in the URL

3. Generate your Zendesk API Token

4. Review Zendesk Dev Docs on how to authenticate with an API Token

5. Base64 encode your API Token, in the format: {email_address}/token:{api_token}

6. Replace "auth-value" with your Base64 enconded API token

7. Capture "response.ticket.id" to {ticketID}

### Voiceflow template walkthrough

Get started with a Voiceflow [template](https://creator.voiceflow.com/dashboard?import=662bfb229b775c57246aeaa7) to automate ticket submission.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FCyAU5CUsjTY%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DCyAU5CUsjTY&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FCyAU5CUsjTY%2Fhqdefault.jpg&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=CyAU5CUsjTY",
  "title": "How to Integrate Zendesk for Faster Ticket Resolution with Voiceflow",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/CyAU5CUsjTY/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=CyAU5CUsjTY",
  "typeOfEmbed": "youtube"
}
[/block]


<br />

### Community partner walkthrough

Checkout the tutorial how a community leader built a Zendesk app in Voiceflow.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FDt3KJKX29-I&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DDt3KJKX29-I&image=http%3A%2F%2Fi.ytimg.com%2Fvi%2FDt3KJKX29-I%2Fhqdefault.jpg&key=7788cb384c9f4d5dbbdbeffd9fe4b92f&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=Dt3KJKX29-I",
  "favicon": "https://www.google.com/favicon.ico",
  "image": "http://i.ytimg.com/vi/Dt3KJKX29-I/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=Dt3KJKX29-I",
  "typeOfEmbed": "youtube"
}
[/block]