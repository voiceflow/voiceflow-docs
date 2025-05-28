---
title: Passing custom variables into web chat
excerpt: Send custom variables on web chat load like userID, email, and more.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Customization & Configuration

As you can see in the default snippet code available in your Web Chat agent's integration page,  we use the **chat.load()** function to load a <Glossary>agent</Glossary> by setting the **project ID**, the **runtime URL** and a **version ID**.

Below is an example of the default code snippet.

```javascript
window.voiceflow.chat.load({
  verify: {
    projectID: "<ID>"
  },
  url: "https://general-runtime.voiceflow.com",
  versionID: "production"
});
```

You can add additional settings on top of the above configuration to further customize the Web Chat experience for your users.

## Passing in a custom userID (optional)

You can assign a unique ID to each user with the userID property. This ID becomes available in your agent as the built-in `{user_id}` variable.

This is useful for:

* Identifying users across sessions
* Persisting conversation history
* Personalizing interactions

Here's an example:

```javascript
window.voiceflow.chat.load({
  verify: {
    projectID: 'YOUR_PROJECT_ID'
  },
  url: 'https://general-runtime.voiceflow.com',
  versionID: 'production',
  userID: 'user_12345'
});

```

# Pass custom variable values (optional)

You can pre-fill variables when the assistant loads by using the `launch.event.payload` field. These values populate the last\_event system variable and can be used in a [JavaScript step](doc:javascript-step) at the beginning of the conversation.

```javascript
window.voiceflow.chat.load({
  verify: {
    projectID: 'YOUR_PROJECT_ID'
  },
  url: 'https://general-runtime.voiceflow.com',
  versionID: 'production',
  launch: {
    event: {
      type: 'launch',
      payload: {
        user_name: 'Mary',
        user_email: 'mary@test.com'
      }
    }
  }
});

```

<Image align="center" border={false} caption="Heads up! The JavaScript step can't create new variables. For the example in the screenshot above to work, you'd need to have already created the `user_name` and `user_email` variables like usual." src="https://files.readme.io/12eca38-Screenshot_2023-11-09_at_3.03.02_PM.png" />

One important thing to note: the `last_event` variable is set upon each new user event in the conversation (for example, when the widget loads, an intent is triggered, or a button is clicked). If you'd like to set variables with default values, set them immediately after the Start step in your agent's design.

# Annotating transcripts with user metadata (optional)

You can pass basic user profile info for use in Voiceflow's [Transcripts](doc:transcripts) feature.. This metadata is not available to your agent's logic. It is only used for labeling conversations in the UI.

```javascript
window.voiceflow.chat.load({
  verify: {
    projectID: '<your-project-id>'
  },
  url: 'https://general-runtime.voiceflow.com',
  versionID: 'production',
  user: {
    name: 'Mary',
    image: 'https://example.com/avatar.jpg'
  }
});

```