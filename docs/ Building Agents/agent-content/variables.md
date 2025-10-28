---
title: Variables
excerpt: Store information for the duration of a conversation.
deprecated: false
hidden: true
metadata:
  robots: index
---
Variables let your agent remember and reuse information during a conversation. You can store details like a user’s name and account details, then reference them later to personalize responses or make decisions in your flow.  Variables act as your agent’s short-term memory, helping it keep track of what matters from one step to the next.

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

    <tr>
      <td>
        `user_id`
      </td>

      <td>
        The user's unique ID, as set through the [web chat widget](doc:chat-widget) or the [API](doc:custom-interfaces). If using Voiceflow's [phone](doc:telephony) integration, this is automatically set to the phone number that the agent is calling.
      </td>

      <td>
        **Web chat or API**: example_user  
        **Phone**: +16471234567
      </td>
    </tr>

    <tr>
      <td>
        `vf_memory`
      </td>

      <td>
        The last ten user inputs and agent responses in a string. This also includes tool calls.
      </td>

      <td>
        agent: Hey what's up?
        user: I want to order maple syrup.
      </td>
    </tr>

    <tr>
      <td>
        `vf_now`
      </td>

      <td>
        The current date and time formatted in a human-readable way. You can modify the timezone in project settings.

      </td>

      <td>
        Jan 1, 2025, 16:37
      </td>
    </tr>

    <tr>
      <td>
        `vf_date`
      </td>

      <td>
        The current date formatted in a human-readable way.
      </td>

      <td>
        Jan 1, 2025
      </td>
    </tr>

    <tr>
      <td>
        `vf_time`
      </td>

      <td>
        The current time formatted in a human-readable way.
      </td>

      <td>
        16:37
      </td>
    </tr>

    <tr>
      <td>
        `vf_month`
      </td>

      <td>
        The current month.
      </td>

      <td>
        January
      </td>
    </tr>

    <tr>
      <td>
        `vf_day`
      </td>

      <td>
        The current day of the month.
      </td>

      <td>
        1
      </td>
    </tr>

    <tr>
      <td>
        `vf_year`
      </td>

      <td>
        The current year.
      </td>

      <td>
        2025
      </td>
    </tr>

    <tr>
      <td>
        `vf_timezone`
      </td>

      <td>
        The user's timezone in the format. If unavailable, defaults to the project's timezone.
      </td>

      <td>
        America/Toronto
      </td>
    </tr>
  </tbody>
</Table>

<br />
