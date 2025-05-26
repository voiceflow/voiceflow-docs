---
title: Microsoft LUIS - NLU Model Export
excerpt: Learn how to use our NLU export with Microsoft LUIS
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Quick Reference

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Data
      </th>

      <th style={{ textAlign: "left" }}>
        Support
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        File format
      </td>

      <td style={{ textAlign: "left" }}>
        JSON
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **Data Support**
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Intents
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Training Phrases
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Entities
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Synonyms
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **Import Type** 
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Modify
      </td>

      <td style={{ textAlign: "left" }}>
        ❌
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Overwrite
      </td>

      <td style={{ textAlign: "left" }}>
        ✅
      </td>
    </tr>
  </tbody>
</Table>

## Sample Export

```json project_burger.json
{
   "name":"6203f8ed4fbf39001b95e759",
   "desc":"",
   "culture":"en-us",
   "intents":[
      {
         "name":"place_order_demo"
      },
      {
         "name":"dm_316c6d5f13_place_order_demo"
      }
   ],
   "entities":[
      {
         "name":"sandwich_demo",
         "features":[
            
         ]
      },
      {
         "name":"side_demo",
         "features":[
            
         ]
      },
      {
         "name":"drink_demo",
         "features":[
            
         ]
      }
   ],
   "patterns":[
      {
         "intent":"place_order_demo",
         "pattern":"{drink_demo}"
      },
      {
         "intent":"place_order_demo",
         "pattern":"{side_demo}"
      },
      {
         "intent":"place_order_demo",
         "pattern":"{sandwich_demo} with {side_demo} and a {drink_demo}"
      },
      {
         "intent":"place_order_demo",
         "pattern":"need a {sandwich_demo} and a {side_demo} and a {drink_demo}"
      },
      {
         "intent":"place_order_demo",
         "pattern":"My order is {sandwich_demo}"
      },
      {
         "intent":"place_order_demo",
         "pattern":"I want a {sandwich_demo} with {drink_demo}"
      },
      {
         "intent":"place_order_demo",
         "pattern":"{sandwich_demo} please"
      },
      {
         "intent":"place_order_demo",
         "pattern":"{sandwich_demo}"
      },
      {
         "intent":"place_order_demo",
         "pattern":"Give me a {sandwich_demo} and {side_demo}"
      },
      {
         "intent":"place_order_demo",
         "pattern":"I'd like to order a {sandwich_demo} with {side_demo} and a {drink_demo}"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} How about a {sandwich_demo}"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} I want a {sandwich_demo}"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} {sandwich_demo}"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} a {sandwich_demo}"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} {sandwich_demo} please"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} give me a {sandwich_demo}"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} I asked for {side_demo}"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} some {side_demo}"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} {side_demo}"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} I want {side_demo}"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} {side_demo} please"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} give me {side_demo}"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} {drink_demo} please"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} I asked for a {drink_demo}"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} {drink_demo}"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} a {drink_demo}"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} I want a {drink_demo}"
      },
      {
         "intent":"dm_316c6d5f13_place_order_demo",
         "pattern":"{dm_316c6d5f13} give me a {drink_demo}"
      }
   ],
   "settings":[
      
   ],
   "versionId":"0.1",
   "composites":[
      
   ],
   "utterances":[
      {
         "text":"Coke",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":0,
               "endPos":3,
               "entity":"drink_demo"
            }
         ]
      },
      {
         "text":"Fries",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":0,
               "endPos":4,
               "entity":"side_demo"
            }
         ]
      },
      {
         "text":"I'd like to order a combo",
         "intent":"place_order_demo",
         "entities":[
            
         ]
      },
      {
         "text":"Hamburger with fry and a coca cola",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":0,
               "endPos":8,
               "entity":"sandwich_demo"
            },
            {
               "startPos":15,
               "endPos":17,
               "entity":"side_demo"
            },
            {
               "startPos":25,
               "endPos":33,
               "entity":"drink_demo"
            }
         ]
      },
      {
         "text":"need a burger and a a fries and a pepsi",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":7,
               "endPos":12,
               "entity":"sandwich_demo"
            },
            {
               "startPos":20,
               "endPos":26,
               "entity":"side_demo"
            },
            {
               "startPos":34,
               "endPos":38,
               "entity":"drink_demo"
            }
         ]
      },
      {
         "text":"My order is single",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":12,
               "endPos":17,
               "entity":"sandwich_demo"
            }
         ]
      },
      {
         "text":"I want a plain burger with Sprite",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":9,
               "endPos":20,
               "entity":"sandwich_demo"
            },
            {
               "startPos":27,
               "endPos":32,
               "entity":"drink_demo"
            }
         ]
      },
      {
         "text":"Cheeseburger please",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":0,
               "endPos":11,
               "entity":"sandwich_demo"
            }
         ]
      },
      {
         "text":"cheeseburg",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":0,
               "endPos":9,
               "entity":"sandwich_demo"
            }
         ]
      },
      {
         "text":"Give me a a cheeseburger and some fries",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":10,
               "endPos":23,
               "entity":"sandwich_demo"
            },
            {
               "startPos":29,
               "endPos":38,
               "entity":"side_demo"
            }
         ]
      },
      {
         "text":"I'd like to order a cheese burger with french fries and a seven up",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":20,
               "endPos":32,
               "entity":"sandwich_demo"
            },
            {
               "startPos":39,
               "endPos":50,
               "entity":"side_demo"
            },
            {
               "startPos":58,
               "endPos":65,
               "entity":"drink_demo"
            }
         ]
      },
      {
         "text":"Super Chicken with Poutine and a 7 up",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":0,
               "endPos":12,
               "entity":"sandwich_demo"
            },
            {
               "startPos":19,
               "endPos":25,
               "entity":"side_demo"
            },
            {
               "startPos":33,
               "endPos":36,
               "entity":"drink_demo"
            }
         ]
      },
      {
         "text":"need a chicken and a gravy and a Root Beer",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":7,
               "endPos":13,
               "entity":"sandwich_demo"
            },
            {
               "startPos":21,
               "endPos":25,
               "entity":"side_demo"
            },
            {
               "startPos":33,
               "endPos":41,
               "entity":"drink_demo"
            }
         ]
      },
      {
         "text":"I want a chicken sandwich with barks",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":9,
               "endPos":24,
               "entity":"sandwich_demo"
            },
            {
               "startPos":31,
               "endPos":35,
               "entity":"drink_demo"
            }
         ]
      },
      {
         "text":"I'd like to order a Fish Burger with fries and gravy and a barks root beer",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":20,
               "endPos":30,
               "entity":"sandwich_demo"
            },
            {
               "startPos":37,
               "endPos":51,
               "entity":"side_demo"
            },
            {
               "startPos":59,
               "endPos":73,
               "entity":"drink_demo"
            }
         ]
      },
      {
         "text":"barqs",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":0,
               "endPos":4,
               "entity":"drink_demo"
            }
         ]
      },
      {
         "text":"fish sandwich with Onion Rings and a Iced Tea",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":0,
               "endPos":12,
               "entity":"sandwich_demo"
            },
            {
               "startPos":19,
               "endPos":29,
               "entity":"side_demo"
            },
            {
               "startPos":37,
               "endPos":44,
               "entity":"drink_demo"
            }
         ]
      },
      {
         "text":"need a fish filet and a onion and a cold tea",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":7,
               "endPos":16,
               "entity":"sandwich_demo"
            },
            {
               "startPos":24,
               "endPos":28,
               "entity":"side_demo"
            },
            {
               "startPos":36,
               "endPos":43,
               "entity":"drink_demo"
            }
         ]
      },
      {
         "text":"I want a fish with nestea",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":9,
               "endPos":12,
               "entity":"sandwich_demo"
            },
            {
               "startPos":19,
               "endPos":24,
               "entity":"drink_demo"
            }
         ]
      },
      {
         "text":"I'd like to order a Veggie Burger with rings and a Water",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":20,
               "endPos":32,
               "entity":"sandwich_demo"
            },
            {
               "startPos":39,
               "endPos":43,
               "entity":"side_demo"
            },
            {
               "startPos":51,
               "endPos":55,
               "entity":"drink_demo"
            }
         ]
      },
      {
         "text":"onions",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":0,
               "endPos":5,
               "entity":"side_demo"
            }
         ]
      },
      {
         "text":"vegetable sandwich with Salad and a Sprite",
         "intent":"place_order_demo",
         "entities":[
            {
               "startPos":0,
               "endPos":17,
               "entity":"sandwich_demo"
            },
            {
               "startPos":24,
               "endPos":28,
               "entity":"side_demo"
            },
            {
               "startPos":36,
               "endPos":41,
               "entity":"drink_demo"
            }
         ]
      },
      {
         "text":"316c6d5f13 How about a Hamburger",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":23,
               "endPos":31,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 I want a burger",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":20,
               "endPos":25,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 single",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":16,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 a plain burger",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":13,
               "endPos":24,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 Cheeseburger please",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":22,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 give me a cheeseburg",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":21,
               "endPos":30,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 a cheeseburger",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":24,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 How about a cheese burger",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":23,
               "endPos":35,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 I want a Super Chicken",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":20,
               "endPos":32,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 chicken",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":17,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 a chicken sandwich",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":13,
               "endPos":28,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 Fish Burger please",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":21,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 give me a fish sandwich",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":21,
               "endPos":33,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 fish filet",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":20,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 How about a fish",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":23,
               "endPos":26,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 I want a Veggie Burger",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":20,
               "endPos":32,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 vegetable sandwich",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":28,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 a vegetarian sandwich",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":13,
               "endPos":31,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 veggie sandwich please",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":25,
               "entity":"sandwich_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 I asked for Fries",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":23,
               "endPos":27,
               "entity":"side_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 some fry",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":16,
               "endPos":18,
               "entity":"side_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 a fries",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":17,
               "entity":"side_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 I want some fries",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":18,
               "endPos":27,
               "entity":"side_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 french fries please",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":22,
               "entity":"side_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 give me Poutine",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":19,
               "endPos":25,
               "entity":"side_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 gravy",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":15,
               "entity":"side_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 I asked for fries and gravy",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":23,
               "endPos":37,
               "entity":"side_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 some Onion Rings",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":16,
               "endPos":26,
               "entity":"side_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 onion",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":15,
               "entity":"side_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 I want rings",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":18,
               "endPos":22,
               "entity":"side_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 onions please",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":16,
               "entity":"side_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 give me Salad",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":19,
               "endPos":23,
               "entity":"side_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 Coke please",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":14,
               "entity":"drink_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 I asked for a coca cola",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":25,
               "endPos":33,
               "entity":"drink_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 pepsi",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":15,
               "entity":"drink_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 a Sprite",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":13,
               "endPos":18,
               "entity":"drink_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 I want a seven up",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":20,
               "endPos":27,
               "entity":"drink_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 give me a 7 up",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":21,
               "endPos":24,
               "entity":"drink_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 Root Beer",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":19,
               "entity":"drink_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 barks please",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":15,
               "entity":"drink_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 I asked for a barks root beer",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":25,
               "endPos":39,
               "entity":"drink_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 barqs",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":15,
               "entity":"drink_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 a Iced Tea",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":13,
               "endPos":20,
               "entity":"drink_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 I want a cold tea",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":20,
               "endPos":27,
               "entity":"drink_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 give me a nestea",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":21,
               "endPos":26,
               "entity":"drink_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"316c6d5f13 Water",
         "intent":"dm_316c6d5f13_place_order_demo",
         "entities":[
            {
               "startPos":11,
               "endPos":15,
               "entity":"drink_demo"
            },
            {
               "startPos":0,
               "endPos":10,
               "entity":"dm_316c6d5f13"
            }
         ]
      },
      {
         "text":"Time flies like an arrow, but fruit flies like a banana",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"The quick brown fox jumps over the lazy dog",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"Pack my box with five dozen liquor jugs",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"The five boxing wizards jump quickly",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"The horse raced past the barn fell",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"Her scream silenced the rowdy teenagers",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"Be careful with that butter knife",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"It didn't make sense unless you had the power to eat colors",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"The gloves protect my feet from excess work",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"She had some amazing news to share but nobody to share it with",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"All you need to do is pick up the pen and begin",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"What’s your very first memory",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"Is there anything about yourself you’ve never told another soul",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"Free if you bring a gnome costume",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"Pink horses galloped across the sea",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"You bite up because of your lower jaw",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"I'd rather be a bird than a fish",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"Seek success, but always be prepared for random cats",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"The ants enjoyed the barbecue more than the family",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"It was getting dark, and we weren’t there yet",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"The tree fell unexpectedly short",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"If you could domesticate any animal in the world, which would you pick",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"Why do you do what you do",
         "intent":"None",
         "entities":[
            
         ]
      },
      {
         "text":"When is the last time you experienced nostalgia",
         "intent":"None",
         "entities":[
            
         ]
      }
   ],
   "closedLists":[
      
   ],
   "phraselists":[
      {
         "name":"sandwich_demo",
         "mode":true,
         "words":"Hamburger,burger,single,plainburger,Cheeseburger,cheeseburg,acheeseburger,cheeseburger,SuperChicken,chicken,chickensandwich,FishBurger,fishsandwich,fishfilet,fish,VeggieBurger,vegetablesandwich,vegetariansandwich,veggiesandwich",
         "activated":true,
         "enabledForAllModels":false
      },
      {
         "name":"side_demo",
         "mode":true,
         "words":"Fries,fry,afries,somefries,frenchfries,Poutine,gravy,friesandgravy,OnionRings,onion,rings,onions,Salad",
         "activated":true,
         "enabledForAllModels":false
      },
      {
         "name":"drink_demo",
         "mode":true,
         "words":"Coke,cocacola,pepsi,Sprite,sevenup,7up,RootBeer,barks,barksrootbeer,barqs,IcedTea,coldtea,nestea,Water",
         "activated":true,
         "enabledForAllModels":false
      }
   ],
   "modelFeatures":[
      {
         "name":"sandwich_demo",
         "mode":true,
         "words":"Hamburger,burger,single,plainburger,Cheeseburger,cheeseburg,acheeseburger,cheeseburger,SuperChicken,chicken,chickensandwich,FishBurger,fishsandwich,fishfilet,fish,VeggieBurger,vegetablesandwich,vegetariansandwich,veggiesandwich",
         "activated":true,
         "enabledForAllModels":false
      },
      {
         "name":"side_demo",
         "mode":true,
         "words":"Fries,fry,afries,somefries,frenchfries,Poutine,gravy,friesandgravy,OnionRings,onion,rings,onions,Salad",
         "activated":true,
         "enabledForAllModels":false
      },
      {
         "name":"drink_demo",
         "mode":true,
         "words":"Coke,cocacola,pepsi,Sprite,sevenup,7up,RootBeer,barks,barksrootbeer,barqs,IcedTea,coldtea,nestea,Water",
         "activated":true,
         "enabledForAllModels":false
      }
   ],
   "hierarchicals":[
      
   ],
   "regexFeatures":[
      
   ],
   "prebuiltEntities":[
      
   ],
   "tokenizerVersion":"1.0.0",
   "luis_schema_version":"7.0.0",
   "patternAnyEntities":[
      
   ],
   "regex_entities":[
      {
         "name":"dm_316c6d5f13",
         "regexPattern":"316c6d5f13"
      }
   ]
}
```
