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

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Variable name
      </th>

      <th>
        Description
      </th>

      <th>
        Example Data
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        `intent_confidence`
      </td>

      <td>
        The confidence interval (measured as a value from 0 to 100) for the most recently matched [intent](doc:intents-1). **Note: intents are a legacy feature that we do not recommend using in new agent builds.**
      </td>

      <td>
        67
      </td>
    </tr>

    <tr>
      <td>
        `last_event`
      </td>

      <td>
        Information about the last [event](doc:events) that the user triggered. Defaults to `{"type":"launch","payload":{"resetState":false}}`. **Note: this variable contains an object rather than a string**.
      </td>

      <td>
        `{"type":"event","payload":{"event":{"name":"buySyrup"}}}
        `
      </td>
    </tr>

    <tr>
      <td>
        `last_response`
      </td>

      <td>
        The agent's last response that it sent to the user.
      </td>

      <td>
        Hello, I'm an agent! How can I help today?
      </td>
    </tr>

    <tr>
      <td>
        `last_utterance`
      </td>

      <td>
        The previous message that was sent by the user.
      </td>

      <td>
        My name is Braden and I like cookies.
      </td>
    </tr>

    <tr>
      <td>
        `locale`
      </td>

      <td>
        The [locale](https://learn.microsoft.com/en-us/globalization/locale/standard-locale-names) of the user, as detected from their browser.
      </td>

      <td>
        en-CA
      </td>
    </tr>

    <tr>
      <td>
        `platform`
      </td>

      <td>
        The platform your agent is running on.
      </td>

      <td>
        voiceflow
      </td>
    </tr>

    <tr>
      <td>
        `sessions`
      </td>

      <td>
        The number of times a particular user has opened the agent.
      </td>

      <td>
        8
      </td>
    </tr>

    <tr>
      <td>
        `timestamp`
      </td>

      <td>
        The [UNIX timestamp](https://en.wikipedia.org/wiki/Unix_time) of when the conversation began.
      </td>

      <td>
        873700668
      </td>
    </tr>
  </tbody>
</Table>

<br />
