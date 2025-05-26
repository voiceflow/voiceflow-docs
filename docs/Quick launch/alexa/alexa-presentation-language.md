---
title: Alexa Presentation Language (APL)
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
In this introduction video, learn how to use APL in Voiceflow's design tool.

**Video Walkthrough** 

<Embed url="https://www.youtube.com/watch?v=cgtO64PLOwg&feature=youtu.be" title="Introduction to using APL in Voiceflow" favicon="https://www.youtube.com/s/desktop/ec801097/img/favicon.ico" image="https://i.ytimg.com/vi/cgtO64PLOwg/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=cgtO64PLOwg&feature=youtu.be" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FcgtO64PLOwg%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DcgtO64PLOwg%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FcgtO64PLOwg%252Fhqdefault.jpg%26key%3Df2aa6fc3595946d0afc3d76cbbd25dc3%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22640%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## Sample Project

```json apl_demo.vf
{
  "_version": "1.2",
  "project": {
    "_id": "621a1aac12fa84001c7a29a7",
    "name": "JSON | Response Search",
    "teamID": "ylkpJq6nRZ",
    "devVersion": "621a1aac0bcf9efe1f81e05e",
    "platform": "general",
    "platformData": {
      "invocationName": "template project general"
    },
    "members": [],
    "linkType": "STRAIGHT",
    "image": "",
    "_version": 1.2,
    "creatorID": 3600,
    "createdAt": "2022-02-26T12:18:52.000Z"
  },
  "version": {
    "_id": "621a1aac0bcf9efe1f81e05e",
    "variables": [
      "sessions",
      "user_id",
      "timestamp",
      "platform",
      "locale",
      "JSONresponse",
      "result",
      "name",
      "email",
      "probabilityLevel",
      "city"
    ],
    "platformData": {
      "slots": [],
      "intents": [],
      "settings": {
        "restart": true,
        "repeat": 100,
        "locales": [
          "en-US"
        ],
        "defaultVoice": "Alexa"
      },
      "publishing": {},
      "platform": "general"
    },
    "name": "Initial Version",
    "projectID": "621a1aac12fa84001c7a29a7",
    "rootDiagramID": "621a1aac0bcf9efe1f81e05f",
    "creatorID": 3600,
    "components": [],
    "topics": [
      {
        "sourceID": "621a1aac0bcf9efe1f81e05f",
        "type": "DIAGRAM"
      }
    ],
    "prototype": {
      "data": {
        "name": "JSON | Response Search",
        "locales": [
          "en-US"
        ]
      },
      "model": {
        "intents": [],
        "slots": []
      },
      "context": {
        "stack": [
          {
            "storage": {},
            "variables": {},
            "programID": "621a1aac0bcf9efe1f81e05f"
          }
        ],
        "variables": {}
      },
      "settings": {},
      "platform": "general"
    }
  },
  "diagrams": {
    "621a1aac0bcf9efe1f81e05f": {
      "_id": "621a1aac0bcf9efe1f81e05f",
      "offsetX": 272,
      "offsetY": 104,
      "zoom": 80,
      "variables": [],
      "name": "ROOT",
      "versionID": "621a1aac0bcf9efe1f81e05e",
      "creatorID": 3600,
      "modified": 1646003497,
      "nodes": {
        "start00000000000000000000": {
          "nodeID": "start00000000000000000000",
          "type": "start",
          "coords": [
            360,
            120
          ],
          "data": {
            "name": "Start",
            "color": "standard",
            "steps": [],
            "ports": [
              {
                "type": "next",
                "target": "621a1ac5f7720d749303cd37",
                "id": "60b7e7cad4b17f0ce7bddf11"
              }
            ]
          }
        },
        "621a1ac5f7720d749303cd33": {
          "nodeID": "621a1ac5f7720d749303cd33",
          "type": "api",
          "data": {
            "url": "https://jsonplaceholder.typicode.com/users",
            "body": [
              {
                "key": "",
                "val": ""
              }
            ],
            "params": [
              {
                "key": "",
                "val": ""
              }
            ],
            "method": "GET",
            "headers": [
              {
                "key": "",
                "val": ""
              }
            ],
            "content": "",
            "mappings": [
              {
                "path": "response",
                "var": "JSONresponse"
              }
            ],
            "bodyType": "formData",
            "selectedAction": "Make a GET Request",
            "selectedIntegration": "Custom API",
            "ports": [
              {
                "type": "next",
                "target": "621a2d4ef7720d749303cda4",
                "id": "621a1ac5f7720d749303cd35",
                "data": {
                  "points": [
                    {
                      "point": [
                        950.8548206144669,
                        259.54721664882055
                      ]
                    },
                    {
                      "point": [
                        978.0475620085099,
                        259.54721664882055
                      ]
                    },
                    {
                      "point": [
                        978.0475620085099,
                        157.55486130214092
                      ]
                    },
                    {
                      "point": [
                        1005.2403034025529,
                        157.55486130214092
                      ],
                      "allowedToTop": true
                    }
                  ]
                }
              },
              {
                "type": "fail",
                "target": null,
                "id": "621a1ac5f7720d749303cd36"
              }
            ]
          }
        },
        "621a1ac5f7720d749303cd37": {
          "nodeID": "621a1ac5f7720d749303cd37",
          "type": "block",
          "coords": [
            785.8548202784127,
            123.29726781633077
          ],
          "data": {
            "name": "Get JSON",
            "color": "blue",
            "steps": [
              "621a1ac5f7720d749303cd33"
            ]
          }
        },
        "621a1dfef7720d749303cd6e": {
          "nodeID": "621a1dfef7720d749303cd6e",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "Name: {{[name].name}} | Email: {{[email].email}} \nCity: {{[city].city}}\nProbability: {{[probabilityLevel].probabilityLevel}} "
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": null,
                "id": "621a1dfef7720d749303cd6f"
              }
            ]
          }
        },
        "621a1dfef7720d749303cd6a": {
          "nodeID": "621a1dfef7720d749303cd6a",
          "type": "code",
          "data": {
            "code": "// Nearest Neighbor\n// https://www.npmjs.com/package/nearest-neighbor\n\nconst nn = requireFromUrl('https://cdn.jsdelivr.net/npm/nearest-neighbor');\n\nvar query = { name: name, email: email };\n\nvar fields = [\n  { name: \"name\", measure: nn.comparisonMethods.word },\n  { name: \"email\", measure: nn.comparisonMethods.word }\n];\n\n\nnn.findMostSimilar(query, JSONresponse, fields, function(nearestNeighbor, probability) {\n  if(probability > probabilityLevel) {\n    probabilityLevel = probability\n    result = nearestNeighbor\n  }\n});",
            "ports": [
              {
                "type": "next",
                "target": "621a2cdcf7720d749303cd7e",
                "id": "621a1dfef7720d749303cd6c"
              },
              {
                "type": "fail",
                "target": "621a2cdcf7720d749303cd7e",
                "id": "621a1dfef7720d749303cd6b"
              }
            ]
          }
        },
        "621a1dfef7720d749303cd68": {
          "nodeID": "621a1dfef7720d749303cd68",
          "type": "block",
          "coords": [
            1600.7518026566152,
            127.32301439386661
          ],
          "data": {
            "name": "Search | Check Result",
            "color": "blue",
            "steps": [
              "621a1dfef7720d749303cd6a",
              "621a2cdcf7720d749303cd7e"
            ]
          }
        },
        "621a2697f7720d749303cd78": {
          "nodeID": "621a2697f7720d749303cd78",
          "type": "markup_image",
          "coords": [
            620.5811084562638,
            -498.8347184708083
          ],
          "data": {
            "url": "https://s3.amazonaws.com/com.getstoryflow.api.images/1645880982431-cleanshot-2022-02-26-at-14.09.07.png",
            "width": 511,
            "height": 566,
            "rotate": 0,
            "blockColor": "standard"
          }
        },
        "621a2cdcf7720d749303cd7e": {
          "nodeID": "621a2cdcf7720d749303cd7e",
          "type": "ifV2",
          "data": {
            "expressions": [
              {
                "type": null,
                "name": "Check for result",
                "value": [
                  {
                    "id": "3lo73lv4",
                    "logicInterface": "expression",
                    "type": "advance",
                    "value": "{{[result].result}}"
                  }
                ]
              }
            ],
            "noMatch": {
              "type": "path",
              "pathName": "Nothing Found"
            },
            "ports": [
              {
                "type": "else",
                "target": "621a2e16f7720d749303cdbb",
                "id": "621a2cdcf7720d749303cd81",
                "data": {
                  "points": [
                    {
                      "point": [
                        1765.751896398432,
                        327.07297027072235
                      ]
                    },
                    {
                      "point": [
                        1789.751896398432,
                        327.07297027072235
                      ]
                    },
                    {
                      "point": [
                        1789.751896398432,
                        394.19793873410384
                      ],
                      "locked": true
                    },
                    {
                      "point": [
                        1604.261818204781,
                        394.19793873410384
                      ],
                      "locked": true
                    },
                    {
                      "point": [
                        1604.261818204781,
                        430.1842091492373
                      ],
                      "toTop": true,
                      "allowedToTop": true
                    }
                  ]
                }
              },
              {
                "type": "",
                "target": "621a2cf2f7720d749303cd8c",
                "id": "621a2cdcf7720d749303cd80",
                "data": {
                  "points": [
                    {
                      "point": [
                        1765.751793270717,
                        271.57297348475805
                      ]
                    },
                    {
                      "point": [
                        1806.2289508634904,
                        271.57297348475805
                      ]
                    },
                    {
                      "point": [
                        1806.2289508634904,
                        160.16525864100805
                      ]
                    },
                    {
                      "point": [
                        1846.7061084562638,
                        160.16525864100805
                      ],
                      "allowedToTop": true
                    }
                  ],
                  "event": {
                    "type": "Check for result"
                  }
                }
              }
            ]
          }
        },
        "621a2cf2f7720d749303cd8c": {
          "nodeID": "621a2cf2f7720d749303cd8c",
          "type": "block",
          "coords": [
            2011.7061084562638,
            129.1652815291917
          ],
          "data": {
            "name": "Result",
            "color": "purple",
            "steps": [
              "621a2d03f7720d749303cd96",
              "621a1dfef7720d749303cd6e"
            ]
          }
        },
        "621a2d03f7720d749303cd96": {
          "nodeID": "621a2d03f7720d749303cd96",
          "type": "setV2",
          "data": {
            "sets": [
              {
                "type": "advance",
                "variable": "name",
                "expression": "{{[result].result}}.name"
              },
              {
                "type": "advance",
                "variable": "email",
                "expression": "{{[result].result}}.email"
              },
              {
                "type": "advance",
                "variable": "city",
                "expression": "{{[result].result}}.address.city"
              }
            ],
            "title": "Populate variables",
            "ports": [
              {
                "type": "next",
                "target": "621a1dfef7720d749303cd6e",
                "id": "621a2d03f7720d749303cd98"
              }
            ]
          }
        },
        "621a2d45f7720d749303cd9d": {
          "nodeID": "621a2d45f7720d749303cd9d",
          "type": "setV2",
          "data": {
            "sets": [
              {
                "type": "value",
                "variable": "name",
                "expression": "Leanne"
              }
            ],
            "title": "Name",
            "ports": [
              {
                "type": "next",
                "target": "621a2d78f7720d749303cdac",
                "id": "621a2d45f7720d749303cd9f"
              }
            ]
          }
        },
        "621a2d4ef7720d749303cda4": {
          "nodeID": "621a2d4ef7720d749303cda4",
          "type": "block",
          "coords": [
            1170.240284003268,
            126.55483551147069
          ],
          "data": {
            "name": "Query",
            "color": "green",
            "steps": [
              "621a2d45f7720d749303cd9d",
              "621a2d78f7720d749303cdac",
              "621a2e64f7720d749303cdc3"
            ]
          }
        },
        "621a2d78f7720d749303cdac": {
          "nodeID": "621a2d78f7720d749303cdac",
          "type": "setV2",
          "data": {
            "sets": [
              {
                "type": "value",
                "variable": "email",
                "expression": "sincere@april.biz"
              }
            ],
            "title": "Email",
            "ports": [
              {
                "type": "next",
                "target": "621a2e64f7720d749303cdc3",
                "id": "621a2d78f7720d749303cdae"
              }
            ]
          }
        },
        "621a2e16f7720d749303cdb8": {
          "nodeID": "621a2e16f7720d749303cdb8",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "No user found"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": null,
                "id": "621a2e16f7720d749303cdba"
              }
            ]
          }
        },
        "621a2e16f7720d749303cdbb": {
          "nodeID": "621a2e16f7720d749303cdbb",
          "type": "block",
          "coords": [
            1604.2618891059121,
            431.1842119986583
          ],
          "data": {
            "name": "Nothing found | Low probability",
            "color": "red",
            "steps": [
              "621a2e16f7720d749303cdb8"
            ]
          }
        },
        "621a2e64f7720d749303cdc3": {
          "nodeID": "621a2e64f7720d749303cdc3",
          "type": "setV2",
          "data": {
            "sets": [
              {
                "type": "value",
                "variable": "probabilityLevel",
                "expression": "0.2"
              }
            ],
            "title": "Probability Level",
            "ports": [
              {
                "type": "next",
                "target": "621a1dfef7720d749303cd68",
                "id": "621a2e64f7720d749303cdc5",
                "data": {
                  "points": [
                    {
                      "point": [
                        1335.2402163018842,
                        332.30485112327284
                      ]
                    },
                    {
                      "point": [
                        1385.4960070439317,
                        332.30485112327284
                      ]
                    },
                    {
                      "point": [
                        1385.4960070439317,
                        158.32305488102733
                      ]
                    },
                    {
                      "point": [
                        1435.7517977859793,
                        158.32305488102733
                      ],
                      "allowedToTop": true
                    }
                  ]
                }
              }
            ]
          }
        },
        "621a2f9bf7720d749303cdcc": {
          "nodeID": "621a2f9bf7720d749303cdcc",
          "type": "markup_image",
          "coords": [
            1147.0295553708706,
            -498.399490961978
          ],
          "data": {
            "url": "https://s3.amazonaws.com/com.getstoryflow.api.images/1645883290964-cleanshot-2022-02-26-at-14.48.00.png",
            "width": 452,
            "height": 563,
            "rotate": 0,
            "blockColor": "standard"
          }
        }
      },
      "children": [],
      "type": "TOPIC",
      "intentStepIDs": []
    }
  },
  "variableStates": []
}
```
