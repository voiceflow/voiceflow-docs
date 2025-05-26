---
title: Versions and Project IDs
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
You can find your Project ID and Version ID in the general settings. This article will explain what they are and why you might care about using them.

![](https://files.readme.io/a6ec4f7-image.png)

# Versions

Voiceflow agents use versions to be able to choose a specific version of their agent to run with our Dialog Manager API (DM API) or the Chat Widget, and is also required for some other APIs.

The two main versions available are:

* development:  A new development version is compiled each time you click on the Play button

<Image align="center" src="https://files.readme.io/593ba78-CleanShot_2024-06-24_at_14.30.202x.png" />

* production: A new production version is published each time you click on the Publish button

<Image align="center" src="https://files.readme.io/fd76511-CleanShot_2024-06-24_at_14.33.002x.png" />

A **development** version is meant to be used for testing purpose, when you are making changes to your agent and want to test them before pushing those changes to your live agent (production). A **production** version should be a stable, tested version you want to use in production while you’re working on the development version of your agent in Voiceflow Creator.

Each version has a unique version ID associated, but your current production and development version can often be referred to using their **alias**. The production version's alias is `production` and the development version's alias is `development`. This is useful because it means you don't have to update the version ID being used in your code if you publish a new version.

**Note:** *A couple of APIs might still next the exact version ID instead of an alias like in the versions API.*

When you make a request to the DM API without passing any version in the header, we **default to the development** version (same goes for the Chat Widget snippet code). 

*Below, a DM API launch request using the**development** version of an agent*

```curl
curl --request POST \
  --url https://general-runtime.voiceflow.com/state/user/demo/interact \
  --header 'Authorization: VF.DM.XYZ' \
  --header 'Content-Type: application/json' \
  --header 'versionID: development' \
  --data '{
	"action": {
		"type": "launch"
  }
}'
```

*Below, some Chat Widget snippet code loading the**production** version of an agent*

```html
<script type="text/javascript">
  (function(d, t) {
      var v = d.createElement(t), s = d.getElementsByTagName(t)[0];
      v.onload = function() {
        window.voiceflow.chat.load({
          verify: { projectID: 'xyz' },
          url: 'https://general-runtime.voiceflow.com',
          versionID: 'production'
        });
      }
      v.src = "https://cdn.voiceflow.com/widget/bundle.mjs"; v.type = "text/javascript"; s.parentNode.insertBefore(v, s);
  })(document, 'script');
</script>
```

Again, always having two different versions allow you to keep working on/updating your agent (**development**) without impacting an existing live version (**production**).

# Project IDs

Project IDs are only required for certain APIs, and is also used in the web chat's code snippet. It can be found from the Settings → General page, and uniquely identifies your project (and never changes).

For the DM API for example, the link to the project is done through the API key directly, but some APIs the like the [Transcripts API](https://developer.voiceflow.com/v2.0/reference/fetchtranscripts) for example, needs both the authorization and the Project ID.

In general, you'll only need to use the API key, and your applications can have a local variable storing the project ID for when it's needed, but in some cases you might need your Project ID.
