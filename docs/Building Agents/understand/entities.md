---
title: Entities
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
An entity is a specific piece of information or data point that can be extracted from a user’s input (utterance) to provide context and detail about the user’s intent. Entities are crucial for understanding the specifics of what the user is asking or stating. Entities are primarily used in the [Capture step](https://developer.voiceflow.com/v2.0/docs/capture) when extracting information from user input, or inside intents themselves, where entities can automatically be filled out when triggering an intent. See [Intents vs Entities](https://developer.voiceflow.com/v2.0/docs/intents-vs-entities) for further explanation.

# Managing Entities

**How do I manage my conversation entities, slots, synonyms?**  
To view your assistant's entities, navigate to the **Entities** tab in the CMS.

![](https://files.readme.io/ff245ae-CleanShot_2024-06-06_at_14.35.362x.png)

## Creating Entities

To create a **New Entity**, hit the blue button in the top right of the CMS view. You can also create a new entity from any canvas locations where entities are used.

![](https://files.readme.io/83c41fb-CleanShot_2024-06-06_at_14.40.422x.png)

When creating a new entity, you’ll need to enter:

- **Entity Name** — you will notice the curly-braced {} in a colored box populate as you input a name; this will be how you invoke/input the entity in Intent utterances or any other applicable part of your assistant
- **Entity Type** — the type of data the entity is capturing, either 
- **Entity Values** — its potential values (available when using Custom Entities)
- **Entity Synonyms (optional) ** — the alternative slot values/variations of the entity values that can classify the Entity slot, and are helpful to improve the recognition of the entity
- **Entity Color** — this does not affect your end-user experience, it helps organize your Model Manager experience

## Entity Type

Entity types indicate the type of data the entity is capturing. Depending on your assistant type, you will notice a dropdown of various entity types available for your building experience.

In Voiceflow, there are two ways to categorize entities:

**Custom Entities**: These are the entities that can be defined by the conversation designer as per their use case.

**System-Defined Entities**: The system entities are commonly used entities that are pre-defined in the system, dependent on channel/assistant-type.

### System-Defined Entities In Voiceflow

In Voiceflow, there are a 14 pre-defined entity types for English based projects.

1. **NAME**: Describes the name of a person, including first names, last names, or full names. For example, when asking for a user's name, they might reply with “Louise” or “Jen Zhong.”
2. **EMAIL**: Represents an email address. Useful in scenarios where you need to contact the user or send them information. An example response might be “[bob@voiceflow.com.](mailto:bob@voiceflow.com.)“
3. **PHONENUMBER**: Captures phone numbers. It's applicable in situations where the user needs to provide a contact number, such as “(650) 253-0000”
4. **PERCENTAGE**: Recognizes percentages, whether written in symbols or words. This could be used when discussing completion rates, like “8 percent” of a task being done.
5. **GEOGRAPHY**: Relates to geographical locations such as cities, countries, continents. A user may mention they are located in “South America.”
6. **NUMBER**: Identifies numerical values, which can range from integers to more complex numbers like “259223723” or phrases such as “four hundred and twenty-one.”
7. **TEMPERATURE**: Deals with temperature values, which could be used for setting or querying climate control settings, like “18 below” Celsius.
8. **DIMENSION**: Pertains to measurements including length, volume, area, etc. It could be used in logistics, for instance, when a user says a package is “86 square feet”.
9. **DATETIME**: Captures dates and times in various formats. If a user is making an appointment, they might say “21/02/2018” or “Today.”
10. **CURRENCY**: Refers to monetary amounts in various currencies. This would be useful in transactions, like when a user states their budget is “5 pounds”.
11. **AGE**: Indicates the age of a person. It could be used in any context where age is relevant, like a user stating “I am 54.”
12. **KEY_PHRASE**: Deprecated: A concept or subject to capture. Best to use a custom entity.
13. **URL**: Captures web addresses. When asking for a source of information, a user might provide “<https://en.wikipedia.org/.>"
14. **ORDINAL**: Recognizes ordinal numbers that denote position or sequence, like “first” in a race or “23rd” in a series.

## Extending System Defined Entities

If you have a specific pattern that you are expecting, you can extend the entity.

1. For example, if you are looking for 5-digit numbers, you can either create a number intent and add examples of 5-digit numbers, or use a custom intent.
2. If your entity is surrounded by certain terms like “Hi, my name is Bob”, adding example utterances to the capture or intent step are helpful.

## Custom Entities

If there isn't an existing built-in Entity type for your use case, you will have to build a Custom Entity type. When building a Custom Entity type, you will manually or bulk-import the values you want your Entities to be able to capture.

## Entity Synonyms

Entity synonyms let you enter variations of what a user could say to incite the value of a particular Entity.

# Using Entities inside Intents

You can also use entities inside an intent if your utterances contain dynamic information. In the example below — the intent if for modifying an item. 

In this case, our utterances can be more generic and reference our intent. This will train the model to trigger this intent when the user says the main phrase in combination with an entity value. For best results, ensure to include examples of utterances where the entity is in different locations, so the agent can better recognize different patterns.

![](https://files.readme.io/46d56fe-CleanShot_2024-06-20_at_19.25.232x.png)