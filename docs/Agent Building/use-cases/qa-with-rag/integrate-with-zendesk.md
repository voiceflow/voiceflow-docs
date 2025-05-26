---
title: Integrating ticket management with Zendesk
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

   * Brand (required): Before importing any articles, you must select the brand which to fetch the articles from. 
     * NOTE: you can run the import operation as many times as necessary from across various brands if necessary.
   * User Segment: This field allows you to filter by user segment.
   * Locale: This field allows you to only import articles for a certain language. You can get the locale from the Zendesk Help Center URL after you've selected a specific language.
   * Categories: If you have multiple categories then you can optionally filter articles for a specific category.
   * Labels: This field allows you to filter by labels applied to your articles.
   * Refresh Rate: Decide how often you want the document to sync with Zendesk, ensuring your AI has the latest information.
   * Import Confirmation: Once you finalize the import filters, you will be shown the number of articles that will be imported in the Import button.

   ### Integration management

   <br />

   ![](https://files.readme.io/bbf45e6-image.png)

{/*-*/}

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

5. Base64 encode your API Token, in the format: \{email\_address}/token:\{api\_token}

6. Replace "auth-value" with your Base64 enconded API token

7. Capture "response.ticket.id" to \{ticketID}

### Voiceflow template walkthrough

Get started with a Voiceflow [template](https://creator.voiceflow.com/dashboard?import=662bfb229b775c57246aeaa7) to automate ticket submission.

<Embed url="https://www.youtube.com/watch?v=CyAU5CUsjTY" title="How to Integrate Zendesk for Faster Ticket Resolution with Voiceflow" favicon="https://www.google.com/favicon.ico" image="https://i.ytimg.com/vi/CyAU5CUsjTY/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=CyAU5CUsjTY" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FCyAU5CUsjTY%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DCyAU5CUsjTY%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FCyAU5CUsjTY%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

<br />

### Community partner walkthrough

Checkout the tutorial how a community leader built a Zendesk app in Voiceflow.

<Embed url="https://www.youtube.com/watch?v=Dt3KJKX29-I" favicon="https://www.google.com/favicon.ico" image="http://i.ytimg.com/vi/Dt3KJKX29-I/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=Dt3KJKX29-I" typeOfEmbed="youtube" title="undefined" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FDt3KJKX29-I%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DDt3KJKX29-I%26image%3Dhttp%253A%252F%252Fi.ytimg.com%252Fvi%252FDt3KJKX29-I%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />
