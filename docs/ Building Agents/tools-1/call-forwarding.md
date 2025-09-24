---
title: Call forwarding
excerpt: Automatically forward calls to a live agent.
deprecated: false
hidden: true
metadata:
  robots: index
---
<Callout icon="ℹ️">
  This feature is only available when calling an agent via [phone](doc:telephony).
</Callout>

After interacting with your AI agent, some callers may still need to speak with a person for certain requests or follow-ups. Call forwarding lets you send the call to another phone number, SIP address, or extension. It’s useful when the agent collects initial details, then directs the caller to the right teammate, department, or specialist to finish the conversation.

<br />

## Basic usage

<br />

Inside an [Agent step](doc:agents), enable the **Call forward** option on the sidebar. Then, set the following three options:

* **LLM description** - this allows you to to describe the tool to your agent and tell it when it should be triggered.
* **Phone number** - the phone number that the caller should be forwarded to, including country code. For example, `+16471112222`.
* **Extension (optional)** - if you'd like to automatically connect the caller to a specific extension, enter the extension here. Otherwise, leave this input blank.

Some advanced users may wish to forward the call via SIP instead. This can be done by selecting the SIP option and entering a SIP address when prompted.

<br />

<br />

<br />
