---
title: Secrets Manager API
excerpt: Programmatically manipulate secret values stored in your Secrets Manager
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

The Secrets Manager feature in Voiceflow allows you to securely store secret values for your AI assistant. Secret values are encrypted with the AES-256-CBC algorithm and have tight restrictions on when they are allowed to be exposed outside of storage. This system allows you to store sensitive data like API keys without unnecessarily leaking its value.

This functionality is useful whenever a step requires a sensitive value to operate. For example, the Function step will often run code that makes API calls and thus requires access to API keys. However, it is dangerous to provide keys through a Voiceflow variable, as they are unencrypted at rest and were not designed to prevent unintentional leaking of data. Storing the API key as a secret and passing it into a Function step solves this issue. 

The Secrets Manager API allows you to programmatically manipulate secret values within your secret manager. To use this API, it is important to understand the difference between default and override values for secrets, which we will outline this brief guide.

# Secrets

A **secret** consists of a **name** and associated **values**. Projects own a collection of secrets.

A secret's values come in two types: **default values** and **override value**.  Default values are owned by the **project** and each secret always has exactly one default value. Override values are owned by an **environment** within a project and each secret may optionally have an override within in an environment.

> 📘 Projects and Environments
>
> Recall that Voiceflow projects come with multiple **environments**, which are different version of your project's source content. In fact, the legacy implementation of environments was called *versions*.
>
> Environments are used to manage your project's development and deployment. Projects come with two built-in environments: the **development** and **production** environments. The development environment is what you edit with the Voiceflow canvas, while the production environment is the version that is automatically created (or updated) when you build your assistant.

To execute an assistant on the Voiceflow Runtime, we must specify an environment for that assistant to execute in. On the Voiceflow canvas, you test your assistant by executing in the development environment. For production, you would make calls to execute your assistant in the production environment

When an assistant is executed, it pulls two collections from the secrets manager: the default values of the project being executed and the override values of the executing environment. When a secret is referenced by a step, the Voiceflow runtime first looks up the override value, then falls back to the default value if no override exists. 

As a concrete example, suppose that the default values and override values of that assistant interaction looks like this:

```javascript json
const defaultValues = {
  secret1: 'default-value-1',
  secret2: 'default-value-2',
};

const overrideValues = {
  secret1: 'override-value-1'
}
```

If a step were to access `secret1`, then the value resolves to `override-value-1` since the override for the environment exists.

If a step were to access `secret2`, then the value resolves to `default-value-2` because the override for `secret2` does not exist in this environment, and thus, resolution falls back to the default value originating from the project configuration.
