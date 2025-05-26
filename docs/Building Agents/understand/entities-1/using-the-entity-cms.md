---
title: Using the Entities CMS
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
![](https://files.readme.io/94e1659ad287d0c73e7ac0d239137f925d9be3e1d3340de5e1384c2958aeb2fd-image.png)

## Accessing the Entities CMS

1. **Open Your Voiceflow Project**: Navigate to your project's dashboard.
2. **Go to the Entities CMS**: Click on the **"Entities"** tab or access it via the project menu.

## Creating an Entity

1. **Click on the 'New entity' button** located in the upper right area of the screen within the Entities CMS interface.
2. A dialog box will appear prompting you to define the new entity.
3. **Enter a name** for the entity in the 'Name' field. The name should represent the kind of information the entity will hold, like "city\_name" or "product\_type".
4. Choose a **'Data type'** from the drop-down menu. This could be 'Custom' for unique data types or something predefined like 'Number', 'Date', etc.
5. Under 'Values', **enter possible values** that the entity can take. You can also add synonyms for each value to ensure that the AI recognizes different variations of the same value.
6. Once completed, **click 'Create entity'** to save the new entity to your CMS.

## Editing Entity Details

![](https://files.readme.io/beda8ed249831db50c20f3d8360e55a55f0083206549dbc88da6abe72acb3785-image.png)

<br />

1. In the entity details panel, **click on a value or synonym** to edit or delete it.
2. **Add new entity values** or synonyms by adding new utterances or clicking 'Generate.'
3. **Remove irrelevant entity values** by clicking the '-' next to the item.
4. Make sure to **update the description** if the intent's purpose has evolved over time.
5. **Adjust the data type** if the nature of the entity changes.

## Deleting an Entity

### Single Entity

1. To delete a single entity, **select the entity** you wish to remove, and in the editor view click the '...' (more options) button, and **select 'Delete'** from the dropdown menu.
2. Confirm the deletion when prompted to remove the entity from your CMS.

### Bulk Deleting Entities

1. For bulk actions, **select multiple entities** by selecting the checkboxes next to the entity names.
2. Once selected, on the **bulk action toolbar** above the table, **click the 'Delete' button** to initiate the bulk deletion process.
3. **Confirm the bulk deletion** to remove all selected entities simultaneously.

## Entity Types

Entity types indicate the type of data the entity is capturing. Depending on your assistant type, you will notice a dropdown of various entity types available for your building experience.

### Custom Entities

These are the entities that can be defined by the conversation designer as per their use case.

### System-Defined Entities (legacy)

> 🚧
>
> With the introduction of entity collection using LLMs, system-defined entity types should be complemented with entity rules that specify the entity value requirements.

The system entities are commonly used entities that are pre-defined in the system. In Voiceflow, there are 14 pre-defined entity types for English-based projects:

| Entity Types | Description                                                                                                                                                                                 |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| NAME         | Describes the name of a person, including first names, last names, or full names. For example, when asking for a user's name, they might reply with "Louise" or "Jen Zhong."                |
| EMAIL        | Represents an email address. Useful in scenarios where you need to contact the user or send them information. An example response might be "[bob@voiceflow.com](mailto:bob@voiceflow.com)." |
| PHONENUMBER  | Captures phone numbers, like "(650) 253-0000."                                                                                                                                              |
| PERCENTAGE   | Recognizes percentages, like "8 percent" of a task being done.                                                                                                                              |
| GEOGRAPHY    | Relates to geographical locations such as cities, countries, continents. A user may mention they are located in "South America."                                                            |
| NUMBER       | Identifies numerical values, like "259223723" or "four hundred and twenty-one."                                                                                                             |
| TEMPERATURE  | Deals with temperature values, such as "18 below" Celsius.                                                                                                                                  |
| DIMENSION    | Pertains to measurements, such as length, volume, or area. For example, "86 square feet."                                                                                                   |
| DATETIME     | Captures dates and times in various formats, like "21/02/2018" or "Today."                                                                                                                  |
| CURRENCY     | Refers to monetary amounts in various currencies.                                                                                                                                           |
| AGE          | Indicates the age of a person, like "I am 54."                                                                                                                                              |
| KEY\_PHRASE  | *Deprecated*: A concept or subject to capture. Best to use a custom entity.                                                                                                                 |
| URL          | Captures web addresses like "[https://en.wikipedia.org](https://en.wikipedia.org)."                                                                                                         |
| ORDINAL      | Recognizes ordinal numbers, like "first" in a race or "23rd" in a series.                                                                                                                   |

### Extending System Defined Entities

If you have a specific pattern that you are expecting, you can extend the entity.

1. For example, if you are looking for 5-digit numbers, you can either create a number intent and add examples of 5-digit numbers or use a custom intent.
2. If your entity is surrounded by certain terms like "Hi my name is Bob," adding example utterances to the capture or intent step is helpful.

## Tips for Entity Management

* **Understand your domain**: Create entities that capture the essential information relevant to your application's domain.
* **Define clear purposes**: Each entity should have a clear purpose, like "flight\_date" for capturing dates related to flights.
* **Granularity matters**: Design entities to be as granular as needed for your application. For example, "departure\_city" and "arrival\_city" are better than a single "city" entity.
* **Consider synonyms and variations**: Include common synonyms and variations, like "beverage," "drink," "soda," and "pop."
* **Regularly expand entities**: As you gather more data from user interactions, expand your entities to include new phrases and terms.
* **Avoid overlapping entities**: Ensure entities are distinct and don’t capture information that could be better suited to another entity.
