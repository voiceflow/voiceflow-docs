---
title: Twilio Voice
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
> 🚧 Before you start
>
> 1. **Create a Voiceflow project**: you need to first build a chat project on [Voiceflow](creator.voiceflow.com)
> 2. **Find your Project API Key**: Follow these [instructions](https://developer.voiceflow.com/reference/project) to obtain your API key.
> 3. [Template source code on Github](https://github.com/DecathectZero/twilio-adapter)

## VF file

```json movie_concierge.vf
{
  "_version": "1.2",
  "project": {
    "_id": "626c0633970711001c44065f",
    "name": "Movie Concierge",
    "teamID": "VzElVBmjL6",
    "devVersion": "626c0632ce89e0d909cb11e6",
    "platform": "general",
    "platformData": {
      "invocationName": "template project general"
    },
    "members": [],
    "linkType": "STRAIGHT",
    "image": "",
    "_version": 1.2,
    "creatorID": 12656,
    "prototype": {
      "nlp": {
        "type": "LUIS",
        "appID": "bcc82932-c87b-4d25-b800-4d363ba76e2d",
        "resourceID": "https://us-8.cognitiveservices.azure.com/"
      },
      "data": {},
      "lastTrainedTime": 1651258816053,
      "trainedModel": {
        "intents": [
          {
            "key": "ahd3bsp",
            "name": "discover_movies",
            "inputs": [
              {
                "text": "what movies are playing now",
                "slots": []
              },
              {
                "text": "what are some movies showing",
                "slots": []
              },
              {
                "text": "what movies are available now",
                "slots": []
              }
            ],
            "slots": []
          },
          {
            "key": "b02n362m",
            "name": "discover_cinemas",
            "inputs": [
              {
                "text": "what theatres are near me",
                "slots": []
              }
            ],
            "slots": []
          },
          {
            "key": "9o4c36ee",
            "name": "checkout",
            "inputs": [
              {
                "text": "I want to watch {{[movie_name].yw5136ms}} at {{[time].6r5936x6}}",
                "slots": [
                  "yw5136ms",
                  "6r5936x6"
                ]
              },
              {
                "text": "check out",
                "slots": []
              },
              {
                "text": "checkout",
                "slots": []
              }
            ],
            "slots": [
              {
                "id": "yw5136ms",
                "required": false,
                "dialog": {
                  "prompt": [],
                  "confirm": [],
                  "utterances": [],
                  "confirmEnabled": false
                }
              },
              {
                "id": "6r5936x6",
                "required": false,
                "dialog": {
                  "prompt": [
                    {
                      "text": "What time would you like to watch this movie?",
                      "slots": [],
                      "voice": ""
                    }
                  ],
                  "confirm": [],
                  "utterances": [],
                  "confirmEnabled": false
                }
              }
            ]
          },
          {
            "key": "VF.YES",
            "name": "VF.YES",
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
              }
            ],
            "slots": []
          },
          {
            "key": "VF.NO",
            "name": "VF.NO",
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
              }
            ],
            "slots": []
          },
          {
            "key": "pq1k3h4n",
            "name": "Angry Conceirge",
            "inputs": [
              {
                "text": "this is not great",
                "slots": []
              },
              {
                "text": "I'm having a terrible time",
                "slots": []
              },
              {
                "text": "your service sucks",
                "slots": []
              },
              {
                "text": "i hate you",
                "slots": []
              },
              {
                "text": "bastard",
                "slots": []
              },
              {
                "text": "bitch",
                "slots": []
              },
              {
                "text": "what did you say to me?",
                "slots": []
              },
              {
                "text": "asshole",
                "slots": []
              },
              {
                "text": "go fuck yourself",
                "slots": []
              },
              {
                "text": "fuck you",
                "slots": []
              },
              {
                "text": "you're trash",
                "slots": []
              },
              {
                "text": "you suck",
                "slots": []
              }
            ],
            "slots": []
          },
          {
            "key": "re3l3hi5",
            "name": "talk to human",
            "inputs": [
              {
                "text": "i hate robots",
                "slots": []
              },
              {
                "text": "i want a human",
                "slots": []
              },
              {
                "text": "i want ben",
                "slots": []
              },
              {
                "text": "i want to speak with a human",
                "slots": []
              },
              {
                "text": "talk with human",
                "slots": []
              },
              {
                "text": "talk to human",
                "slots": []
              },
              {
                "text": "i want to talk to a human",
                "slots": []
              }
            ],
            "slots": []
          },
          {
            "key": "capture_film_index_albdchcg",
            "name": "capture_film_index_albdchcg",
            "inputs": [],
            "slots": [
              {
                "id": "bj5639nw",
                "required": true,
                "dialog": {
                  "prompt": [
                    {
                      "text": "Huh? What?",
                      "slots": [],
                      "voice": ""
                    }
                  ],
                  "confirm": [],
                  "utterances": [
                    {
                      "text": "film {{[film_index].bj5639nw}}",
                      "slots": [
                        "bj5639nw"
                      ]
                    },
                    {
                      "text": "{{[film_index].bj5639nw}}",
                      "slots": [
                        "bj5639nw"
                      ]
                    },
                    {
                      "text": "{{[film_index].bj5639nw}}",
                      "slots": [
                        "bj5639nw"
                      ]
                    }
                  ],
                  "confirmEnabled": false
                }
              }
            ]
          },
          {
            "key": "capture_cinema_index_pjdjbkal",
            "name": "capture_cinema_index_pjdjbkal",
            "inputs": [],
            "slots": [
              {
                "id": "jltq394u",
                "required": true,
                "dialog": {
                  "prompt": [],
                  "confirm": [],
                  "utterances": [
                    {
                      "text": "cinema {{[cinema_index].jltq394u}}",
                      "slots": [
                        "jltq394u"
                      ]
                    },
                    {
                      "text": "{{[cinema_index].jltq394u}}",
                      "slots": [
                        "jltq394u"
                      ]
                    },
                    {
                      "text": "{{[cinema_index].jltq394u}}",
                      "slots": [
                        "jltq394u"
                      ]
                    }
                  ],
                  "confirmEnabled": false
                }
              }
            ]
          },
          {
            "key": "capture_showing_index_ciinefkm",
            "name": "capture_showing_index_ciinefkm",
            "inputs": [],
            "slots": [
              {
                "id": "4j1r395k",
                "required": true,
                "dialog": {
                  "prompt": [
                    {
                      "text": "Huh? What?",
                      "slots": [],
                      "voice": ""
                    }
                  ],
                  "confirm": [],
                  "utterances": [
                    {
                      "text": "showing {{[showing_index].4j1r395k}}",
                      "slots": [
                        "4j1r395k"
                      ]
                    },
                    {
                      "text": "{{[showing_index].4j1r395k}}",
                      "slots": [
                        "4j1r395k"
                      ]
                    },
                    {
                      "text": "{{[showing_index].4j1r395k}}",
                      "slots": [
                        "4j1r395k"
                      ]
                    }
                  ],
                  "confirmEnabled": false
                }
              }
            ]
          }
        ],
        "slots": [
          {
            "key": "yw5136ms",
            "name": "movie_name",
            "type": {
              "value": "VF.NAME"
            },
            "color": "#5b9fd7",
            "inputs": []
          },
          {
            "key": "6r5936x6",
            "name": "time",
            "type": {
              "value": "VF.DATETIME"
            },
            "color": "#e37c93",
            "inputs": []
          },
          {
            "key": "bj5639nw",
            "name": "film_index",
            "type": {
              "value": "VF.NUMBER"
            },
            "inputs": []
          },
          {
            "key": "jltq394u",
            "name": "cinema_index",
            "type": {
              "value": "VF.NUMBER"
            },
            "color": "#5b9fd7",
            "inputs": []
          },
          {
            "key": "n03q392i",
            "name": "showing_time",
            "type": {
              "value": "VF.DATETIME"
            },
            "color": "#56b365",
            "inputs": []
          },
          {
            "key": "4j1r395k",
            "name": "showing_index",
            "type": {
              "value": "VF.NUMBER"
            },
            "color": "#56b365",
            "inputs": []
          }
        ]
      }
    },
    "createdAt": "2022-04-29T15:37:23.000Z"
  },
  "version": {
    "_id": "626c0632ce89e0d909cb11e6",
    "variables": [
      "sessions",
      "user_id",
      "timestamp",
      "platform",
      "locale",
      "film_reco_count",
      "MovieGlu_authorization",
      "MovieGlu_client",
      "MovieGlu_x_api_key",
      "MovieGlu_api_version",
      "MovieGlu_geolocation",
      "MovieGlu_device_datetime",
      "MovieGlu_territory",
      "film_results",
      "joke",
      "film_speak",
      "cinema_results",
      "cinema_speak",
      "purchase_link",
      "film_index",
      "film_choice",
      "film_id",
      "purchase_date",
      "purchase_time",
      "cinema_choice",
      "showings_results",
      "showings_speak",
      "cinema_id"
    ],
    "platformData": {
      "slots": [
        {
          "key": "yw5136ms",
          "name": "movie_name",
          "type": {
            "value": "VF.NAME"
          },
          "color": "#5b9fd7",
          "inputs": []
        },
        {
          "key": "6r5936x6",
          "name": "time",
          "type": {
            "value": "VF.DATETIME"
          },
          "color": "#e37c93",
          "inputs": []
        },
        {
          "key": "bj5639nw",
          "name": "film_index",
          "type": {
            "value": "VF.NUMBER"
          },
          "inputs": []
        },
        {
          "key": "jltq394u",
          "name": "cinema_index",
          "type": {
            "value": "VF.NUMBER"
          },
          "color": "#5b9fd7",
          "inputs": []
        },
        {
          "key": "n03q392i",
          "name": "showing_time",
          "type": {
            "value": "VF.DATETIME"
          },
          "color": "#56b365",
          "inputs": []
        },
        {
          "key": "4j1r395k",
          "name": "showing_index",
          "type": {
            "value": "VF.NUMBER"
          },
          "color": "#56b365",
          "inputs": []
        }
      ],
      "intents": [
        {
          "key": "ahd3bsp",
          "name": "discover_movies",
          "inputs": [
            {
              "text": "what movies are playing now",
              "slots": []
            },
            {
              "text": "what are some movies showing",
              "slots": []
            },
            {
              "text": "what movies are available now",
              "slots": []
            }
          ],
          "slots": []
        },
        {
          "key": "b02n362m",
          "name": "discover_cinemas",
          "inputs": [
            {
              "text": "what theatres are near me",
              "slots": []
            }
          ],
          "slots": []
        },
        {
          "key": "9o4c36ee",
          "name": "checkout",
          "inputs": [
            {
              "text": "I want to watch {{[movie_name].yw5136ms}} at {{[time].6r5936x6}}",
              "slots": [
                "yw5136ms",
                "6r5936x6"
              ]
            },
            {
              "text": "check out",
              "slots": []
            },
            {
              "text": "checkout",
              "slots": []
            }
          ],
          "slots": [
            {
              "id": "yw5136ms",
              "dialog": {
                "prompt": [],
                "confirm": [],
                "utterances": [],
                "confirmEnabled": false
              },
              "required": false
            },
            {
              "id": "6r5936x6",
              "dialog": {
                "prompt": [
                  {
                    "text": "What time would you like to watch this movie?",
                    "slots": [],
                    "voice": ""
                  }
                ],
                "confirm": [],
                "utterances": [],
                "confirmEnabled": false
              },
              "required": false
            }
          ]
        },
        {
          "key": "VF.YES",
          "name": "VF.YES",
          "inputs": [],
          "slots": []
        },
        {
          "key": "VF.NO",
          "name": "VF.NO",
          "inputs": [],
          "slots": []
        },
        {
          "key": "pq1k3h4n",
          "name": "Angry Conceirge",
          "inputs": [
            {
              "text": "this is not great",
              "slots": []
            },
            {
              "text": "I'm having a terrible time",
              "slots": []
            },
            {
              "text": "your service sucks",
              "slots": []
            },
            {
              "text": "i hate you",
              "slots": []
            },
            {
              "text": "bastard",
              "slots": []
            },
            {
              "text": "bitch",
              "slots": []
            },
            {
              "text": "what did you say to me?",
              "slots": []
            },
            {
              "text": "asshole",
              "slots": []
            },
            {
              "text": "go fuck yourself",
              "slots": []
            },
            {
              "text": "fuck you",
              "slots": []
            },
            {
              "text": "you're trash",
              "slots": []
            },
            {
              "text": "you suck",
              "slots": []
            }
          ],
          "slots": []
        },
        {
          "key": "re3l3hi5",
          "name": "talk to human",
          "inputs": [
            {
              "text": "i hate robots",
              "slots": []
            },
            {
              "text": "i want a human",
              "slots": []
            },
            {
              "text": "i want ben",
              "slots": []
            },
            {
              "text": "i want to speak with a human",
              "slots": []
            },
            {
              "text": "talk with human",
              "slots": []
            },
            {
              "text": "talk to human",
              "slots": []
            },
            {
              "text": "i want to talk to a human",
              "slots": []
            }
          ],
          "slots": []
        }
      ],
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
    "projectID": "626c0633970711001c44065f",
    "rootDiagramID": "626c0633ce89e0d909cb11e7",
    "creatorID": 12656,
    "components": [
      {
        "sourceID": "626c0b49970711001c440666",
        "type": "DIAGRAM"
      },
      {
        "sourceID": "626c214739d2bc001e07c834",
        "type": "DIAGRAM"
      }
    ],
    "topics": [
      {
        "sourceID": "626c0633ce89e0d909cb11e7",
        "type": "DIAGRAM"
      }
    ],
    "prototype": {
      "data": {
        "name": "Movie Concierge",
        "locales": [
          "en-US"
        ]
      },
      "model": {
        "intents": [
          {
            "key": "ahd3bsp",
            "name": "discover_movies",
            "inputs": [
              {
                "text": "what movies are playing now",
                "slots": []
              },
              {
                "text": "what are some movies showing",
                "slots": []
              },
              {
                "text": "what movies are available now",
                "slots": []
              }
            ],
            "slots": []
          },
          {
            "key": "b02n362m",
            "name": "discover_cinemas",
            "inputs": [
              {
                "text": "what theatres are near me",
                "slots": []
              }
            ],
            "slots": []
          },
          {
            "key": "9o4c36ee",
            "name": "checkout",
            "inputs": [
              {
                "text": "I want to watch {{[movie_name].yw5136ms}} at {{[time].6r5936x6}}",
                "slots": [
                  "yw5136ms",
                  "6r5936x6"
                ]
              },
              {
                "text": "check out",
                "slots": []
              },
              {
                "text": "checkout",
                "slots": []
              }
            ],
            "slots": [
              {
                "id": "yw5136ms",
                "required": false,
                "dialog": {
                  "prompt": [],
                  "confirm": [],
                  "utterances": [],
                  "confirmEnabled": false
                }
              },
              {
                "id": "6r5936x6",
                "required": false,
                "dialog": {
                  "prompt": [
                    {
                      "text": "What time would you like to watch this movie?",
                      "slots": [],
                      "voice": ""
                    }
                  ],
                  "confirm": [],
                  "utterances": [],
                  "confirmEnabled": false
                }
              }
            ]
          },
          {
            "key": "VF.YES",
            "name": "VF.YES",
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
              }
            ],
            "slots": []
          },
          {
            "key": "VF.NO",
            "name": "VF.NO",
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
              }
            ],
            "slots": []
          },
          {
            "key": "pq1k3h4n",
            "name": "Angry Conceirge",
            "inputs": [
              {
                "text": "this is not great",
                "slots": []
              },
              {
                "text": "I'm having a terrible time",
                "slots": []
              },
              {
                "text": "your service sucks",
                "slots": []
              },
              {
                "text": "i hate you",
                "slots": []
              },
              {
                "text": "bastard",
                "slots": []
              },
              {
                "text": "bitch",
                "slots": []
              },
              {
                "text": "what did you say to me?",
                "slots": []
              },
              {
                "text": "asshole",
                "slots": []
              },
              {
                "text": "go fuck yourself",
                "slots": []
              },
              {
                "text": "fuck you",
                "slots": []
              },
              {
                "text": "you're trash",
                "slots": []
              },
              {
                "text": "you suck",
                "slots": []
              }
            ],
            "slots": []
          },
          {
            "key": "re3l3hi5",
            "name": "talk to human",
            "inputs": [
              {
                "text": "i hate robots",
                "slots": []
              },
              {
                "text": "i want a human",
                "slots": []
              },
              {
                "text": "i want ben",
                "slots": []
              },
              {
                "text": "i want to speak with a human",
                "slots": []
              },
              {
                "text": "talk with human",
                "slots": []
              },
              {
                "text": "talk to human",
                "slots": []
              },
              {
                "text": "i want to talk to a human",
                "slots": []
              }
            ],
            "slots": []
          },
          {
            "key": "capture_film_index_albdchcg",
            "name": "capture_film_index_albdchcg",
            "inputs": [],
            "slots": [
              {
                "id": "bj5639nw",
                "required": true,
                "dialog": {
                  "prompt": [
                    {
                      "text": "Huh? What?",
                      "slots": [],
                      "voice": ""
                    }
                  ],
                  "confirm": [],
                  "utterances": [
                    {
                      "text": "film {{[film_index].bj5639nw}}",
                      "slots": [
                        "bj5639nw"
                      ]
                    },
                    {
                      "text": "{{[film_index].bj5639nw}}",
                      "slots": [
                        "bj5639nw"
                      ]
                    },
                    {
                      "text": "{{[film_index].bj5639nw}}",
                      "slots": [
                        "bj5639nw"
                      ]
                    }
                  ],
                  "confirmEnabled": false
                }
              }
            ]
          },
          {
            "key": "capture_cinema_index_pjdjbkal",
            "name": "capture_cinema_index_pjdjbkal",
            "inputs": [],
            "slots": [
              {
                "id": "jltq394u",
                "required": true,
                "dialog": {
                  "prompt": [],
                  "confirm": [],
                  "utterances": [
                    {
                      "text": "cinema {{[cinema_index].jltq394u}}",
                      "slots": [
                        "jltq394u"
                      ]
                    },
                    {
                      "text": "{{[cinema_index].jltq394u}}",
                      "slots": [
                        "jltq394u"
                      ]
                    },
                    {
                      "text": "{{[cinema_index].jltq394u}}",
                      "slots": [
                        "jltq394u"
                      ]
                    }
                  ],
                  "confirmEnabled": false
                }
              }
            ]
          },
          {
            "key": "capture_showing_index_ciinefkm",
            "name": "capture_showing_index_ciinefkm",
            "inputs": [],
            "slots": [
              {
                "id": "4j1r395k",
                "required": true,
                "dialog": {
                  "prompt": [
                    {
                      "text": "Huh? What?",
                      "slots": [],
                      "voice": ""
                    }
                  ],
                  "confirm": [],
                  "utterances": [
                    {
                      "text": "showing {{[showing_index].4j1r395k}}",
                      "slots": [
                        "4j1r395k"
                      ]
                    },
                    {
                      "text": "{{[showing_index].4j1r395k}}",
                      "slots": [
                        "4j1r395k"
                      ]
                    },
                    {
                      "text": "{{[showing_index].4j1r395k}}",
                      "slots": [
                        "4j1r395k"
                      ]
                    }
                  ],
                  "confirmEnabled": false
                }
              }
            ]
          }
        ],
        "slots": [
          {
            "key": "yw5136ms",
            "name": "movie_name",
            "type": {
              "value": "VF.NAME"
            },
            "color": "#5b9fd7",
            "inputs": []
          },
          {
            "key": "6r5936x6",
            "name": "time",
            "type": {
              "value": "VF.DATETIME"
            },
            "color": "#e37c93",
            "inputs": []
          },
          {
            "key": "bj5639nw",
            "name": "film_index",
            "type": {
              "value": "VF.NUMBER"
            },
            "inputs": []
          },
          {
            "key": "jltq394u",
            "name": "cinema_index",
            "type": {
              "value": "VF.NUMBER"
            },
            "color": "#5b9fd7",
            "inputs": []
          },
          {
            "key": "n03q392i",
            "name": "showing_time",
            "type": {
              "value": "VF.DATETIME"
            },
            "color": "#56b365",
            "inputs": []
          },
          {
            "key": "4j1r395k",
            "name": "showing_index",
            "type": {
              "value": "VF.NUMBER"
            },
            "color": "#56b365",
            "inputs": []
          }
        ]
      },
      "context": {
        "stack": [
          {
            "programID": "626c0633ce89e0d909cb11e7",
            "storage": {},
            "variables": {}
          }
        ],
        "variables": {}
      },
      "settings": {},
      "platform": "general"
    }
  },
  "diagrams": {
    "626c0633ce89e0d909cb11e7": {
      "_id": "626c0633ce89e0d909cb11e7",
      "offsetX": 886.0423000731815,
      "offsetY": 726.68536200079,
      "zoom": 80,
      "variables": [],
      "name": "ROOT",
      "versionID": "626c0632ce89e0d909cb11e6",
      "creatorID": 12656,
      "modified": 1651262318,
      "nodes": {
        "start00000000000000000000": {
          "nodeID": "start00000000000000000000",
          "type": "start",
          "coords": [
            -407.5528750914767,
            -658.3567025009875
          ],
          "data": {
            "name": "Start",
            "color": "standard",
            "steps": [],
            "ports": [
              {
                "type": "next",
                "target": "626c1f02c0566dbf6a3beef7",
                "id": "60b7e7cad4b17f0ce7bddf11",
                "data": {
                  "points": [
                    {
                      "point": [
                        -242.55290258074706,
                        -577.6067197936127
                      ]
                    },
                    {
                      "point": [
                        -136.34511983538573,
                        -577.6067197936127
                      ]
                    },
                    {
                      "point": [
                        -136.34511983538573,
                        -438.907411398227
                      ],
                      "toTop": true,
                      "allowedToTop": true
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c064ee263897ea03e32a7": {
          "nodeID": "626c064ee263897ea03e32a7",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "Welcome to Movie Concierge, how may I assist you?"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c0c03557cd20b7e4af1be",
                "id": "626c064ee263897ea03e32a9"
              }
            ]
          }
        },
        "626c08aebdad36ba098937ff": {
          "nodeID": "626c08aebdad36ba098937ff",
          "type": "intent",
          "data": {
            "intent": "ahd3bsp",
            "mappings": [],
            "availability": "GLOBAL",
            "ports": [
              {
                "type": "next",
                "target": "626c0b968b24611bea445af9",
                "id": "626c08aebdad36ba09893800",
                "data": {
                  "points": [
                    {
                      "point": [
                        1682.8616648893158,
                        -506.1589026848844
                      ]
                    },
                    {
                      "point": [
                        1971.3830424527923,
                        -505.90949777765786
                      ]
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c08aebdad36ba09893801": {
          "nodeID": "626c08aebdad36ba09893801",
          "type": "block",
          "coords": [
            1517.861669423971,
            -586.9088577047103
          ],
          "data": {
            "name": "New Block 4",
            "color": "standard",
            "steps": [
              "626c08aebdad36ba098937ff"
            ]
          }
        },
        "626c08babdad36ba09893807": {
          "nodeID": "626c08babdad36ba09893807",
          "type": "intent",
          "data": {
            "intent": "b02n362m",
            "mappings": [],
            "availability": "GLOBAL",
            "ports": [
              {
                "type": "next",
                "target": "626c1811032511b71bbea904",
                "id": "626c08babdad36ba09893808",
                "data": {
                  "points": [
                    {
                      "point": [
                        1703.2260118175745,
                        33.499997874997696
                      ]
                    },
                    {
                      "point": [
                        1958.8087894141631,
                        33.54204732605944
                      ]
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c08babdad36ba09893809": {
          "nodeID": "626c08babdad36ba09893809",
          "type": "block",
          "coords": [
            1538.2260419062502,
            -47.2500052006095
          ],
          "data": {
            "name": "New Block 5",
            "color": "standard",
            "steps": [
              "626c08babdad36ba09893807"
            ]
          }
        },
        "626c091bbdad36ba09893827": {
          "nodeID": "626c091bbdad36ba09893827",
          "type": "intent",
          "data": {
            "intent": "9o4c36ee",
            "mappings": [],
            "availability": "GLOBAL",
            "ports": [
              {
                "type": "next",
                "target": "626c3294aba355fdfa8957e6",
                "id": "626c091bbdad36ba09893828"
              }
            ]
          }
        },
        "626c091bbdad36ba09893829": {
          "nodeID": "626c091bbdad36ba09893829",
          "type": "block",
          "coords": [
            1537.648776563835,
            334.10139671642
          ],
          "data": {
            "name": "New Block 8",
            "color": "standard",
            "steps": [
              "626c091bbdad36ba09893827"
            ]
          }
        },
        "626c0b968b24611bea445af5": {
          "nodeID": "626c0b968b24611bea445af5",
          "type": "api",
          "data": {
            "url": "https://api-gate2.movieglu.com/filmsNowShowing",
            "body": [
              {
                "key": "",
                "val": ""
              }
            ],
            "params": [
              {
                "key": "n",
                "val": "{{[film_reco_count].film_reco_count}}"
              }
            ],
            "method": "GET",
            "headers": [
              {
                "key": "client",
                "val": "{{[MovieGlu_client].MovieGlu_client}}"
              },
              {
                "key": "x-api-key",
                "val": "{{[MovieGlu_x_api_key].MovieGlu_x_api_key}}"
              },
              {
                "key": "authorization",
                "val": "{{[MovieGlu_authorization].MovieGlu_authorization}}"
              },
              {
                "key": "territory",
                "val": "{{[MovieGlu_territory].MovieGlu_territory}}"
              },
              {
                "key": "api-version",
                "val": "{{[MovieGlu_api_version].MovieGlu_api_version}}"
              },
              {
                "key": "geolocation",
                "val": "{{[MovieGlu_geolocation].MovieGlu_geolocation}}"
              },
              {
                "key": "device-datetime",
                "val": "{{[MovieGlu_device_datetime].MovieGlu_device_datetime}}"
              }
            ],
            "content": "",
            "mappings": [
              {
                "path": "response.films",
                "var": "film_results"
              }
            ],
            "bodyType": "formData",
            "selectedAction": "Make a GET Request",
            "selectedIntegration": "Custom API",
            "ports": [
              {
                "type": "next",
                "target": "626c0f5b27a23d1858c809a7",
                "id": "626c0b968b24611bea445af7"
              },
              {
                "type": "fail",
                "target": "626c0f5b27a23d1858c809a7",
                "id": "626c0b968b24611bea445af8"
              }
            ]
          }
        },
        "626c0b968b24611bea445af9": {
          "nodeID": "626c0b968b24611bea445af9",
          "type": "block",
          "coords": [
            2136.3830271940033,
            -532.9094596306852
          ],
          "data": {
            "name": "Find Films Nearby",
            "color": "red",
            "steps": [
              "626c0b968b24611bea445af5",
              "626c0f5b27a23d1858c809a7",
              "626c0deb27a23d1858c80983",
              "626c1d82e68c5c0f99161d7e",
              "626c1f57aa295b6ad8b749bb"
            ]
          }
        },
        "626c0bf7db52d10bfddb5adf": {
          "nodeID": "626c0bf7db52d10bfddb5adf",
          "type": "block",
          "coords": [
            749.049090124561,
            -431.1599022352673
          ],
          "data": {
            "name": "Block",
            "color": "standard",
            "steps": [
              "626c064ee263897ea03e32a7",
              "626c0c03557cd20b7e4af1be"
            ]
          }
        },
        "626c0c03557cd20b7e4af1be": {
          "nodeID": "626c0c03557cd20b7e4af1be",
          "type": "prompt",
          "data": {
            "ports": [
              {
                "type": "else",
                "target": "626c225dc0566dbf6a3bef86",
                "id": "626c0c03557cd20b7e4af1c0",
                "data": {
                  "points": [
                    {
                      "point": [
                        583.049055592169,
                        -148.40987350749302
                      ],
                      "reversed": true
                    },
                    {
                      "point": [
                        492.655124126297,
                        -148.40987350749302
                      ]
                    },
                    {
                      "point": [
                        492.655124126297,
                        -654.3608757955424
                      ]
                    },
                    {
                      "point": [
                        402.26119266042497,
                        -654.3608757955424
                      ],
                      "reversed": true
                    }
                  ]
                }
              }
            ],
            "noReply": {
              "types": [
                "reprompt"
              ],
              "timeout": 10,
              "pathName": "No Reply",
              "randomize": false,
              "reprompts": [
                {
                  "voice": "",
                  "content": "Not sure if you said anything there. How can I assist you?"
                },
                {
                  "voice": "Alexa",
                  "content": "Sorry I'm not sure if I heard anything, you might have to speak louder."
                }
              ]
            },
            "noMatch": {
              "types": [
                "reprompt",
                "path"
              ],
              "pathName": "No Match",
              "randomize": false,
              "reprompts": [
                {
                  "voice": "Alexa",
                  "content": "hey not sure if I can help with that sorry."
                },
                {
                  "voice": "Alexa",
                  "content": "I'm unable to assist you."
                }
              ]
            },
            "chips": null,
            "buttons": null
          }
        },
        "626c0c2fc2e19160d0e4fec2": {
          "nodeID": "626c0c2fc2e19160d0e4fec2",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "Cool, we've set up the booking, we are sending you the link to your phone where you can confirm and pay."
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": null,
                "id": "626c0c2fc2e19160d0e4fec4"
              }
            ]
          }
        },
        "626c0c2fc2e19160d0e4fec5": {
          "nodeID": "626c0c2fc2e19160d0e4fec5",
          "type": "block",
          "coords": [
            2544.4472527966477,
            467.17770637129183
          ],
          "data": {
            "name": "New Block 12",
            "color": "standard",
            "steps": [
              "626c0c2fc2e19160d0e4fec2"
            ]
          }
        },
        "626c0deb27a23d1858c80983": {
          "nodeID": "626c0deb27a23d1858c80983",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "{{[film_speak].film_speak}} "
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c1d82e68c5c0f99161d7e",
                "id": "626c0deb27a23d1858c80985"
              }
            ]
          }
        },
        "626c0f5b27a23d1858c809a7": {
          "nodeID": "626c0f5b27a23d1858c809a7",
          "type": "code",
          "data": {
            "code": "film_names = film_results.map((film, index) => `Film ${index + 1} ${film.film_name}`).join(', ');\nfilm_speak = `I found the following films. ${film_names}`\n",
            "ports": [
              {
                "type": "next",
                "target": "626c0deb27a23d1858c80983",
                "id": "626c0f5b27a23d1858c809a9"
              },
              {
                "type": "fail",
                "target": "626c0deb27a23d1858c80983",
                "id": "626c0f5b27a23d1858c809aa"
              }
            ]
          }
        },
        "626c1511b0e9012043799c0b": {
          "nodeID": "626c1511b0e9012043799c0b",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "testing test test man"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c152e14fc7cd7a678e2a6",
                "id": "626c1511b0e9012043799c0d"
              }
            ]
          }
        },
        "626c1511b0e9012043799c0e": {
          "nodeID": "626c1511b0e9012043799c0e",
          "type": "block",
          "coords": [
            37.89121312420115,
            174.03961977538935
          ],
          "data": {
            "name": "New Block 23",
            "color": "standard",
            "steps": [
              "626c167f0a648cbf30e6cc57",
              "626c1511b0e9012043799c0b",
              "626c152e14fc7cd7a678e2a6"
            ]
          }
        },
        "626c152e14fc7cd7a678e2a6": {
          "nodeID": "626c152e14fc7cd7a678e2a6",
          "type": "interaction",
          "data": {
            "name": "Choice",
            "choices": [
              {
                "intent": "VF.YES",
                "action": "PATH",
                "mappings": []
              },
              {
                "intent": "VF.NO",
                "action": "PATH",
                "mappings": []
              }
            ],
            "intentScope": "GLOBAL",
            "noMatch": {
              "types": [
                "reprompt"
              ],
              "pathName": "No Match",
              "randomize": false,
              "reprompts": [
                {
                  "voice": "Alexa",
                  "content": "I have no idea lol"
                }
              ]
            },
            "noReply": null,
            "chips": null,
            "buttons": null,
            "ports": [
              {
                "type": "else",
                "target": null,
                "id": "626c152e14fc7cd7a678e2a9"
              },
              {
                "type": "",
                "target": "626c153814fc7cd7a678e2b4",
                "id": "626c152e14fc7cd7a678e2a8",
                "data": {
                  "points": [
                    {
                      "point": [
                        202.8912673215053,
                        379.78962757706194
                      ]
                    },
                    {
                      "point": [
                        254.86433882618064,
                        379.78962757706194
                      ]
                    },
                    {
                      "point": [
                        254.86433882618064,
                        227.15917650993472
                      ]
                    },
                    {
                      "point": [
                        306.83741033085596,
                        227.15917650993472
                      ],
                      "allowedToTop": true
                    }
                  ]
                }
              },
              {
                "type": "",
                "target": "626c1bfd4e0b1108b70ddde3",
                "id": "626c153214fc7cd7a678e2af",
                "data": {
                  "points": [
                    {
                      "point": [
                        202.8912673215053,
                        434.28962391448454
                      ]
                    },
                    {
                      "point": [
                        254.21868851635293,
                        434.28962391448454
                      ]
                    },
                    {
                      "point": [
                        254.21868851635293,
                        495.94074496471006
                      ]
                    },
                    {
                      "point": [
                        305.54610971120053,
                        495.94074496471006
                      ]
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c153814fc7cd7a678e2b1": {
          "nodeID": "626c153814fc7cd7a678e2b1",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "you said yes, now bugger off"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": null,
                "id": "626c153814fc7cd7a678e2b3"
              }
            ]
          }
        },
        "626c153814fc7cd7a678e2b4": {
          "nodeID": "626c153814fc7cd7a678e2b4",
          "type": "block",
          "coords": [
            471.83733078658975,
            200.15917013835252
          ],
          "data": {
            "name": "New Block 24",
            "color": "standard",
            "steps": [
              "626c153814fc7cd7a678e2b1"
            ]
          }
        },
        "626c167f0a648cbf30e6cc57": {
          "nodeID": "626c167f0a648cbf30e6cc57",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "yo yo yo"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c1511b0e9012043799c0b",
                "id": "626c167f0a648cbf30e6cc59"
              }
            ]
          }
        },
        "626c1811032511b71bbea900": {
          "nodeID": "626c1811032511b71bbea900",
          "type": "api",
          "data": {
            "url": "https://api-gate2.movieglu.com/cinemasNearby",
            "body": [
              {
                "key": "",
                "val": ""
              }
            ],
            "params": [
              {
                "key": "n",
                "val": "{{[film_reco_count].film_reco_count}}"
              }
            ],
            "method": "GET",
            "headers": [
              {
                "key": "client",
                "val": "{{[MovieGlu_client].MovieGlu_client}}"
              },
              {
                "key": "x-api-key",
                "val": "{{[MovieGlu_x_api_key].MovieGlu_x_api_key}}"
              },
              {
                "key": "authorization",
                "val": "{{[MovieGlu_authorization].MovieGlu_authorization}}"
              },
              {
                "key": "territory",
                "val": "{{[MovieGlu_territory].MovieGlu_territory}}"
              },
              {
                "key": "api-version",
                "val": "{{[MovieGlu_api_version].MovieGlu_api_version}}"
              },
              {
                "key": "geolocation",
                "val": "{{[MovieGlu_geolocation].MovieGlu_geolocation}}"
              },
              {
                "key": "device-datetime",
                "val": "{{[MovieGlu_device_datetime].MovieGlu_device_datetime}}"
              }
            ],
            "content": "",
            "mappings": [
              {
                "path": "response.cinemas",
                "var": "cinema_results"
              }
            ],
            "bodyType": "formData",
            "selectedAction": "Make a GET Request",
            "selectedIntegration": "Custom API",
            "ports": [
              {
                "type": "next",
                "target": "626c1869032511b71bbea91c",
                "id": "626c1811032511b71bbea902"
              },
              {
                "type": "fail",
                "target": "626c1869032511b71bbea91c",
                "id": "626c1811032511b71bbea901"
              }
            ]
          }
        },
        "626c1811032511b71bbea904": {
          "nodeID": "626c1811032511b71bbea904",
          "type": "block",
          "coords": [
            2123.8088056526235,
            6.54201790612598
          ],
          "data": {
            "name": "Find Cinemas Nearby",
            "color": "red",
            "steps": [
              "626c1811032511b71bbea900",
              "626c1869032511b71bbea91c",
              "626c1821032511b71bbea90c"
            ]
          }
        },
        "626c1821032511b71bbea90c": {
          "nodeID": "626c1821032511b71bbea90c",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "{{[cinema_speak].cinema_speak}} "
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": null,
                "id": "626c1821032511b71bbea90e"
              }
            ]
          }
        },
        "626c1869032511b71bbea91c": {
          "nodeID": "626c1869032511b71bbea91c",
          "type": "code",
          "data": {
            "code": "cinema_names = cinema_results.map(cinema => cinema.cinema_name).join(', ');\ncinema_speak = `We found the following cinemas. ${cinema_names}`",
            "ports": [
              {
                "type": "next",
                "target": "626c1821032511b71bbea90c",
                "id": "626c1869032511b71bbea91e"
              },
              {
                "type": "fail",
                "target": "626c1821032511b71bbea90c",
                "id": "626c1869032511b71bbea91d"
              }
            ]
          }
        },
        "626c192e032511b71bbea939": {
          "nodeID": "626c192e032511b71bbea939",
          "type": "api",
          "data": {
            "url": "https://api-gate2.movieglu.com/purchaseConfirmation",
            "body": [
              {
                "key": "",
                "val": ""
              }
            ],
            "params": [
              {
                "key": "cinema_id",
                "val": "{{[film_reco_count].film_reco_count}}"
              },
              {
                "key": "film_id",
                "val": []
              },
              {
                "key": "date",
                "val": []
              },
              {
                "key": "time",
                "val": []
              }
            ],
            "method": "GET",
            "headers": [
              {
                "key": "client",
                "val": "{{[MovieGlu_client].MovieGlu_client}}"
              },
              {
                "key": "x-api-key",
                "val": "{{[MovieGlu_x_api_key].MovieGlu_x_api_key}}"
              },
              {
                "key": "authorization",
                "val": "{{[MovieGlu_authorization].MovieGlu_authorization}}"
              },
              {
                "key": "territory",
                "val": "{{[MovieGlu_territory].MovieGlu_territory}}"
              },
              {
                "key": "api-version",
                "val": "{{[MovieGlu_api_version].MovieGlu_api_version}}"
              },
              {
                "key": "geolocation",
                "val": "{{[MovieGlu_geolocation].MovieGlu_geolocation}}"
              },
              {
                "key": "device-datetime",
                "val": "{{[MovieGlu_device_datetime].MovieGlu_device_datetime}}"
              }
            ],
            "content": "",
            "mappings": [
              {
                "path": "response.url",
                "var": "purchase_link"
              }
            ],
            "bodyType": "formData",
            "selectedAction": "Make a GET Request",
            "selectedIntegration": "Custom API",
            "ports": [
              {
                "type": "next",
                "target": "626c19c5032511b71bbea946",
                "id": "626c192e032511b71bbea93b"
              },
              {
                "type": "fail",
                "target": "626c19c5032511b71bbea946",
                "id": "626c192e032511b71bbea93a"
              }
            ]
          }
        },
        "626c192e032511b71bbea93d": {
          "nodeID": "626c192e032511b71bbea93d",
          "type": "block",
          "coords": [
            2139.820515815594,
            386.0053893189147
          ],
          "data": {
            "name": "Send Purchase Link",
            "color": "red",
            "steps": [
              "626c192e032511b71bbea939",
              "626c19c5032511b71bbea946"
            ]
          }
        },
        "626c19c5032511b71bbea946": {
          "nodeID": "626c19c5032511b71bbea946",
          "type": "api",
          "data": {
            "url": "",
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
                "path": "",
                "var": null
              }
            ],
            "bodyType": "formData",
            "selectedAction": "Make a GET Request",
            "selectedIntegration": "Custom API",
            "ports": [
              {
                "type": "next",
                "target": null,
                "id": "626c19c5032511b71bbea948"
              },
              {
                "type": "fail",
                "target": null,
                "id": "626c19c5032511b71bbea949"
              }
            ]
          }
        },
        "626c1a50032511b71bbea966": {
          "nodeID": "626c1a50032511b71bbea966",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "Great, you selected {{[film_choice].film_choice}} "
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c23d9aa295b6ad8b74b08",
                "id": "626c1a50032511b71bbea968"
              }
            ]
          }
        },
        "626c1a50032511b71bbea969": {
          "nodeID": "626c1a50032511b71bbea969",
          "type": "block",
          "coords": [
            2609.5929973362777,
            -678.5596930071536
          ],
          "data": {
            "name": "Find Cinemas Playing Film",
            "color": "red",
            "steps": [
              "626c1c44032511b71bbea9ac",
              "626c1a50032511b71bbea966",
              "626c23d9aa295b6ad8b74b08",
              "626c242eaa295b6ad8b74b1a",
              "626c2492aa295b6ad8b74b2c",
              "626c2496aa295b6ad8b74b3b",
              "626c2618aa295b6ad8b74b53"
            ]
          }
        },
        "626c1b9e032511b71bbea99c": {
          "nodeID": "626c1b9e032511b71bbea99c",
          "type": "setV2",
          "data": {
            "sets": [
              {
                "type": "value",
                "variable": "MovieGlu_authorization",
                "expression": "Basic Vk9JQ19YWDpKaWlidXRWcHZmTDk="
              },
              {
                "type": "value",
                "variable": "MovieGlu_client",
                "expression": "VOIC"
              },
              {
                "type": "value",
                "variable": "MovieGlu_x_api_key",
                "expression": "n5mV66Bhxn3nLlyGiKAcY44wIyYDE5Mr5v7At7GG"
              },
              {
                "type": "value",
                "variable": "MovieGlu_territory",
                "expression": "XX"
              },
              {
                "type": "value",
                "variable": "MovieGlu_api_version",
                "expression": "v200"
              },
              {
                "type": "value",
                "variable": "MovieGlu_geolocation",
                "expression": "-22.0;14.0"
              },
              {
                "type": "value",
                "variable": "MovieGlu_device_datetime",
                "expression": "2022-04-29T15:44:05.787Z"
              },
              {
                "type": "value",
                "variable": "film_reco_count",
                "expression": "3"
              }
            ],
            "title": "Set Staging Variables",
            "ports": [
              {
                "type": "next",
                "target": null,
                "id": "626c1b9e032511b71bbea99d"
              }
            ]
          }
        },
        "626c1bfd4e0b1108b70ddde3": {
          "nodeID": "626c1bfd4e0b1108b70ddde3",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": ""
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": null,
                "id": "626c1bfd4e0b1108b70ddde5"
              }
            ]
          }
        },
        "626c1bfd4e0b1108b70ddde6": {
          "nodeID": "626c1bfd4e0b1108b70ddde6",
          "type": "block",
          "coords": [
            471.54603438288206,
            416.44070173716705
          ],
          "data": {
            "name": "New Block 18",
            "color": "standard",
            "steps": [
              "626c1bfd4e0b1108b70ddde3"
            ]
          }
        },
        "626c1c44032511b71bbea9ac": {
          "nodeID": "626c1c44032511b71bbea9ac",
          "type": "code",
          "data": {
            "code": "const film = film_results[film_index - 1];\n \nfilm_choice = film.film_name\nfilm_id = film.film_id\npurchase_date = new Date().toISOString().split('T')[0];",
            "ports": [
              {
                "type": "next",
                "target": "626c1a50032511b71bbea966",
                "id": "626c1c44032511b71bbea9ae"
              },
              {
                "type": "fail",
                "target": "626c1a50032511b71bbea966",
                "id": "626c1c44032511b71bbea9af"
              }
            ]
          }
        },
        "626c1d82e68c5c0f99161d7e": {
          "nodeID": "626c1d82e68c5c0f99161d7e",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "Which film do you want to see? Please select a number"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c1f57aa295b6ad8b749bb",
                "id": "626c1d82e68c5c0f99161d80"
              }
            ]
          }
        },
        "626c1e22aa295b6ad8b74996": {
          "nodeID": "626c1e22aa295b6ad8b74996",
          "type": "trace",
          "data": {
            "_v": 1,
            "payload": {
              "name": "call",
              "body": "{ \"number\": \"519-501-2684\" }"
            },
            "defaultPath": 0,
            "ports": [
              {
                "type": "",
                "target": null,
                "id": "626c1e22aa295b6ad8b74998",
                "data": {
                  "event": {
                    "type": "success"
                  }
                }
              },
              {
                "type": "",
                "target": null,
                "id": "626c20dc42518b5e8e114601",
                "data": {
                  "event": {
                    "type": "fail"
                  }
                }
              }
            ]
          }
        },
        "626c1f02c0566dbf6a3beef3": {
          "nodeID": "626c1f02c0566dbf6a3beef3",
          "type": "ifV2",
          "data": {
            "expressions": [
              {
                "type": null,
                "name": "First session",
                "value": [
                  {
                    "logicInterface": "variable",
                    "type": "equals",
                    "value": [
                      {
                        "type": "variable",
                        "value": "sessions"
                      },
                      {
                        "type": "value",
                        "value": "1"
                      }
                    ]
                  }
                ]
              },
              {
                "type": null,
                "name": "Second session",
                "value": [
                  {
                    "logicInterface": "variable",
                    "type": "not_equal",
                    "value": [
                      {
                        "type": "variable",
                        "value": "sessions"
                      },
                      {
                        "type": "value",
                        "value": "1"
                      }
                    ]
                  }
                ]
              }
            ],
            "noMatch": {
              "type": "none",
              "pathName": "No Match"
            },
            "ports": [
              {
                "type": "else",
                "target": null,
                "id": "626c1f02c0566dbf6a3beef6"
              },
              {
                "type": "",
                "target": "626c322a6498f1d7a80eab63",
                "id": "626c1f02c0566dbf6a3beef5",
                "data": {
                  "points": [
                    {
                      "point": [
                        28.654964811033395,
                        -354.15741242578054
                      ]
                    },
                    {
                      "point": [
                        453.52772618273474,
                        -354.15741242578054
                      ]
                    },
                    {
                      "point": [
                        453.52772618273474,
                        -661.8015355325518
                      ]
                    },
                    {
                      "point": [
                        878.4004875544362,
                        -661.8015355325518
                      ],
                      "allowedToTop": true
                    }
                  ],
                  "event": {
                    "type": "First session"
                  }
                }
              },
              {
                "type": "",
                "target": "626c1f58c0566dbf6a3bef16",
                "id": "626c1f17c0566dbf6a3bef01",
                "data": {
                  "points": [
                    {
                      "point": [
                        28.654937744140796,
                        -299.6573905944824
                      ]
                    },
                    {
                      "point": [
                        117.40493011474626,
                        -299.6573905944824
                      ]
                    },
                    {
                      "point": [
                        117.40493011474626,
                        -95.15738677978513
                      ],
                      "toTop": true,
                      "allowedToTop": true
                    }
                  ],
                  "event": {
                    "type": "Second session"
                  }
                }
              }
            ]
          }
        },
        "626c1f02c0566dbf6a3beef7": {
          "nodeID": "626c1f02c0566dbf6a3beef7",
          "type": "block",
          "coords": [
            -136.3451080322264,
            -434.9073867797851
          ],
          "data": {
            "name": "New Block 19",
            "color": "standard",
            "steps": [
              "626c1f02c0566dbf6a3beef3"
            ]
          }
        },
        "626c1f57aa295b6ad8b749bb": {
          "nodeID": "626c1f57aa295b6ad8b749bb",
          "type": "captureV2",
          "data": {
            "intentScope": "GLOBAL",
            "capture": {
              "type": "intent",
              "intent": {
                "key": "",
                "name": "",
                "inputs": [],
                "slots": [
                  {
                    "id": "bj5639nw",
                    "dialog": {
                      "prompt": [
                        {
                          "text": "Huh? What?",
                          "slots": [],
                          "voice": ""
                        }
                      ],
                      "confirm": [],
                      "utterances": [
                        {
                          "text": "film {{[film_index].bj5639nw}} ",
                          "slots": [
                            "bj5639nw"
                          ]
                        },
                        {
                          "text": "{{[film_index].bj5639nw}} ",
                          "slots": [
                            "bj5639nw"
                          ]
                        }
                      ],
                      "confirmEnabled": false
                    },
                    "required": true
                  }
                ]
              }
            },
            "noReply": null,
            "noMatch": {
              "types": [
                "reprompt",
                "path"
              ],
              "pathName": "No Match",
              "randomize": false,
              "reprompts": [
                {
                  "voice": "Alexa",
                  "content": "Sorry, I didn't catch that. Please select a number from the following list of films. {{[film_speak].film_speak}} "
                }
              ]
            },
            "chips": null,
            "ports": [
              {
                "type": "next",
                "target": "626c1a50032511b71bbea969",
                "id": "626c1f57aa295b6ad8b749bd",
                "data": {
                  "points": [
                    {
                      "point": [
                        2301.3831050633285,
                        -177.6595083758059
                      ]
                    },
                    {
                      "point": [
                        2372.9880969761703,
                        -177.6595083758059
                      ]
                    },
                    {
                      "point": [
                        2372.9880969761703,
                        -651.5596930071536
                      ]
                    },
                    {
                      "point": [
                        2444.593088889012,
                        -651.5596930071536
                      ],
                      "allowedToTop": true
                    }
                  ]
                }
              },
              {
                "type": "else",
                "target": "626c1fa9aa295b6ad8b749d7",
                "id": "626c1f57aa295b6ad8b749be",
                "data": {
                  "points": [
                    {
                      "point": [
                        2301.383066916356,
                        -123.15950074641137
                      ]
                    },
                    {
                      "point": [
                        2337.633097433934,
                        -123.15950074641137
                      ]
                    },
                    {
                      "point": [
                        2337.633097433934,
                        163.59052977116676
                      ]
                    },
                    {
                      "point": [
                        2373.883127951512,
                        163.59052977116676
                      ]
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c1f58c0566dbf6a3bef13": {
          "nodeID": "626c1f58c0566dbf6a3bef13",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "It's nice to hear from you again!"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c322a6498f1d7a80eab63",
                "id": "626c1f58c0566dbf6a3bef15",
                "data": {
                  "points": [
                    {
                      "point": [
                        282.4049588217484,
                        0.84256826406736
                      ]
                    },
                    {
                      "point": [
                        580.4027231880923,
                        0.84256826406736
                      ]
                    },
                    {
                      "point": [
                        580.4027231880923,
                        -661.801488319702
                      ]
                    },
                    {
                      "point": [
                        878.4004875544362,
                        -661.801488319702
                      ],
                      "allowedToTop": true
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c1f58c0566dbf6a3bef16": {
          "nodeID": "626c1f58c0566dbf6a3bef16",
          "type": "block",
          "coords": [
            117.40489196777361,
            -91.15738677978513
          ],
          "data": {
            "name": "New Block 22",
            "color": "standard",
            "steps": [
              "626c1f58c0566dbf6a3bef13"
            ]
          }
        },
        "626c1fa5c0566dbf6a3bef25": {
          "nodeID": "626c1fa5c0566dbf6a3bef25",
          "type": "intent",
          "data": {
            "intent": "pq1k3h4n",
            "mappings": [],
            "availability": "GLOBAL",
            "ports": [
              {
                "type": "next",
                "target": "626c1fbfc0566dbf6a3bef3a",
                "id": "626c1fa5c0566dbf6a3bef26"
              }
            ]
          }
        },
        "626c1fa5c0566dbf6a3bef27": {
          "nodeID": "626c1fa5c0566dbf6a3bef27",
          "type": "block",
          "coords": [
            233.6694533780061,
            -1017.9857733855688
          ],
          "data": {
            "name": "New Block 21",
            "color": "red",
            "steps": [
              "626c1fa5c0566dbf6a3bef25",
              "626c1fbfc0566dbf6a3bef3a"
            ]
          }
        },
        "626c1fa9aa295b6ad8b749d7": {
          "nodeID": "626c1fa9aa295b6ad8b749d7",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "Sorry, I didn't catch that, would you like me to list the films again?"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c1fbcaa295b6ad8b749e1",
                "id": "626c1fa9aa295b6ad8b749d9"
              }
            ]
          }
        },
        "626c1fa9aa295b6ad8b749da": {
          "nodeID": "626c1fa9aa295b6ad8b749da",
          "type": "block",
          "coords": [
            2539.8830271940033,
            84.0905403693148
          ],
          "data": {
            "name": "New Block 22",
            "color": "standard",
            "steps": [
              "626c1fa9aa295b6ad8b749d7",
              "626c1fbcaa295b6ad8b749e1"
            ]
          }
        },
        "626c1fbcaa295b6ad8b749e1": {
          "nodeID": "626c1fbcaa295b6ad8b749e1",
          "type": "interaction",
          "data": {
            "name": "Choice",
            "choices": [
              {
                "intent": "VF.YES",
                "action": "PATH",
                "mappings": []
              },
              {
                "intent": "VF.NO",
                "action": "PATH",
                "mappings": []
              }
            ],
            "intentScope": "GLOBAL",
            "noMatch": {
              "types": [
                "reprompt"
              ],
              "pathName": "No Match",
              "randomize": false,
              "reprompts": [
                {
                  "voice": "Alexa",
                  "content": ""
                }
              ]
            },
            "noReply": null,
            "chips": null,
            "buttons": null,
            "ports": [
              {
                "type": "else",
                "target": null,
                "id": "626c1fbcaa295b6ad8b749e4"
              },
              {
                "type": "",
                "target": "626c0deb27a23d1858c80983",
                "id": "626c1fbcaa295b6ad8b749e3",
                "data": {
                  "points": [
                    {
                      "point": [
                        2373.883127951512,
                        272.34052977116676
                      ],
                      "reversed": true
                    },
                    {
                      "point": [
                        2338.133127951512,
                        272.34052977116676
                      ]
                    },
                    {
                      "point": [
                        2338.133127951512,
                        -326.40954652277856
                      ]
                    },
                    {
                      "point": [
                        2302.383127951512,
                        -326.40954652277856
                      ],
                      "reversed": true
                    }
                  ]
                }
              },
              {
                "type": "",
                "target": "626c262baa295b6ad8b74b66",
                "id": "626c1fc3aa295b6ad8b749f5",
                "data": {
                  "points": [
                    {
                      "point": [
                        2704.883168585978,
                        326.840541974898
                      ]
                    },
                    {
                      "point": [
                        3527.3188776580064,
                        326.840541974898
                      ]
                    },
                    {
                      "point": [
                        3527.3188776580064,
                        439.2204966557502
                      ]
                    },
                    {
                      "point": [
                        4349.754586730035,
                        439.2204966557502
                      ],
                      "allowedToTop": true
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c1fbfc0566dbf6a3bef3a": {
          "nodeID": "626c1fbfc0566dbf6a3bef3a",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "en-US-standard-E",
                "content": "you're not that guy pal, you're not that guy "
              },
              {
                "voice": "Alexa",
                "content": "I'm gunna put some dirt in your eye   "
              },
              {
                "voice": "Alexa",
                "content": "I forgot the part where thats my problem "
              },
              {
                "voice": "Alexa",
                "content": "You want forgiveness? Get religion"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c1e22aa295b6ad8b74996",
                "id": "626c1fbfc0566dbf6a3bef3c",
                "data": {
                  "points": [
                    {
                      "point": [
                        398.66941494758566,
                        -863.4857518021349
                      ]
                    },
                    {
                      "point": [
                        526.1971706848904,
                        -863.1066662613634
                      ]
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c1fbfc0566dbf6a3bef3d": {
          "nodeID": "626c1fbfc0566dbf6a3bef3d",
          "type": "block",
          "coords": [
            692.1971249085232,
            -942.6067025009875
          ],
          "data": {
            "name": "New Block 23",
            "color": "standard",
            "steps": [
              "626c1e22aa295b6ad8b74996"
            ]
          }
        },
        "626c1fddc0566dbf6a3bef4c": {
          "nodeID": "626c1fddc0566dbf6a3bef4c",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "I'll ask one more time, how can I help you?"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c0c03557cd20b7e4af1be",
                "id": "626c1fddc0566dbf6a3bef4e",
                "data": {
                  "points": [
                    {
                      "point": [
                        591.6025229119356,
                        73.63735528159836
                      ],
                      "reversed": true
                    },
                    {
                      "point": [
                        559.049055592169,
                        73.63735528159836
                      ]
                    },
                    {
                      "point": [
                        559.049055592169,
                        -204.15989574005198
                      ]
                    },
                    {
                      "point": [
                        583.049055592169,
                        -204.15989574005198
                      ]
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c212142518b5e8e114609": {
          "nodeID": "626c212142518b5e8e114609",
          "type": "block",
          "coords": [
            757.6025093413347,
            -18.362695169511007
          ],
          "data": {
            "name": "Block",
            "color": "standard",
            "steps": [
              "626c1fddc0566dbf6a3bef4c"
            ]
          }
        },
        "626c2216aa295b6ad8b74aed": {
          "nodeID": "626c2216aa295b6ad8b74aed",
          "type": "api",
          "data": {
            "url": "https://api-gate2.movieglu.com/purchaseConfirmation",
            "body": [
              {
                "key": "",
                "val": ""
              }
            ],
            "params": [
              {
                "key": "cinema_id",
                "val": "{{[cinema_id].cinema_id}}"
              },
              {
                "key": "film_id",
                "val": "{{[film_id].film_id}}"
              },
              {
                "key": "date",
                "val": "{{[purchase_date].purchase_date}}"
              },
              {
                "key": "time",
                "val": "{{[purchase_time].purchase_time}}"
              }
            ],
            "method": "GET",
            "headers": [
              {
                "key": "client",
                "val": "{{[MovieGlu_client].MovieGlu_client}}"
              },
              {
                "key": "x-api-key",
                "val": "{{[MovieGlu_x_api_key].MovieGlu_x_api_key}}"
              },
              {
                "key": "authorization",
                "val": "{{[MovieGlu_authorization].MovieGlu_authorization}}"
              },
              {
                "key": "territory",
                "val": "{{[MovieGlu_territory].MovieGlu_territory}}"
              },
              {
                "key": "api-version",
                "val": "{{[MovieGlu_api_version].MovieGlu_api_version}}"
              },
              {
                "key": "geolocation",
                "val": "{{[MovieGlu_geolocation].MovieGlu_geolocation}}"
              },
              {
                "key": "device-datetime",
                "val": "{{[MovieGlu_device_datetime].MovieGlu_device_datetime}}"
              }
            ],
            "content": "",
            "mappings": [
              {
                "path": "response.url",
                "var": "purchase_link"
              }
            ],
            "bodyType": "formData",
            "selectedAction": "Make a GET Request",
            "selectedIntegration": "Custom API",
            "ports": [
              {
                "type": "next",
                "target": "626c31093b5dda004e903864",
                "id": "626c2216aa295b6ad8b74aef"
              },
              {
                "type": "fail",
                "target": "626c31093b5dda004e903864",
                "id": "626c2216aa295b6ad8b74aee"
              }
            ]
          }
        },
        "626c2216aa295b6ad8b74af1": {
          "nodeID": "626c2216aa295b6ad8b74af1",
          "type": "block",
          "coords": [
            4088.298059689111,
            -899.1712104443347
          ],
          "data": {
            "name": "Generate Purchase Link",
            "color": "red",
            "steps": [
              "626c2216aa295b6ad8b74aed",
              "626c31093b5dda004e903864",
              "626c318267f19b4d82ca45c9",
              "626c341f6498f1d7a80eac9e"
            ]
          }
        },
        "626c2239c0566dbf6a3bef7d": {
          "nodeID": "626c2239c0566dbf6a3bef7d",
          "type": "intent",
          "data": {
            "intent": "re3l3hi5",
            "mappings": [],
            "availability": "GLOBAL",
            "ports": [
              {
                "type": "next",
                "target": "626c225dc0566dbf6a3bef86",
                "id": "626c2239c0566dbf6a3bef7e"
              }
            ]
          }
        },
        "626c2239c0566dbf6a3bef7f": {
          "nodeID": "626c2239c0566dbf6a3bef7f",
          "type": "block",
          "coords": [
            236.26120041489727,
            -796.3609636443207
          ],
          "data": {
            "name": "New Block 25",
            "color": "standard",
            "steps": [
              "626c2239c0566dbf6a3bef7d",
              "626c225dc0566dbf6a3bef86"
            ]
          }
        },
        "626c225dc0566dbf6a3bef86": {
          "nodeID": "626c225dc0566dbf6a3bef86",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "No problem, connecting you with our happiness agent, one moment"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c1e22aa295b6ad8b74996",
                "id": "626c225dc0566dbf6a3bef88",
                "data": {
                  "points": [
                    {
                      "point": [
                        401.2611965637966,
                        -630.6109291855578
                      ]
                    },
                    {
                      "point": [
                        463.7291836243435,
                        -630.6109291855578
                      ]
                    },
                    {
                      "point": [
                        463.7291836243435,
                        -863.1066567246203
                      ]
                    },
                    {
                      "point": [
                        526.1971706848904,
                        -863.1066567246203
                      ]
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c23d9aa295b6ad8b74b08": {
          "nodeID": "626c23d9aa295b6ad8b74b08",
          "type": "api",
          "data": {
            "url": "https://api-gate2.movieglu.com/filmShowTimes",
            "body": [
              {
                "key": "",
                "val": ""
              }
            ],
            "params": [
              {
                "key": "n",
                "val": "{{[film_reco_count].film_reco_count}}"
              },
              {
                "key": "film_id",
                "val": "{{[film_id].film_id}}"
              },
              {
                "key": "date",
                "val": "{{[purchase_date].purchase_date}}"
              }
            ],
            "method": "GET",
            "headers": [
              {
                "key": "client",
                "val": "{{[MovieGlu_client].MovieGlu_client}}"
              },
              {
                "key": "x-api-key",
                "val": "{{[MovieGlu_x_api_key].MovieGlu_x_api_key}}"
              },
              {
                "key": "authorization",
                "val": "{{[MovieGlu_authorization].MovieGlu_authorization}}"
              },
              {
                "key": "territory",
                "val": "{{[MovieGlu_territory].MovieGlu_territory}}"
              },
              {
                "key": "api-version",
                "val": "{{[MovieGlu_api_version].MovieGlu_api_version}}"
              },
              {
                "key": "geolocation",
                "val": "{{[MovieGlu_geolocation].MovieGlu_geolocation}}"
              },
              {
                "key": "device-datetime",
                "val": "{{[MovieGlu_device_datetime].MovieGlu_device_datetime}}"
              }
            ],
            "content": "",
            "mappings": [
              {
                "path": "response.cinemas",
                "var": "cinema_results"
              }
            ],
            "bodyType": "formData",
            "selectedAction": "Make a GET Request",
            "selectedIntegration": "Custom API",
            "ports": [
              {
                "type": "next",
                "target": "626c242eaa295b6ad8b74b1a",
                "id": "626c23d9aa295b6ad8b74b0a"
              },
              {
                "type": "fail",
                "target": "626c242eaa295b6ad8b74b1a",
                "id": "626c23d9aa295b6ad8b74b09"
              }
            ]
          }
        },
        "626c242eaa295b6ad8b74b1a": {
          "nodeID": "626c242eaa295b6ad8b74b1a",
          "type": "code",
          "data": {
            "code": "cinema_names = cinema_results.map((cinema, index) => `Cinema ${index + 1} ${cinema.cinema_name}`).join(', ');\ncinema_speak = `I found the following cinemas that are playing ${film_choice} today. ${cinema_names}`\n",
            "ports": [
              {
                "type": "next",
                "target": "626c2492aa295b6ad8b74b2c",
                "id": "626c242eaa295b6ad8b74b1c"
              },
              {
                "type": "fail",
                "target": "626c2492aa295b6ad8b74b2c",
                "id": "626c242eaa295b6ad8b74b1b"
              }
            ]
          }
        },
        "626c2492aa295b6ad8b74b2c": {
          "nodeID": "626c2492aa295b6ad8b74b2c",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "{{[cinema_speak].cinema_speak}} "
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c2496aa295b6ad8b74b3b",
                "id": "626c2492aa295b6ad8b74b2d"
              }
            ]
          }
        },
        "626c2496aa295b6ad8b74b3b": {
          "nodeID": "626c2496aa295b6ad8b74b3b",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "Which cinema do you want go to? Please select a number"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c2618aa295b6ad8b74b53",
                "id": "626c2496aa295b6ad8b74b3c"
              }
            ]
          }
        },
        "626c2618aa295b6ad8b74b53": {
          "nodeID": "626c2618aa295b6ad8b74b53",
          "type": "captureV2",
          "data": {
            "intentScope": "GLOBAL",
            "capture": {
              "type": "intent",
              "intent": {
                "key": "",
                "name": "",
                "inputs": [],
                "slots": [
                  {
                    "id": "jltq394u",
                    "dialog": {
                      "prompt": [],
                      "confirm": [],
                      "utterances": [
                        {
                          "text": "cinema {{[cinema_index].jltq394u}} ",
                          "slots": [
                            "jltq394u"
                          ]
                        },
                        {
                          "text": "{{[cinema_index].jltq394u}} ",
                          "slots": [
                            "jltq394u"
                          ]
                        }
                      ],
                      "confirmEnabled": false
                    },
                    "required": true
                  }
                ]
              }
            },
            "noReply": null,
            "noMatch": {
              "types": [
                "reprompt",
                "path"
              ],
              "pathName": "No Match",
              "randomize": false,
              "reprompts": [
                {
                  "voice": "Alexa",
                  "content": "Sorry, I didn't catch that. Please select a number from the following list of cinemas. {{[cinema_speak].cinema_speak}} "
                }
              ]
            },
            "chips": null,
            "ports": [
              {
                "type": "next",
                "target": "626c26cfd843ec9a3f80993e",
                "id": "626c2618aa295b6ad8b74b55",
                "data": {
                  "points": [
                    {
                      "point": [
                        2774.592981564111,
                        -197.3096610668935
                      ]
                    },
                    {
                      "point": [
                        2832.1341192594236,
                        -197.3096610668935
                      ]
                    },
                    {
                      "point": [
                        2832.1341192594236,
                        -674.1380836132802
                      ]
                    },
                    {
                      "point": [
                        2889.675256954736,
                        -674.1380836132802
                      ],
                      "allowedToTop": true
                    }
                  ]
                }
              },
              {
                "type": "else",
                "target": "626c262baa295b6ad8b74b64",
                "id": "626c2618aa295b6ad8b74b56",
                "data": {
                  "points": [
                    {
                      "point": [
                        2774.59307214709,
                        -142.80973458409932
                      ]
                    },
                    {
                      "point": [
                        2881.343056888301,
                        -140.30973458409932
                      ]
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c262baa295b6ad8b74b70": {
          "nodeID": "626c262baa295b6ad8b74b70",
          "type": "component",
          "data": {
            "diagramID": "626c214739d2bc001e07c834",
            "variableMap": null,
            "ports": [
              {
                "type": "next",
                "target": null,
                "id": "626c262baa295b6ad8b74b71"
              }
            ]
          }
        },
        "626c262baa295b6ad8b74b6b": {
          "nodeID": "626c262baa295b6ad8b74b6b",
          "type": "interaction",
          "data": {
            "name": "Choice",
            "choices": [
              {
                "intent": "VF.YES",
                "action": "PATH",
                "mappings": []
              },
              {
                "intent": "VF.NO",
                "action": "PATH",
                "mappings": []
              }
            ],
            "intentScope": "GLOBAL",
            "noMatch": {
              "types": [
                "reprompt"
              ],
              "pathName": "No Match",
              "randomize": false,
              "reprompts": [
                {
                  "voice": "Alexa",
                  "content": ""
                }
              ]
            },
            "noReply": null,
            "chips": null,
            "buttons": null,
            "ports": [
              {
                "type": "else",
                "target": null,
                "id": "626c262baa295b6ad8b74b6c"
              },
              {
                "type": "",
                "target": "626c2492aa295b6ad8b74b2c",
                "id": "626c262baa295b6ad8b74b6d"
              },
              {
                "type": "",
                "target": "626c262baa295b6ad8b74b66",
                "id": "626c262baa295b6ad8b74b6e",
                "data": {
                  "points": [
                    {
                      "point": [
                        3211.3431382477233,
                        75.440304340353
                      ]
                    },
                    {
                      "point": [
                        3780.5488624888794,
                        75.440304340353
                      ]
                    },
                    {
                      "point": [
                        3780.5488624888794,
                        439.2205041923663
                      ]
                    },
                    {
                      "point": [
                        4349.754586730035,
                        439.2205041923663
                      ],
                      "allowedToTop": true
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c262baa295b6ad8b74b68": {
          "nodeID": "626c262baa295b6ad8b74b68",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "Sorry, I didn't catch that, would you like me to list the cinemas again?"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c262baa295b6ad8b74b6b",
                "id": "626c262baa295b6ad8b74b69"
              }
            ]
          }
        },
        "626c262baa295b6ad8b74b66": {
          "nodeID": "626c262baa295b6ad8b74b66",
          "type": "block",
          "coords": [
            4514.754548178649,
            412.2204803888001
          ],
          "data": {
            "name": "New Block 22",
            "color": "green",
            "steps": [
              "626c262baa295b6ad8b74b70"
            ]
          }
        },
        "626c262baa295b6ad8b74b64": {
          "nodeID": "626c262baa295b6ad8b74b64",
          "type": "block",
          "coords": [
            3046.3429973362777,
            -167.30969682185082
          ],
          "data": {
            "name": "New Block 22",
            "color": "standard",
            "steps": [
              "626c262baa295b6ad8b74b68",
              "626c262baa295b6ad8b74b6b"
            ]
          }
        },
        "626c26cfd843ec9a3f80993b": {
          "nodeID": "626c26cfd843ec9a3f80993b",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "Great, you selected {{[cinema_choice].cinema_choice}} "
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c28cbbb7ae3048272848c",
                "id": "626c26cfd843ec9a3f80993d"
              }
            ]
          }
        },
        "626c26cfd843ec9a3f80993e": {
          "nodeID": "626c26cfd843ec9a3f80993e",
          "type": "block",
          "coords": [
            3054.6753600570687,
            -701.1381012025828
          ],
          "data": {
            "name": "Send Purchase Link",
            "color": "red",
            "steps": [
              "626c26e9d843ec9a3f809949",
              "626c26cfd843ec9a3f80993b",
              "626c28cbbb7ae3048272848c",
              "626c29acbb7ae304827284a8",
              "626c2978bb7ae30482728499"
            ]
          }
        },
        "626c26e9d843ec9a3f809949": {
          "nodeID": "626c26e9d843ec9a3f809949",
          "type": "code",
          "data": {
            "code": "const cinema = cinema_results[cinema_index - 1];\n \ncinema_choice = cinema.cinema_name\ncinema_id = cinema.cinema_id\n\nshowings_results = cinema.showings.Standard.times\n\nconst times = showings_results.map((showing, index) => `Showing ${index + 1} ${showing.start_time}`).join(', ')\nshowings_speak = `I found showings for ${film_choice} at ${times}`",
            "ports": [
              {
                "type": "next",
                "target": "626c26cfd843ec9a3f80993b",
                "id": "626c26e9d843ec9a3f80994b"
              },
              {
                "type": "fail",
                "target": "626c26cfd843ec9a3f80993b",
                "id": "626c26e9d843ec9a3f80994a"
              }
            ]
          }
        },
        "626c28cbbb7ae3048272848c": {
          "nodeID": "626c28cbbb7ae3048272848c",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "{{[showings_speak].showings_speak}} "
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c29acbb7ae304827284a8",
                "id": "626c28cbbb7ae3048272848e"
              }
            ]
          }
        },
        "626c2978bb7ae30482728499": {
          "nodeID": "626c2978bb7ae30482728499",
          "type": "captureV2",
          "data": {
            "intentScope": "GLOBAL",
            "capture": {
              "type": "intent",
              "intent": {
                "key": "",
                "name": "",
                "inputs": [],
                "slots": [
                  {
                    "id": "4j1r395k",
                    "dialog": {
                      "prompt": [
                        {
                          "text": "Huh? What?",
                          "slots": [],
                          "voice": ""
                        }
                      ],
                      "confirm": [],
                      "utterances": [
                        {
                          "text": "showing {{[showing_index].4j1r395k}} ",
                          "slots": [
                            "4j1r395k"
                          ]
                        },
                        {
                          "text": "{{[showing_index].4j1r395k}} ",
                          "slots": [
                            "4j1r395k"
                          ]
                        }
                      ],
                      "confirmEnabled": false
                    },
                    "required": true
                  }
                ]
              }
            },
            "noReply": null,
            "noMatch": {
              "types": [
                "reprompt",
                "path"
              ],
              "pathName": "No Match",
              "randomize": false,
              "reprompts": [
                {
                  "voice": "Alexa",
                  "content": "Sorry, I didn't catch that. Please from the following list of show times. \n{{[showings_speak].showings_speak}} "
                }
              ]
            },
            "chips": null,
            "ports": [
              {
                "type": "next",
                "target": "626c2acb5b52ea4b569c50fe",
                "id": "626c2978bb7ae3048272849b",
                "data": {
                  "points": [
                    {
                      "point": [
                        3219.6752671177433,
                        -313.1381330610779
                      ]
                    },
                    {
                      "point": [
                        3324.816849264099,
                        -313.1381330610779
                      ]
                    },
                    {
                      "point": [
                        3324.816849264099,
                        -847.2481330953794
                      ]
                    },
                    {
                      "point": [
                        3429.958431410454,
                        -847.2481330953794
                      ],
                      "allowedToTop": true
                    }
                  ]
                }
              },
              {
                "type": "else",
                "target": "626c29edbb7ae304827284bd",
                "id": "626c2978bb7ae3048272849c",
                "data": {
                  "points": [
                    {
                      "point": [
                        3219.6752671177433,
                        -247.38819638506467
                      ]
                    },
                    {
                      "point": [
                        3354.7836476892267,
                        -247.38819638506467
                      ]
                    },
                    {
                      "point": [
                        3354.7836476892267,
                        -336.1865965318465
                      ]
                    },
                    {
                      "point": [
                        3489.89202826071,
                        -336.1865965318465
                      ],
                      "allowedToTop": true
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c29acbb7ae304827284a8": {
          "nodeID": "626c29acbb7ae304827284a8",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "Which showing do you want to go to? Please select a number"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c2978bb7ae30482728499",
                "id": "626c29acbb7ae304827284a9"
              }
            ]
          }
        },
        "626c29edbb7ae304827284c5": {
          "nodeID": "626c29edbb7ae304827284c5",
          "type": "interaction",
          "data": {
            "name": "Choice",
            "choices": [
              {
                "intent": "VF.YES",
                "action": "PATH",
                "mappings": []
              },
              {
                "intent": "VF.NO",
                "action": "PATH",
                "mappings": []
              }
            ],
            "intentScope": "GLOBAL",
            "noMatch": {
              "types": [
                "reprompt"
              ],
              "pathName": "No Match",
              "randomize": false,
              "reprompts": [
                {
                  "voice": "Alexa",
                  "content": ""
                }
              ]
            },
            "noReply": null,
            "chips": null,
            "buttons": null,
            "ports": [
              {
                "type": "else",
                "target": null,
                "id": "626c29edbb7ae304827284c6"
              },
              {
                "type": "",
                "target": "626c28cbbb7ae3048272848c",
                "id": "626c29edbb7ae304827284c7",
                "data": {
                  "points": [
                    {
                      "point": [
                        3488.8825926051354,
                        -174.93058594846957
                      ],
                      "reversed": true
                    },
                    {
                      "point": [
                        3354.778376983187,
                        -174.93058594846957
                      ]
                    },
                    {
                      "point": [
                        3354.778376983187,
                        -473.1388989367508
                      ]
                    },
                    {
                      "point": [
                        3220.674161361239,
                        -473.1388989367508
                      ],
                      "reversed": true
                    }
                  ]
                }
              },
              {
                "type": "",
                "target": "626c262baa295b6ad8b74b66",
                "id": "626c29edbb7ae304827284c8",
                "data": {
                  "points": [
                    {
                      "point": [
                        3819.8922105375973,
                        -120.43658581822694
                      ]
                    },
                    {
                      "point": [
                        4084.8233986338164,
                        -120.43658581822694
                      ]
                    },
                    {
                      "point": [
                        4084.8233986338164,
                        439.22050796067435
                      ]
                    },
                    {
                      "point": [
                        4349.754586730035,
                        439.22050796067435
                      ],
                      "allowedToTop": true
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c29edbb7ae304827284c2": {
          "nodeID": "626c29edbb7ae304827284c2",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "Sorry, I didn't catch that, would you like me to list the show times again?"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c29edbb7ae304827284c5",
                "id": "626c29edbb7ae304827284c3"
              }
            ]
          }
        },
        "626c29edbb7ae304827284bd": {
          "nodeID": "626c29edbb7ae304827284bd",
          "type": "block",
          "coords": [
            3654.892132215598,
            -363.1865707555274
          ],
          "data": {
            "name": "New Block 22",
            "color": "standard",
            "steps": [
              "626c29edbb7ae304827284c2",
              "626c29edbb7ae304827284c5"
            ]
          }
        },
        "626c2acb5b52ea4b569c50fb": {
          "nodeID": "626c2acb5b52ea4b569c50fb",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "Great, you chose to see {{[film_choice].film_choice}} at {{[cinema_choice].cinema_choice}}  for {{[purchase_time].purchase_time}} is this correct?"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c30423b5dda004e903849",
                "id": "626c2acb5b52ea4b569c50fd"
              }
            ]
          }
        },
        "626c2acb5b52ea4b569c50fe": {
          "nodeID": "626c2acb5b52ea4b569c50fe",
          "type": "block",
          "coords": [
            3594.958459109981,
            -874.2480814468922
          ],
          "data": {
            "name": "New Block 26",
            "color": "standard",
            "steps": [
              "626c2d7167f19b4d82ca43b1",
              "626c2acb5b52ea4b569c50fb",
              "626c30423b5dda004e903849"
            ]
          }
        },
        "626c2d7167f19b4d82ca43b1": {
          "nodeID": "626c2d7167f19b4d82ca43b1",
          "type": "code",
          "data": {
            "code": "purchase_time = showings_results[showing_index - 1].start_time\n",
            "ports": [
              {
                "type": "next",
                "target": "626c2acb5b52ea4b569c50fb",
                "id": "626c2d7167f19b4d82ca43b3"
              },
              {
                "type": "fail",
                "target": "626c2acb5b52ea4b569c50fb",
                "id": "626c2d7167f19b4d82ca43b2"
              }
            ]
          }
        },
        "626c30423b5dda004e903849": {
          "nodeID": "626c30423b5dda004e903849",
          "type": "interaction",
          "data": {
            "name": "Choice",
            "choices": [
              {
                "intent": "VF.YES",
                "action": "PATH",
                "mappings": []
              },
              {
                "intent": "VF.NO",
                "action": "PATH",
                "mappings": []
              }
            ],
            "intentScope": "GLOBAL",
            "noMatch": {
              "types": [
                "reprompt"
              ],
              "pathName": "No Match",
              "randomize": false,
              "reprompts": [
                {
                  "voice": "Alexa",
                  "content": ""
                }
              ]
            },
            "noReply": null,
            "chips": null,
            "buttons": null,
            "ports": [
              {
                "type": "else",
                "target": null,
                "id": "626c30423b5dda004e90384c"
              },
              {
                "type": "",
                "target": "626c2216aa295b6ad8b74af1",
                "id": "626c30423b5dda004e90384b",
                "data": {
                  "points": [
                    {
                      "point": [
                        3759.9584401419893,
                        -599.9981076430354
                      ]
                    },
                    {
                      "point": [
                        3841.6282276601546,
                        -599.9981076430354
                      ]
                    },
                    {
                      "point": [
                        3841.6282276601546,
                        -872.1712132848373
                      ]
                    },
                    {
                      "point": [
                        3923.29801517832,
                        -872.1712132848373
                      ],
                      "allowedToTop": true
                    }
                  ]
                }
              },
              {
                "type": "",
                "target": "626c306b3b5dda004e903857",
                "id": "626c30513b5dda004e903852",
                "data": {
                  "points": [
                    {
                      "point": [
                        3759.95834265802,
                        -545.4981055792174
                      ]
                    },
                    {
                      "point": [
                        3798.0226708516843,
                        -545.4981055792174
                      ]
                    },
                    {
                      "point": [
                        3798.0226708516843,
                        -457.34800487120964
                      ]
                    },
                    {
                      "point": [
                        3836.086999045349,
                        -457.34800487120964
                      ],
                      "allowedToTop": true
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c306b3b5dda004e903854": {
          "nodeID": "626c306b3b5dda004e903854",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "Uh oh, that's not good, I'll list the showing times again"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c28cbbb7ae3048272848c",
                "id": "626c306b3b5dda004e903856",
                "data": {
                  "points": [
                    {
                      "point": [
                        3835.087118873479,
                        -392.3480410773148
                      ],
                      "reversed": true
                    },
                    {
                      "point": [
                        3527.8812156741656,
                        -392.3480410773148
                      ]
                    },
                    {
                      "point": [
                        3527.8812156741656,
                        -473.1381816166726
                      ]
                    },
                    {
                      "point": [
                        3220.675312474852,
                        -473.1381816166726
                      ],
                      "reversed": true
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c306b3b5dda004e903857": {
          "nodeID": "626c306b3b5dda004e903857",
          "type": "block",
          "coords": [
            4001.0870363756885,
            -484.34800677087514
          ],
          "data": {
            "name": "New Block 27",
            "color": "standard",
            "steps": [
              "626c306b3b5dda004e903854"
            ]
          }
        },
        "626c31093b5dda004e903864": {
          "nodeID": "626c31093b5dda004e903864",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "We are sending the purchase details to your phone."
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c318267f19b4d82ca45c9",
                "id": "626c31093b5dda004e903866"
              }
            ]
          }
        },
        "626c318267f19b4d82ca45c9": {
          "nodeID": "626c318267f19b4d82ca45c9",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "{{[purchase_link].purchase_link}} "
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c341f6498f1d7a80eac9e",
                "id": "626c318267f19b4d82ca45cb"
              }
            ]
          }
        },
        "626c322a6498f1d7a80eab60": {
          "nodeID": "626c322a6498f1d7a80eab60",
          "type": "setV2",
          "data": {
            "sets": [
              {
                "type": "value",
                "variable": "MovieGlu_authorization",
                "expression": "Basic Vk9JQzpZbUpkYUVqTTF1a3I="
              },
              {
                "type": "value",
                "variable": "MovieGlu_client",
                "expression": "VOIC"
              },
              {
                "type": "value",
                "variable": "MovieGlu_x_api_key",
                "expression": "smQsXaeAwi2KQKt0ijoqO7E1oLxfEcra9YkeNOgP"
              },
              {
                "type": "value",
                "variable": "MovieGlu_territory",
                "expression": "CA"
              },
              {
                "type": "value",
                "variable": "MovieGlu_api_version",
                "expression": "v200"
              },
              {
                "type": "value",
                "variable": "MovieGlu_geolocation",
                "expression": "43.654210;-79.386391"
              },
              {
                "type": "value",
                "variable": "film_reco_count",
                "expression": "3"
              }
            ],
            "title": "Set Production Variables",
            "ports": [
              {
                "type": "next",
                "target": "626c0bf7db52d10bfddb5adf",
                "id": "626c322a6498f1d7a80eab61",
                "data": {
                  "points": [
                    {
                      "point": [
                        877.4004831778682,
                        -544.5515153448014
                      ],
                      "reversed": true
                    },
                    {
                      "point": [
                        749.049082148179,
                        -544.5515153448014
                      ]
                    },
                    {
                      "point": [
                        749.049082148179,
                        -435.1599653119286
                      ],
                      "toTop": true,
                      "allowedToTop": true
                    }
                  ]
                }
              }
            ]
          }
        },
        "626c322a6498f1d7a80eab63": {
          "nodeID": "626c322a6498f1d7a80eab63",
          "type": "block",
          "coords": [
            1043.400336804769,
            -688.801448330376
          ],
          "data": {
            "name": "Block copy",
            "color": "green",
            "steps": [
              "626c32966498f1d7a80eab72",
              "626c322a6498f1d7a80eab60"
            ]
          }
        },
        "626c3294aba355fdfa8957e3": {
          "nodeID": "626c3294aba355fdfa8957e3",
          "type": "trace",
          "data": {
            "_v": 1,
            "payload": {
              "name": "sms",
              "body": "your link is {purchase_link}"
            },
            "defaultPath": 0,
            "ports": [
              {
                "type": "",
                "target": null,
                "id": "626c3294aba355fdfa8957e4",
                "data": {}
              }
            ]
          }
        },
        "626c3294aba355fdfa8957e6": {
          "nodeID": "626c3294aba355fdfa8957e6",
          "type": "block",
          "coords": [
            1560.4515313699046,
            531.9475817003135
          ],
          "data": {
            "name": "Generate Purchase Link copy",
            "color": "red",
            "steps": [
              "626c32b2aba355fdfa8957fa",
              "626c32a3aba355fdfa8957f3",
              "626c3294aba355fdfa8957e3"
            ]
          }
        },
        "626c32966498f1d7a80eab72": {
          "nodeID": "626c32966498f1d7a80eab72",
          "type": "code",
          "data": {
            "code": "MovieGlu_device_datetime = new Date().toISOString()",
            "ports": [
              {
                "type": "next",
                "target": "626c322a6498f1d7a80eab60",
                "id": "626c32966498f1d7a80eab74"
              },
              {
                "type": "fail",
                "target": "626c322a6498f1d7a80eab60",
                "id": "626c32966498f1d7a80eab75"
              }
            ]
          }
        },
        "626c32a3aba355fdfa8957f3": {
          "nodeID": "626c32a3aba355fdfa8957f3",
          "type": "setV2",
          "data": {
            "sets": [
              {
                "type": "value",
                "variable": "purchase_link",
                "expression": "https://google.com"
              }
            ],
            "title": "",
            "ports": [
              {
                "type": "next",
                "target": "626c3294aba355fdfa8957e3",
                "id": "626c32a3aba355fdfa8957f5"
              }
            ]
          }
        },
        "626c32b2aba355fdfa8957fa": {
          "nodeID": "626c32b2aba355fdfa8957fa",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "sending a text"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c32a3aba355fdfa8957f3",
                "id": "626c32b2aba355fdfa8957fc"
              }
            ]
          }
        },
        "626c32c56498f1d7a80eab8f": {
          "nodeID": "626c32c56498f1d7a80eab8f",
          "type": "block",
          "coords": [
            611.6081261709168,
            -622.8967759314982
          ],
          "data": {
            "name": "Block",
            "color": "purple",
            "steps": [
              "626c1b9e032511b71bbea99c"
            ]
          }
        },
        "626c341f6498f1d7a80eac9e": {
          "nodeID": "626c341f6498f1d7a80eac9e",
          "type": "trace",
          "data": {
            "_v": 1,
            "payload": {
              "name": "sms",
              "body": "your link is {purchase_link}"
            },
            "defaultPath": 0,
            "ports": [
              {
                "type": "",
                "target": "626c262baa295b6ad8b74b66",
                "id": "626c341f6498f1d7a80eac9f",
                "data": {}
              }
            ]
          }
        }
      },
      "children": [
        "626c214739d2bc001e07c834"
      ],
      "type": "TOPIC",
      "intentStepIDs": [
        "626c08aebdad36ba098937ff",
        "626c08babdad36ba09893807",
        "626c091bbdad36ba09893827",
        "626c1fa5c0566dbf6a3bef25",
        "626c2239c0566dbf6a3bef7d"
      ]
    },
    "626c0b49970711001c440666": {
      "_id": "626c0b49970711001c440666",
      "name": "error flow",
      "type": "COMPONENT",
      "zoom": 80,
      "offsetX": 272,
      "offsetY": 104,
      "modified": 1651248075,
      "nodes": {
        "626c0b4908bba80008f1d4bc": {
          "nodeID": "626c0b4908bba80008f1d4bc",
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
                "target": null,
                "id": "626c0b4901d26656897e638d"
              }
            ]
          }
        }
      },
      "children": [],
      "variables": [],
      "intentStepIDs": [],
      "creatorID": 12656,
      "versionID": "626c0632ce89e0d909cb11e6"
    },
    "626c214739d2bc001e07c834": {
      "_id": "626c214739d2bc001e07c834",
      "name": "happy_goodbye",
      "type": "COMPONENT",
      "zoom": 80,
      "offsetX": 272,
      "offsetY": 104,
      "modified": 1651258347,
      "nodes": {
        "626c21473783330007683beb": {
          "nodeID": "626c21473783330007683beb",
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
                "target": "626c2148aa295b6ad8b74a31",
                "id": "626c2147aa295b6ad8b74a2d"
              }
            ]
          }
        },
        "626c2148aa295b6ad8b74a36": {
          "nodeID": "626c2148aa295b6ad8b74a36",
          "type": "exit",
          "data": {
            "ports": []
          }
        },
        "626c2148aa295b6ad8b74a33": {
          "nodeID": "626c2148aa295b6ad8b74a33",
          "type": "speak",
          "data": {
            "randomize": true,
            "canvasVisibility": "preview",
            "dialogs": [
              {
                "voice": "Alexa",
                "content": "Thanks for choosing movie concierge, have a nice day"
              }
            ],
            "ports": [
              {
                "type": "next",
                "target": "626c2148aa295b6ad8b74a36",
                "id": "626c2148aa295b6ad8b74a34"
              }
            ]
          }
        },
        "626c2148aa295b6ad8b74a31": {
          "nodeID": "626c2148aa295b6ad8b74a31",
          "type": "block",
          "coords": [
            797,
            176
          ],
          "data": {
            "name": "New Block 24",
            "color": "standard",
            "steps": [
              "626c2148aa295b6ad8b74a33",
              "626c2148aa295b6ad8b74a36"
            ]
          }
        }
      },
      "children": [],
      "variables": [],
      "intentStepIDs": [],
      "creatorID": 10585,
      "versionID": "626c0632ce89e0d909cb11e6"
    }
  },
  "variableStates": []
}
```
