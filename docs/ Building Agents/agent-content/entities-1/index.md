---
title: Entities
excerpt: >-
  Entities let your agent identify and extract specific information from user
  input.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## What are Entities?

Entities extract specific pieces of information from user input- like a date, location, or product name. They are declared and used to capture specific data during a conversation, while variables are used to store and manage it.

**Example**\
If a user says, "I want to book a flight to Paris next Friday," your assistant might extract:

`location` → `Paris`

`date `→ `next Friday`

These extracted values (entities) can then be stored in variables for later use- for example, to confirm the travel booking.

***

## Entity extraction rules

Entity rules let you define what valid input should look like—such as a 5-digit number for a ZIP code—so your assistant can validate responses and help the LLM extract the right information. These rules are written in natural language, making them easy to create and understand.

\[ insert pic of entities panel w rules showing ]

### Examples entity rules

* **Zip Code**: "Must be exactly 5 digits long."
* **Email Address**: "Must be a valid business email, not a personal email like Gmail or Yahoo."
* **Phone Number**: "Should be a 10-digit number, possibly formatted with dashes or spaces."
* **Order Number**: "Must start with 'ORD' followed by 7 digits."

Clearly define what you need without making it hard for the user to comply. Write rules the same way, you would explain to a person.

***

## Automatic reprompts

**Automatic reprompts** are dynamic follow-up messages that the system generates when a user's input doesn't meet the entity's requirements. This feature ensures that the conversation remains fluid and user-friendly.

### How automatic reprompts work

1. **Detection**: If the user's input is invalid or incomplete based on your entity rules, the system recognizes this.
2. **Generation**: The LLM crafts a personalized message prompting the user to provide the correct information.
3. **Response**: The user provides the needed input, and the conversation continues smoothly.

**Example**

* *Scenario*: You're capturing an `email address`, and the user says, "It's john at email dot com."
* *Reprompt*: "It seems there's a typo in the email address. Could you please provide a valid email in the format '[example@domain.com](mailto:example@domain.com)'?"

***

## Exit scenarios

Sometimes, a user may be unable or unwilling to provide the information you're requesting. **Exit scenarios** allow your agent to handle such situations gracefully.

### What are exit scenarios?

Exit scenarios are predefined conditions under which the system stops attempting to collect a particular entity and moves on in the conversation.

### How to set up exit scenarios

* **Define Trigger Phrases**: Specify phrases or responses that indicate the user wants to skip or cannot provide the information (e.g., "I don't know," "I'd rather not say").
* **Configure the Exit Path**: Decide where the conversation should go next. This could be:
  * **Main Path**: Proceed as if the entity was captured, perhaps with a default value.
  * **Alternate Path**: Redirect to a different part of the conversation that doesn't require the entity.

**Example**

* *Entity*: `PhoneNumber`
* *Trigger Phrase*: "I don't have a phone."
* *Exit Action*: The agent replies, "No problem, we'll proceed without a phone number," and continues the conversation.