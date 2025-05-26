---
title: Catching Code Step Errors
excerpt: Quick tip for debugging errors in your code steps
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
To capture an error message after a code step execution, use a `try...catch` statement to flag that an error is present and pass the message into a variable that can be returned in a text or speak step.

<Image title="272387476_502377051237065_8100288661843553294_n (1).png" alt={477} src="https://files.readme.io/c0e1374-272387476_502377051237065_8100288661843553294_n_1.png">
  Code Step Catch Error
</Image>

#### Sample Project file

```json catch_error.vf
{
  "_version": "1.2",
  "project": {
    "_id": "621a46bb12fa84001c7a29bd",
    "name": "Code Block // Catch Errors",
    "creatorID": 81810,
    "teamID": "9YnzG0XEbK",
    "image": "https://s3.amazonaws.com/com.getstoryflow.api.images/1592498945123-icons8-error.png",
    "platformData": {
      "products": {}
    },
    "members": [],
    "devVersion": "621a46bb12fa84001c7a29be",
    "privacy": "private",
    "platform": "alexa",
    "_version": 1.2,
    "prototype": {
      "nlp": {
        "type": "LUIS",
        "appID": "4682741d-e3ac-4550-b724-8573739efb9e",
        "resourceID": "https://us-0.cognitiveservices.azure.com/"
      },
      "data": {},
      "lastTrainedTime": 1645889240078,
      "trainedModel": {
        "intents": [
          {
            "key": "VF.HELP",
            "name": "VF.HELP",
            "slots": [],
            "inputs": [
              {
                "text": "help"
              },
              {
                "text": "help me"
              },
              {
                "text": "i need help"
              },
              {
                "text": "Help"
              }
            ]
          },
          {
            "key": "VF.NO",
            "name": "VF.NO",
            "slots": [],
            "inputs": [
              {
                "text": "no"
              },
              {
                "text": "nope"
              },
              {
                "text": "nay"
              },
              {
                "text": "nah"
              },
              {
                "text": "no way"
              },
              {
                "text": "negative"
              },
              {
                "text": "No"
              }
            ]
          },
          {
            "key": "VF.YES",
            "name": "VF.YES",
            "slots": [],
            "inputs": [
              {
                "text": "yes"
              },
              {
                "text": "yea"
              },
              {
                "text": "ok"
              },
              {
                "text": "okay"
              },
              {
                "text": "yup"
              },
              {
                "text": "ya"
              },
              {
                "text": "sure"
              },
              {
                "text": "Yes"
              }
            ]
          },
          {
            "key": "VF.STOP",
            "name": "VF.STOP",
            "slots": [],
            "inputs": [
              {
                "text": "stop"
              },
              {
                "text": "Stop"
              }
            ]
          }
        ],
        "slots": []
      }
    },
    "createdAt": "2022-02-26T15:26:51.000Z"
  },
  "version": {
    "_id": "621a46bb12fa84001c7a29be",
    "projectID": "621a46bb12fa84001c7a29bd",
    "creatorID": 81810,
    "name": "Code Block // Catch Errors",
    "variables": [
      "access_token",
      "error",
      "errorMessage",
      "debug"
    ],
    "platformData": {
      "publishing": {
        "forExport": true,
        "hasAds": false,
        "summary": "Enter your summary for the skill Code Block Catch Errors",
        "invocationName": "Code Block Catch Errors",
        "locales": [
          "en-US"
        ],
        "category": null,
        "personal": false,
        "keywords": "",
        "smallIcon": "https://s3.amazonaws.com/com.getstoryflow.api.images/1592498948485-icons8-error.png",
        "largeIcon": "https://s3.amazonaws.com/com.getstoryflow.api.images/1592498945123-icons8-error.png",
        "description": "Enter your description for the skill Code Block Catch Errors",
        "invocations": [
          "open Code Block Catch Errors",
          "start Code Block Catch Errors",
          "launch Code Block Catch Errors"
        ],
        "hasPurchase": false,
        "forChildren": false,
        "instructions": "Sample Instruction",
        "privacyPolicy": "https://creator.voiceflow.com/creator/terms?name=Nicolas%20Arcay&skill=Code%20Block%20//%20Catch%20Errors&children=false",
        "termsAndConditions": "https://creator.voiceflow.com/creator/terms?name=Nicolas%20Arcay&skill=Code%20Block%20//%20Catch%20Errors&children=false",
        "updatesDescription": ""
      },
      "settings": {
        "error": {
          "voice": "Alexa",
          "content": ""
        },
        "repeat": "ALL",
        "events": null,
        "session": {
          "type": "restart"
        },
        "permissions": [],
        "accountLinking": null,
        "customInterface": false
      },
      "slots": [],
      "intents": [
        {
          "key": "AMAZON.CancelIntent",
          "name": "AMAZON.CancelIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.FallbackIntent",
          "name": "AMAZON.FallbackIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.HelpIntent",
          "name": "AMAZON.HelpIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.LoopOffIntent",
          "name": "AMAZON.LoopOffIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.LoopOnIntent",
          "name": "AMAZON.LoopOnIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.MoreIntent",
          "name": "AMAZON.MoreIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.NextIntent",
          "name": "AMAZON.NextIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.NoIntent",
          "name": "AMAZON.NoIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.YesIntent",
          "name": "AMAZON.YesIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.StopIntent",
          "name": "AMAZON.StopIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.ResumeIntent",
          "name": "AMAZON.ResumeIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.RepeatIntent",
          "name": "AMAZON.RepeatIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.PreviousIntent",
          "name": "AMAZON.PreviousIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.PauseIntent",
          "name": "AMAZON.PauseIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.StartOverIntent",
          "name": "AMAZON.StartOverIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.ShuffleOnIntent",
          "name": "AMAZON.ShuffleOnIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.ShuffleOffIntent",
          "name": "AMAZON.ShuffleOffIntent",
          "slots": [],
          "inputs": []
        },
        {
          "key": "AMAZON.SelectIntent",
          "name": "AMAZON.SelectIntent",
          "slots": [],
          "inputs": []
        }
      ],
      "status": {
        "stage": "DEV"
      }
    },
    "rootDiagramID": "621a46bb12fa84001c7a29c0",
    "prototype": {
      "data": {
        "name": "Code Block // Catch Errors",
        "locales": [
          "en-US"
        ]
      },
      "model": {
        "intents": [
          {
            "key": "VF.HELP",
            "name": "VF.HELP",
            "slots": [],
            "inputs": [
              {
                "text": "help"
              },
              {
                "text": "help me"
              },
              {
                "text": "i need help"
              },
              {
                "text": "Help"
              }
            ]
          },
          {
            "key": "VF.NO",
            "name": "VF.NO",
            "slots": [],
            "inputs": [
              {
                "text": "no"
              },
              {
                "text": "nope"
              },
              {
                "text": "nay"
              },
              {
                "text": "nah"
              },
              {
                "text": "no way"
              },
              {
                "text": "negative"
              },
              {
                "text": "No"
              }
            ]
          },
          {
            "key": "VF.YES",
            "name": "VF.YES",
            "slots": [],
            "inputs": [
              {
                "text": "yes"
              },
              {
                "text": "yea"
              },
              {
                "text": "ok"
              },
              {
                "text": "okay"
              },
              {
                "text": "yup"
              },
              {
                "text": "ya"
              },
              {
                "text": "sure"
              },
              {
                "text": "Yes"
              }
            ]
          },
          {
            "key": "VF.STOP",
            "name": "VF.STOP",
            "slots": [],
            "inputs": [
              {
                "text": "stop"
              },
              {
                "text": "Stop"
              }
            ]
          }
        ],
        "slots": []
      },
      "context": {
        "stack": [
          {
            "storage": {},
            "variables": {},
            "programID": "621a46bb12fa84001c7a29c0"
          }
        ],
        "variables": {}
      },
      "settings": {},
      "platform": "alexa"
    },
    "components": [
      {
        "sourceID": "621a46bb12fa84001c7a29bf",
        "type": "DIAGRAM"
      },
      {
        "sourceID": "621a46bb12fa84001c7a29c1",
        "type": "DIAGRAM"
      },
      {
        "sourceID": "621a46bb12fa84001c7a29c2",
        "type": "DIAGRAM"
      }
    ],
    "topics": [
      {
        "sourceID": "621a46bb12fa84001c7a29c0",
        "type": "DIAGRAM"
      }
    ]
  },
  "diagrams": {
    "621a46bb12fa84001c7a29bf": {
      "_id": "621a46bb12fa84001c7a29bf",
      "offsetX": 361.81006617692776,
      "offsetY": -161.72237149853413,
      "zoom": 107.2755839029948,
      "modified": 1645889232,
      "children": [],
      "creatorID": 81810,
      "variables": [],
      "name": "Stop Flow",
      "versionID": "621a46bb12fa84001c7a29be",
      "nodes": {
        "5f9f58c34b2e0220c2860639": {
          "nodeID": "5f9f58c34b2e0220c2860639",
          "type": "start",
          "coords": [
            247.73741727884033,
            452.15296437316766
          ],
          "data": {
            "name": "Start",
            "color": "standard",
            "steps": [],
            "ports": [
              {
                "type": "next",
                "target": "5f9f58c34b2e0220c286063b",
                "id": "621a46cbdd3b2dd06dfd73fe"
              }
            ]
          }
        },
        "5f9f58c34b2e0220c286063a": {
          "nodeID": "5f9f58c34b2e0220c286063a",
          "type": "block",
          "coords": [
            660,
            453.54871427430436
          ],
          "data": {
            "name": "Exit",
            "color": "standard",
            "steps": [
              "5f9f58c34b2e0220c286063b",
              "5f9f58c34b2e0220c286063c"
            ]
          }
        },
        "5f9f58c34b2e0220c286063b": {
          "nodeID": "5f9f58c34b2e0220c286063b",
          "type": "speak",
          "data": {
            "randomize": false,
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "You said stop. This session is now ending."
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "5f9f58c34b2e0220c286063c",
                "id": "621a46cbdd3b2dd06dfd73ff"
              }
            ]
          }
        },
        "5f9f58c34b2e0220c286063c": {
          "nodeID": "5f9f58c34b2e0220c286063c",
          "type": "exit",
          "data": {
            "ports": []
          }
        }
      },
      "type": "COMPONENT"
    },
    "621a46bb12fa84001c7a29c0": {
      "_id": "621a46bb12fa84001c7a29c0",
      "offsetX": 728.6707387742962,
      "offsetY": -161.49891649268352,
      "zoom": 80,
      "modified": 1645889271,
      "children": [
        "621a46bb12fa84001c7a29bf",
        "621a46bb12fa84001c7a29c1",
        "621a46bb12fa84001c7a29c2"
      ],
      "creatorID": 81810,
      "variables": [],
      "name": "ROOT",
      "versionID": "621a46bb12fa84001c7a29be",
      "nodes": {
        "5f9f58c34b2e0220c286063d": {
          "nodeID": "5f9f58c34b2e0220c286063d",
          "type": "block",
          "coords": [
            168.36122865790668,
            452.25891232677327
          ],
          "data": {
            "name": "Code",
            "color": "blue",
            "steps": [
              "5f9f58c34b2e0220c286063e",
              "605b7a96d85ee075a9564f3e"
            ]
          }
        },
        "5f9f58c34b2e0220c286063e": {
          "nodeID": "5f9f58c34b2e0220c286063e",
          "type": "code",
          "data": {
            "code": "errorMessage = \"\";\nerror = 0;\n\ntry {\n  let debug = \"something\"\n  // take = newDate(); // this will throw exception\n  let json = JSON.parse('\"age\": 30 }'); // incomplete data\n}\ncatch (e) {\n  error = 1;\n  errorMessage = e.message;\n}",
            "ports": [
              {
                "type": "next",
                "target": "605b7a96d85ee075a9564f3e",
                "id": "5fd799d5a7df0d6382da66ca"
              },
              {
                "type": "fail",
                "target": "605b7a96d85ee075a9564f3e",
                "id": "5fd799d5a7df0d6382da66cb"
              }
            ]
          }
        },
        "5f9f58c34b2e0220c2860644": {
          "nodeID": "5f9f58c34b2e0220c2860644",
          "type": "start",
          "coords": [
            -210.83842346787014,
            451.8736456158544
          ],
          "data": {
            "name": "Start",
            "color": "standard",
            "steps": [
              "5f9f58c34b2e0220c2860645",
              "5f9f58c34b2e0220c2860646"
            ],
            "ports": [
              {
                "type": "next",
                "target": "5f9f58c34b2e0220c286063e",
                "id": "5fd799d5a7df0d6382da66d0"
              }
            ]
          }
        },
        "5f9f58c34b2e0220c2860645": {
          "nodeID": "5f9f58c34b2e0220c2860645",
          "type": "command",
          "data": {
            "name": "Stop",
            "next": null,
            "ports": [],
            "intent": "AMAZON.StopIntent",
            "mappings": [],
            "diagramID": "621a46bb12fa84001c7a29bf"
          }
        },
        "5f9f58c34b2e0220c2860646": {
          "nodeID": "5f9f58c34b2e0220c2860646",
          "type": "command",
          "data": {
            "name": "Help",
            "next": null,
            "ports": [],
            "intent": "AMAZON.HelpIntent",
            "mappings": [],
            "diagramID": "621a46bb12fa84001c7a29c1"
          }
        },
        "605b7a96d85ee075a9564f3e": {
          "nodeID": "605b7a96d85ee075a9564f3e",
          "type": "flow",
          "data": {
            "diagramID": "621a46bb12fa84001c7a29c2",
            "variableMap": null,
            "ports": [
              {
                "type": "next",
                "target": null,
                "id": "605b7a96d85ee075a9564f41"
              }
            ]
          }
        }
      },
      "type": "TOPIC"
    },
    "621a46bb12fa84001c7a29c1": {
      "_id": "621a46bb12fa84001c7a29c1",
      "offsetX": 272,
      "offsetY": 104,
      "zoom": 80,
      "modified": 1604278467,
      "children": [],
      "creatorID": 81810,
      "variables": [],
      "name": "Help Flow",
      "versionID": "621a46bb12fa84001c7a29be",
      "nodes": {
        "5f9f58c34b2e0220c2860649": {
          "nodeID": "5f9f58c34b2e0220c2860649",
          "type": "start",
          "coords": [
            360,
            120
          ],
          "data": {
            "name": "Start",
            "color": "standard",
            "ports": [
              {
                "type": "",
                "target": "5f9f58c34b2e0220c286064b"
              }
            ],
            "steps": []
          }
        },
        "5f9f58c34b2e0220c286064a": {
          "nodeID": "5f9f58c34b2e0220c286064a",
          "type": "block",
          "coords": [
            760,
            120
          ],
          "data": {
            "name": "Help Message",
            "color": "standard",
            "steps": [
              "5f9f58c34b2e0220c286064b",
              "5f9f58c34b2e0220c286064c"
            ]
          }
        },
        "5f9f58c34b2e0220c286064b": {
          "nodeID": "5f9f58c34b2e0220c286064b",
          "type": "speak",
          "data": {
            "randomize": false,
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "You said help. Do you want to continue?"
              }
            ],
            "ports": [
              {
                "type": "",
                "target": "5f9f58c34b2e0220c286064c"
              }
            ]
          }
        },
        "5f9f58c34b2e0220c286064c": {
          "nodeID": "5f9f58c34b2e0220c286064c",
          "type": "interaction",
          "data": {
            "name": "Choice",
            "else": {
              "type": "path",
              "randomize": false,
              "reprompts": []
            },
            "choices": [
              {
                "intent": "AMAZON.YesIntent",
                "mappings": []
              },
              {
                "intent": "AMAZON.NoIntent",
                "mappings": []
              }
            ],
            "reprompt": null,
            "ports": [
              {
                "type": "else",
                "target": null
              },
              {
                "type": "",
                "target": null
              },
              {
                "type": "",
                "target": "5f9f58c34b2e0220c286064e"
              }
            ]
          }
        },
        "5f9f58c34b2e0220c286064d": {
          "nodeID": "5f9f58c34b2e0220c286064d",
          "type": "block",
          "coords": [
            1170,
            260
          ],
          "data": {
            "name": "Exit",
            "color": "standard",
            "steps": [
              "5f9f58c34b2e0220c286064e"
            ]
          }
        },
        "5f9f58c34b2e0220c286064e": {
          "nodeID": "5f9f58c34b2e0220c286064e",
          "type": "exit",
          "data": {
            "ports": []
          }
        }
      }
    },
    "621a46bb12fa84001c7a29c2": {
      "_id": "621a46bb12fa84001c7a29c2",
      "offsetX": 272,
      "offsetY": 104,
      "zoom": 80,
      "variables": [],
      "children": [],
      "versionID": "621a46bb12fa84001c7a29be",
      "creatorID": 81810,
      "name": "Error Flow",
      "modified": 1645889267,
      "nodes": {
        "605b7a9cd85ee075a9564f45": {
          "nodeID": "605b7a9cd85ee075a9564f45",
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
                "target": "605b7aa7d85ee075a9564f6f",
                "id": "605b7a9dd85ee075a9564f46"
              }
            ]
          }
        },
        "605b7aa7d85ee075a9564f7c": {
          "nodeID": "605b7aa7d85ee075a9564f7c",
          "type": "speak",
          "data": {
            "randomize": false,
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "Error: {{[errorMessage].errorMessage}} "
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "605b7ab2d85ee075a9564f94",
                "id": "605b7aa7d85ee075a9564f7d"
              }
            ]
          }
        },
        "605b7aa7d85ee075a9564f79": {
          "nodeID": "605b7aa7d85ee075a9564f79",
          "type": "speak",
          "data": {
            "randomize": false,
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "ok "
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": null,
                "id": "605b7aa7d85ee075a9564f7a"
              }
            ]
          }
        },
        "605b7aa7d85ee075a9564f75": {
          "nodeID": "605b7aa7d85ee075a9564f75",
          "type": "ifV2",
          "data": {
            "expressions": [
              {
                "type": null,
                "value": [
                  {
                    "logicInterface": "variable",
                    "type": "equals",
                    "value": [
                      {
                        "type": "variable",
                        "value": "error"
                      },
                      {
                        "type": "value",
                        "value": "0"
                      }
                    ]
                  }
                ]
              }
            ],
            "noMatch": {
              "type": "path",
              "pathName": "No Match"
            },
            "ports": [
              {
                "type": "else",
                "target": "605b7aa7d85ee075a9564f73",
                "id": "605b7aa7d85ee075a9564f76"
              },
              {
                "type": "1",
                "target": "605b7aa7d85ee075a9564f79",
                "id": "605b7aa7d85ee075a9564f77",
                "data": {}
              }
            ]
          }
        },
        "605b7aa7d85ee075a9564f73": {
          "nodeID": "605b7aa7d85ee075a9564f73",
          "type": "block",
          "coords": [
            716.5000040979139,
            319.77404503245214
          ],
          "data": {
            "name": "Error",
            "color": "red",
            "steps": [
              "605b7aa7d85ee075a9564f7c",
              "605b7ab2d85ee075a9564f94"
            ]
          }
        },
        "605b7aa7d85ee075a9564f71": {
          "nodeID": "605b7aa7d85ee075a9564f71",
          "type": "block",
          "coords": [
            1097.0265565389077,
            121.22594153297163
          ],
          "data": {
            "name": "Ok",
            "color": "green",
            "steps": [
              "605b7aa7d85ee075a9564f79"
            ]
          }
        },
        "605b7aa7d85ee075a9564f6f": {
          "nodeID": "605b7aa7d85ee075a9564f6f",
          "type": "block",
          "coords": [
            717.4999959020859,
            119.77405846702845
          ],
          "data": {
            "name": "Block",
            "color": "standard",
            "steps": [
              "605b7aa7d85ee075a9564f75"
            ]
          }
        },
        "605b7ab2d85ee075a9564f94": {
          "nodeID": "605b7ab2d85ee075a9564f94",
          "type": "exit",
          "data": {
            "ports": []
          }
        }
      },
      "type": "COMPONENT"
    }
  },
  "variableStates": []
}
```
