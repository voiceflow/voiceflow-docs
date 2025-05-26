---
title: Adding Custom Variables
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

As you can see in the default snippet code available in your Web Chat agent's integration page,  we use the **chat.load()** function to load a <<glossary:agent>> by setting the **project ID**, the **runtime URL** and a **version ID**.

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

# Pass a custom userID (optional)

Below is an handy way to identify the user and share that info with your <<glossary:agent>>. If you pass a `userID`, the value will be set as the built-in {user_id} variable in your Voiceflow <<glossary:agent>>.

```javascript
/**
* [optional] userID to track users and persist/continue sessions
*/

userID: "string"
```

**Example**

```
window.voiceflow.chat.load({
  verify: {
    projectID: "<ID>"
  },
  url: "https://general-runtime.voiceflow.com",
  versionID: "production",
  userID: "string"
});
```

# Pass custom variable values (optional)

You can pass values to the `last_event` system variable upon `load()`. Use the JavaScript Code step to validate the payload values and set existing variables with default values at the start of each new conversation.

Please note:

- The `last_event` variable is set upon each new user event in the conversation (e.g. widget loaded, intent triggered, button clicked). If you want to set variables with default values, set them immediately after the Start intent in your agent's design.
- Code Steps cannot be used to create new variables. Any variables that you want to use after the Code Step is executed must already exist before being referenced in the Code Step. For example, in the screenshot below, the `user_name` and `user_email` variables would need to be created in your <<glossary:agent>> before you could set them using values from the `last_event` payload.

```javascript
/**
* [optional] pass data to set variables with default values upon load()
*/

launch: {
  event: {
    type: "launch",
    payload: {
      user_name: "Mary",
      user_email: "mary@test.com"
    }
  }
}
```

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/12eca38-Screenshot_2023-11-09_at_3.03.02_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


**Example**

```javascript
/**
* [optional] pass data to set variables with default values upon load()
*/

window.voiceflow.chat.load({
  verify: {
    projectID: "<ID>"
  },
  url: "https://general-runtime.voiceflow.com",
  versionID: "production",
  launch: {
    event: {
      type: "launch",
      payload: {
        user_name: "Mary",
        user_email: "mary@test.com"
      }
    }
  }
});
```

# Pass user info for the Transcripts view (optional)

Here you can set a name and an image that will be used in the transcripts linked to that user. Note: this will not populate any variables or entities in your <<glossary:agent>>.

```javascript
/**
* [optional] user metadata for transcripts
*/

user: {
  name: "string",
  image: "string"
}
```