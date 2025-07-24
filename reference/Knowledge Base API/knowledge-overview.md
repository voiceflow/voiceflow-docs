---
title: Overview
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
The Knowledge Base APIs provide a suite of tools for managing documents, tables, and tags within your Voiceflow Knowledge Base. These APIs enable users to upload, retrieve, query, and manage data effectively, ensuring that the Knowledge Base remains organized, searchable, and responsive. Below is an overview of the key APIs available:

#### 1. **Query API**

The Query API allows users to perform searches within the Voiceflow Knowledge Base to retrieve precise answers to questions. This API supports advanced filtering options, enabling users to narrow down their searches to find the most relevant data.

* **Endpoint**: `/knowledge-base/query`
* **Base URL**: `https://general-runtime.voiceflow.com`
* **Method**: POST
* **Features**:
  * Allows users to submit queries and retrieve the most relevant chunks of information.
  * Supports advanced query filtering capabilities, including equality and comparison, array operations, and logical operators.
  * Enables users to control the synthesis of responses, model selection, temperature settings, and filtering using metadata or tags.
  * Provides practical examples and guidelines for forming complex queries to meet specific search requirements.

#### 2. **Document API**

The Document API offers extensive capabilities for managing various document types within the Knowledge Base. It supports uploading, replacing, deleting, and retrieving documents, including both unstructured and structured data such as tables.

* **Endpoints**:
  * `/v1/knowledge-base/docs/upload` (POST) - Uploads a new document (excluding type "url").
  * `/v1/knowledge-base/docs/{documentID}` (GET, DELETE) - Retrieves or deletes a document by its ID.
  * `/v1/knowledge-base/docs/{documentID}/upload` (PUT) - Replaces an existing document by its ID.
  * `/v1/knowledge-base/docs/upload` (POST) - Uploads a document of type "url".
  * **Tabular Data Support**: `/v1/knowledge-base/docs/upload/table` (POST) - Uploads new table data to the Knowledge Base. This endpoint supports fully customizable fields, including various data types such as string, number, array, or object.
* **Base URL**: `https://api.voiceflow.com`
* **Features**:
  * Supports multiple document types, including URLs, PDFs, text files, DOCX files, and tabular data.
  * Allows for attaching tags to documents for better organization and retrieval.
  * Enables flexible management of documents with options for pagination, filtering, and handling documents in bulk.
  * Provides robust support for tabular data, allowing users to upload structured datasets with searchable and metadata fields for enhanced query capabilities.

### Authentication

All requests to the Knowledge Base APIs must be authenticated using a Dialog Manager API Key. The API Key can be obtained from the Integration tab in the Voiceflow project settings.