---
title: Loading Data Sources
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
# Through the UI

![](https://files.readme.io/7788cee-CleanShot_2024-05-08_at_20.41.052x.png)

1. Access Knowledge Base. Begin by going to the Knowledge Base tab, located within the Content section of your dashboard.
2. Add Data Source. Click the 'Add Data Source' button to start the upload process. This button is prominently displayed in the header for easy access.
3. Choose the type of data source you wish to upload. 
   1. URL(s): Use this for web pages where the AI can read static text. Ideal for FAQ pages or information repositories. Any dynamically-loaded text, table data, or image content will not be used within your response. Any content behind an authentication wall will not be accessible.  
      Optional - Select preferred Refresh rate.
   2. Plain text: Best for when you have unformatted, straightforward text data you want to include.
   3. Sitemap: Useful for giving the AI an understanding of the hierarchy and layout of your content-rich website.
   4. Text: For uploading plain .txt files containing information the AI needs to access. File size is limited to 10MB.
   5. PDF: When you have documentation in PDF form that needs to be referenced by the AI. File size is limited to 10MB.
   6. Docx: For Word documents that contain relevant data for the AI. File size is limited to 10MB.
   7. Integration: Connect to a third-party software (e.g. Zendesk Help Center) to import help articles.  
      Confirmation: After the data source is selected and the upload process is initiated, you will see an indicator that shows the upload progress. Once complete, a confirmation message will indicate that the data source is now integrated and active.
   8. Once you add a data source, it will show you the loading status, and then confirm once the data source has been loaded and is ready to use.

# Through the API

[Use the document api](https://developer.voiceflow.com/reference/post_v3alpha-knowledge-base-docs-upload)  to upload , update and delete content. 

## Add a document

```python python
import requests

url = "https://api.voiceflow.com/v3alpha/knowledge-base/docs/upload?maxChunkSize=1000"

headers = {
    "accept": "application/json",
    "content-type": "multipart/form-data"
}

response = requests.post(url, headers=headers)

print(response.text)
```

## Add a url

```python
import requests

url = "https://api.voiceflow.com/v3alpha/knowledge-base/docs/upload?maxChunkSize=1000"

headers = {
    "accept": "application/json",
    "content-type": "application/json; charset=utf-8"
}

response = requests.post(url, headers=headers)

print(response.text)
```

For full documentation, checkout our API references

> 📘 <https://developer.voiceflow.com/reference/post_v3alpha-knowledge-base-docs-upload-1>