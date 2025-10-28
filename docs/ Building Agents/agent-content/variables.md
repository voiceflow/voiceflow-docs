---
title: Variables
excerpt: Store information for the duration of a conversation.
deprecated: false
hidden: true
metadata:
  robots: index
---
Voiceflow projects supp

<br />

<br />

## Built-in variables

Each project created on Voiceflow automatically has access to some built-in variables. These are automatically set when the user begins a conversation with your agent and when certain actions take place.

<br />

| Variable name       | Description                                                                                                                                                                                                       | Example Data                               |
| :------------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------- |
| `intent_confidence` | The confidence interval (measured as a value from 0 to 100) for the most recently matched [intent](doc:intents-1). **Note that intents are a legacy feature that we do not recommend using in new agent builds.** | 67                                         |
| `last_event`        | The object containing the last [event](doc:events) that the user client has triggered. This variable will be empty if no event has been triggered.                                                                |                                            |
| `last_response`     | The agent's last response that it sent to the user.                                                                                                                                                               | Hello, I'm an agent! How can I help today? |
| `last_utterance`    | The previous message that was sent by the user.                                                                                                                                                                   | My name is Braden and I like cookies.      |
| `locale`            | The [locale](https://learn.microsoft.com/en-us/globalization/locale/standard-locale-names) of the user, as detected from their browser.                                                                           | en-CA                                      |
| `platform`          | The platform your agent is running on.                                                                                                                                                                            | voiceflow                                  |
| `sessions`          | The number of times a particular user has opened the agent.                                                                                                                                                       | 8                                          |
| `timestamp`         | The [UNIX timestamp](https://en.wikipedia.org/wiki/Unix_time) of when the conversation began.                                                                                                                     | 873700668                                  |

<br />
