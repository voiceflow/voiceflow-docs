---
title: Query assistant usage v2
api:
  file: analytics-api-usage-v2.json
  operationId: QueryPublicController_queryUsageV2
hidden: true
---
## 📡 Request Types

There are different types of requests that can be sent.\
To see a list of all request types, check out the documentation for the `data.name` field below.

Examples include:

* Unique users
* Understood messages
* Top intents
* Total interactions

Below are example request and response pairs.

\<div class="tabs">
&#x20; \<button onclick="showTab('intents')">Top Intents\</button>
&#x20; \<button onclick="showTab('users')">Unique Users\</button>
&#x20; \<button onclick="showTab('credits')">Credit Usage\</button>
\</div>

\<div id="intents" class="tab-content">
&#x20; \<pre>\<code class="json">\{
&#x20; "data": \{
&#x20;   "name": "top\_intents",
&#x20;   "filter": \{
&#x20;     "projectID": "your-project-id",
&#x20;     "startTime": "2021-08-01T00:00:00.000Z",
&#x20;     "endTime": "2021-08-16T00:00:00.000Z",
&#x20;     "limit": 3
&#x20;   }
&#x20; }
}\</code>\</pre>
\</div>

\<div id="users" class="tab-content" style="display:none">
&#x20; \<pre>\<code class="json">\{
&#x20; "data": \{
&#x20;   "name": "unique\_users",
&#x20;   "filter": \{
&#x20;     "projectID": "your-project-id",
&#x20;     "startTime": "2021-08-01T00:00:00.000Z",
&#x20;     "endTime": "2021-08-16T00:00:00.000Z"
&#x20;   }
&#x20; }
}\</code>\</pre>
\</div>

\<script>
function showTab(id) \{
&#x20; document.querySelectorAll('.tab-content').forEach(el => el.style.display = 'none');
&#x20; document.getElementById(id).style.display = 'block';
}
\</script>

***

In the example above, the Voiceflow project responded with the top 3 intents for the assistant with `projectID: 62912f08e83f76001b218690`.