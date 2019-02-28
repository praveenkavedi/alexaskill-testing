alexa skill test result:
 
 # hello-world is the skill name
 # under lambda -> custom -> index.js (this is the lamda respone)
 # under test folder i have kept index.test.yml(test suit), testing.json file

 Please find the result after (bst test),
 svtusers-MacBook-Air:hello-world svtuser$ bst test

BST: v2.1.18  Node: v11.10.0
Have questions? Go to https://read.bespoken.io for full documentation on Bespoken tools.

 FAIL  test/index.test.yml
  en-US
    Launch request, no further interaction.
      ✕ LaunchRequest
    HelloWorldIntent direct call
      ✕ HelloWorldIntent
    AMAZON.HelpIntent. Ask for help and exit.
      ✓ LaunchRequest
      ✕ AMAZON.HelpIntent
      ✓ SessionEndedRequest
    AMAZON.HelpIntent. Ask for help and stop.
      ✓ LaunchRequest
      ✓ AMAZON.HelpIntent
      ✓ AMAZON.StopIntent
    AMAZON.HelpIntent. Ask for help and then for a fact.
      ✓ LaunchRequest
      ✓ AMAZON.HelpIntent
      ✕ HelloWorldIntent
    AMAZON.StopIntent
      ✓ LaunchRequest
      ✓ AMAZON.StopIntent
    AMAZON.CancelIntent
      ✓ LaunchRequest
      ✓ AMAZON.CancelIntent
    AMAZON.FallbackIntent
      ✓ LaunchRequest
      ✕ AMAZON.FallbackIntent

  ● en-US › Launch request, no further interaction. › LaunchRequest

    Expected value at [response.outputSpeech.ssml] to ==
    	HelloWorld
    Received:
    	<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>

       6 | - test: Launch request, no further interaction.
       7 | - LaunchRequest: # LaunchRequest is not an utterance but a request type and reserved word
    >  8 |   - response.outputSpeech.ssml: HelloWorld
       9 |   - response.card.type: Simple
      10 |   - response.card.title: hello-world
      11 |   - response.card.content: "*" # Any text will match
      
      at test/index.test.yml:8:0
      Timestamp:
      	2019-02-28T16:49:11.281

  ● en-US › HelloWorldIntent direct call › HelloWorldIntent

    Expected value at [response.outputSpeech.ssml] to ==
    	Here's your fact
    Received:
    	<speak>Hello World!</speak>

      14 | - test: HelloWorldIntent direct call
      15 | - HelloWorldIntent:
    > 16 |   - response.outputSpeech.ssml: Here's your fact  
      17 |   - response.card.type: Simple
      18 |   - response.card.title: hello-world
      19 |   - response.card.content: "*" # Quotes need to be used when the response starts with a star
      
      at test/index.test.yml:16:0
      Timestamp:
      	2019-02-28T16:49:11.285

  ● en-US › AMAZON.HelpIntent. Ask for help and exit. › AMAZON.HelpIntent

    Expected value at [response.outputSpeech.ssml] to ==
    	You can say Hello to the world.
    Received:
    	<speak>You can say hello to me!</speak>

      23 | - LaunchRequest # Empty expected part means we are not testing the response
      24 | - AMAZON.HelpIntent:
    > 25 |   - response.outputSpeech.ssml: You can say Hello to the world.
      26 |   - response.card: Hello World.
      27 |   - response.reprompt.outputSpeech.ssml: I will repeat it, You can say Hello to the world.
      28 | - SessionEndedRequest: # This is equivalent to say 'exit'
      
      at test/index.test.yml:25:0
      Timestamp:
      	2019-02-28T16:49:11.288

  ● en-US › AMAZON.HelpIntent. Ask for help and then for a fact. › HelloWorldIntent

    Error
      Expected value at [prompt] to ==
      	undefined
      Received:
      	<speak>Hello World!</speak>
      
      Timestamp:
      	2019-02-28T16:49:11.295

  ● en-US › AMAZON.FallbackIntent › AMAZON.FallbackIntent

    Unable to match utterance: AMAZON.FallbackIntent to an intent. Try a different utterance, or explicitly set the intent

      54 | - test: AMAZON.FallbackIntent
      55 | - LaunchRequest
    > 56 | - AMAZON.FallbackIntent:
      57 |   - prompt: Sorry, I can\'t understand the command. Please say again. # prompt is equivalent to response.outputSpeech.ssml
      58 |   - reprompt: What can I help you with? # reprompt is equivalent to response.reprompt.outputSpeech.ssml
      59 |   - response.shouldEndSession: false
      
      at test/index.test.yml:56:0
      Timestamp:
      	2019-02-28T16:49:11.300

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:323
    File: index.test.yml Test: Launch request, no further interaction. Utterance: LaunchRequest

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:326
    Request Envelope:
    {
      "context": {
        "System": {
          "application": {
            "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
          },
          "device": {
            "supportedInterfaces": {
              "AudioPlayer": {},
              "Display": {},
              "VideoApp": {}
            }
          },
          "user": {
            "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
          }
        },
        "Display": {},
        "AudioPlayer": {
          "playerActivity": "IDLE"
        }
      },
      "request": {
        "locale": "en-US",
        "requestId": "amzn1.echo-external.request.39430241-1e0d-45ec-83dd-6a4068023261",
        "timestamp": "2019-02-28T11:19:11Z",
        "type": "LaunchRequest"
      },
      "version": "1.0",
      "session": {
        "application": {
          "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
        },
        "new": true,
        "sessionId": "SessionID.3d31c4a5-35b0-4b7b-a260-b2acb57012e4",
        "user": {
          "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
        }
      }
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:288
    Response Envelope:
    {
      "version": "1.0",
      "response": {
        "outputSpeech": {
          "type": "SSML",
          "ssml": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>"
        },
        "reprompt": {
          "outputSpeech": {
            "type": "SSML",
            "ssml": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>"
          }
        },
        "shouldEndSession": false,
        "card": {
          "type": "Simple",
          "title": "Hello World",
          "content": "Welcome to the Alexa Skills Kit, you can say hello!"
        }
      },
      "userAgent": "ask-node/2.4.0 Node/v11.10.0",
      "sessionAttributes": {},
      "cardContent": "Welcome to the Alexa Skills Kit, you can say hello!",
      "cardTitle": "Hello World",
      "prompt": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>",
      "reprompt": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>",
      "sessionEnded": false
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:323
    File: index.test.yml Test: HelloWorldIntent direct call Utterance: HelloWorldIntent

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:326
    Request Envelope:
    {
      "context": {
        "System": {
          "application": {
            "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
          },
          "device": {
            "supportedInterfaces": {
              "AudioPlayer": {},
              "Display": {},
              "VideoApp": {}
            }
          },
          "user": {
            "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
          }
        },
        "Display": {},
        "AudioPlayer": {
          "playerActivity": "IDLE"
        }
      },
      "request": {
        "locale": "en-US",
        "requestId": "amzn1.echo-external.request.6b8bd8d8-6b59-40ef-a1a1-dc3b4d9c0a99",
        "timestamp": "2019-02-28T11:19:11Z",
        "type": "IntentRequest",
        "intent": {
          "name": "HelloWorldIntent"
        }
      },
      "version": "1.0",
      "session": {
        "application": {
          "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
        },
        "new": true,
        "sessionId": "SessionID.aa8c3b5b-1b1d-4fbe-bf70-11ba53741bcd",
        "user": {
          "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
        },
        "attributes": {}
      }
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:288
    Response Envelope:
    {
      "version": "1.0",
      "response": {
        "outputSpeech": {
          "type": "SSML",
          "ssml": "<speak>Hello World!</speak>"
        },
        "card": {
          "type": "Simple",
          "title": "Hello World",
          "content": "Hello World!"
        }
      },
      "userAgent": "ask-node/2.4.0 Node/v11.10.0",
      "sessionAttributes": {},
      "cardContent": "Hello World!",
      "cardTitle": "Hello World",
      "prompt": "<speak>Hello World!</speak>"
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:323
    File: index.test.yml Test: AMAZON.HelpIntent. Ask for help and exit. Utterance: LaunchRequest

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:326
    Request Envelope:
    {
      "context": {
        "System": {
          "application": {
            "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
          },
          "device": {
            "supportedInterfaces": {
              "AudioPlayer": {},
              "Display": {},
              "VideoApp": {}
            }
          },
          "user": {
            "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
          }
        },
        "Display": {},
        "AudioPlayer": {
          "playerActivity": "IDLE"
        }
      },
      "request": {
        "locale": "en-US",
        "requestId": "amzn1.echo-external.request.e94a99f2-c979-4976-828e-a1936882a456",
        "timestamp": "2019-02-28T11:19:11Z",
        "type": "LaunchRequest"
      },
      "version": "1.0",
      "session": {
        "application": {
          "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
        },
        "new": true,
        "sessionId": "SessionID.3d84f7cf-8806-40e5-9be8-6ef6b05ee1e8",
        "user": {
          "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
        }
      }
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:288
    Response Envelope:
    {
      "version": "1.0",
      "response": {
        "outputSpeech": {
          "type": "SSML",
          "ssml": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>"
        },
        "reprompt": {
          "outputSpeech": {
            "type": "SSML",
            "ssml": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>"
          }
        },
        "shouldEndSession": false,
        "card": {
          "type": "Simple",
          "title": "Hello World",
          "content": "Welcome to the Alexa Skills Kit, you can say hello!"
        }
      },
      "userAgent": "ask-node/2.4.0 Node/v11.10.0",
      "sessionAttributes": {},
      "cardContent": "Welcome to the Alexa Skills Kit, you can say hello!",
      "cardTitle": "Hello World",
      "prompt": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>",
      "reprompt": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>",
      "sessionEnded": false
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:323
    File: index.test.yml Test: AMAZON.HelpIntent. Ask for help and exit. Utterance: AMAZON.HelpIntent

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:326
    Request Envelope:
    {
      "context": {
        "System": {
          "application": {
            "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
          },
          "device": {
            "supportedInterfaces": {
              "AudioPlayer": {},
              "Display": {},
              "VideoApp": {}
            }
          },
          "user": {
            "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
          }
        },
        "Display": {},
        "AudioPlayer": {
          "playerActivity": "IDLE"
        }
      },
      "request": {
        "locale": "en-US",
        "requestId": "amzn1.echo-external.request.0cc95889-20cd-4025-aa3b-bc119be82cac",
        "timestamp": "2019-02-28T11:19:11Z",
        "type": "IntentRequest",
        "intent": {
          "name": "AMAZON.HelpIntent"
        }
      },
      "version": "1.0",
      "session": {
        "application": {
          "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
        },
        "new": false,
        "sessionId": "SessionID.3d84f7cf-8806-40e5-9be8-6ef6b05ee1e8",
        "user": {
          "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
        },
        "attributes": {}
      }
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:288
    Response Envelope:
    {
      "version": "1.0",
      "response": {
        "outputSpeech": {
          "type": "SSML",
          "ssml": "<speak>You can say hello to me!</speak>"
        },
        "reprompt": {
          "outputSpeech": {
            "type": "SSML",
            "ssml": "<speak>You can say hello to me!</speak>"
          }
        },
        "shouldEndSession": false,
        "card": {
          "type": "Simple",
          "title": "Hello World",
          "content": "You can say hello to me!"
        }
      },
      "userAgent": "ask-node/2.4.0 Node/v11.10.0",
      "sessionAttributes": {},
      "cardContent": "You can say hello to me!",
      "cardTitle": "Hello World",
      "prompt": "<speak>You can say hello to me!</speak>",
      "reprompt": "<speak>You can say hello to me!</speak>",
      "sessionEnded": false
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:323
    File: index.test.yml Test: AMAZON.HelpIntent. Ask for help and exit. Utterance: SessionEndedRequest

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:326
    Request Envelope:
    {
      "context": {
        "System": {
          "application": {
            "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
          },
          "device": {
            "supportedInterfaces": {
              "AudioPlayer": {},
              "Display": {},
              "VideoApp": {}
            }
          },
          "user": {
            "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
          }
        },
        "Display": {},
        "AudioPlayer": {
          "playerActivity": "IDLE"
        }
      },
      "request": {
        "locale": "en-US",
        "requestId": "amzn1.echo-external.request.a0dcf43f-7b90-48d0-b7f7-730a38821271",
        "timestamp": "2019-02-28T11:19:11Z",
        "type": "SessionEndedRequest",
        "reason": "USER_INITIATED"
      },
      "version": "1.0",
      "session": {
        "application": {
          "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
        },
        "new": false,
        "sessionId": "SessionID.3d84f7cf-8806-40e5-9be8-6ef6b05ee1e8",
        "user": {
          "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
        },
        "attributes": {}
      }
    }

  console.log lambda/custom/index.js:73
    Session ended with reason: USER_INITIATED

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:288
    Response Envelope:
    undefined

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:323
    File: index.test.yml Test: AMAZON.HelpIntent. Ask for help and stop. Utterance: LaunchRequest

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:326
    Request Envelope:
    {
      "context": {
        "System": {
          "application": {
            "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
          },
          "device": {
            "supportedInterfaces": {
              "AudioPlayer": {},
              "Display": {},
              "VideoApp": {}
            }
          },
          "user": {
            "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
          }
        },
        "Display": {},
        "AudioPlayer": {
          "playerActivity": "IDLE"
        }
      },
      "request": {
        "locale": "en-US",
        "requestId": "amzn1.echo-external.request.1135c162-b092-4cb6-8a3a-6a915446e336",
        "timestamp": "2019-02-28T11:19:11Z",
        "type": "LaunchRequest"
      },
      "version": "1.0",
      "session": {
        "application": {
          "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
        },
        "new": true,
        "sessionId": "SessionID.be24ef3b-c5c4-4d1c-bac4-e6348522f68a",
        "user": {
          "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
        }
      }
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:288
    Response Envelope:
    {
      "version": "1.0",
      "response": {
        "outputSpeech": {
          "type": "SSML",
          "ssml": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>"
        },
        "reprompt": {
          "outputSpeech": {
            "type": "SSML",
            "ssml": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>"
          }
        },
        "shouldEndSession": false,
        "card": {
          "type": "Simple",
          "title": "Hello World",
          "content": "Welcome to the Alexa Skills Kit, you can say hello!"
        }
      },
      "userAgent": "ask-node/2.4.0 Node/v11.10.0",
      "sessionAttributes": {},
      "cardContent": "Welcome to the Alexa Skills Kit, you can say hello!",
      "cardTitle": "Hello World",
      "prompt": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>",
      "reprompt": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>",
      "sessionEnded": false
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:323
    File: index.test.yml Test: AMAZON.HelpIntent. Ask for help and stop. Utterance: AMAZON.HelpIntent

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:326
    Request Envelope:
    {
      "context": {
        "System": {
          "application": {
            "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
          },
          "device": {
            "supportedInterfaces": {
              "AudioPlayer": {},
              "Display": {},
              "VideoApp": {}
            }
          },
          "user": {
            "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
          }
        },
        "Display": {},
        "AudioPlayer": {
          "playerActivity": "IDLE"
        }
      },
      "request": {
        "locale": "en-US",
        "requestId": "amzn1.echo-external.request.4ea7590b-b232-4a12-ad14-839858624164",
        "timestamp": "2019-02-28T11:19:11Z",
        "type": "IntentRequest",
        "intent": {
          "name": "AMAZON.HelpIntent"
        }
      },
      "version": "1.0",
      "session": {
        "application": {
          "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
        },
        "new": false,
        "sessionId": "SessionID.be24ef3b-c5c4-4d1c-bac4-e6348522f68a",
        "user": {
          "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
        },
        "attributes": {}
      }
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:288
    Response Envelope:
    {
      "version": "1.0",
      "response": {
        "outputSpeech": {
          "type": "SSML",
          "ssml": "<speak>You can say hello to me!</speak>"
        },
        "reprompt": {
          "outputSpeech": {
            "type": "SSML",
            "ssml": "<speak>You can say hello to me!</speak>"
          }
        },
        "shouldEndSession": false,
        "card": {
          "type": "Simple",
          "title": "Hello World",
          "content": "You can say hello to me!"
        }
      },
      "userAgent": "ask-node/2.4.0 Node/v11.10.0",
      "sessionAttributes": {},
      "cardContent": "You can say hello to me!",
      "cardTitle": "Hello World",
      "prompt": "<speak>You can say hello to me!</speak>",
      "reprompt": "<speak>You can say hello to me!</speak>",
      "sessionEnded": false
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:323
    File: index.test.yml Test: AMAZON.HelpIntent. Ask for help and stop. Utterance: AMAZON.StopIntent

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:326
    Request Envelope:
    {
      "context": {
        "System": {
          "application": {
            "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
          },
          "device": {
            "supportedInterfaces": {
              "AudioPlayer": {},
              "Display": {},
              "VideoApp": {}
            }
          },
          "user": {
            "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
          }
        },
        "Display": {},
        "AudioPlayer": {
          "playerActivity": "IDLE"
        }
      },
      "request": {
        "locale": "en-US",
        "requestId": "amzn1.echo-external.request.30bbdd18-825b-4317-9869-88e524d53557",
        "timestamp": "2019-02-28T11:19:11Z",
        "type": "IntentRequest",
        "intent": {
          "name": "AMAZON.StopIntent"
        }
      },
      "version": "1.0",
      "session": {
        "application": {
          "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
        },
        "new": false,
        "sessionId": "SessionID.be24ef3b-c5c4-4d1c-bac4-e6348522f68a",
        "user": {
          "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
        },
        "attributes": {}
      }
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:288
    Response Envelope:
    {
      "version": "1.0",
      "response": {
        "outputSpeech": {
          "type": "SSML",
          "ssml": "<speak>Goodbye!</speak>"
        },
        "card": {
          "type": "Simple",
          "title": "Hello World",
          "content": "Goodbye!"
        }
      },
      "userAgent": "ask-node/2.4.0 Node/v11.10.0",
      "sessionAttributes": {},
      "cardContent": "Goodbye!",
      "cardTitle": "Hello World",
      "prompt": "<speak>Goodbye!</speak>"
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:323
    File: index.test.yml Test: AMAZON.HelpIntent. Ask for help and then for a fact. Utterance: LaunchRequest

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:326
    Request Envelope:
    {
      "context": {
        "System": {
          "application": {
            "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
          },
          "device": {
            "supportedInterfaces": {
              "AudioPlayer": {},
              "Display": {},
              "VideoApp": {}
            }
          },
          "user": {
            "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
          }
        },
        "Display": {},
        "AudioPlayer": {
          "playerActivity": "IDLE"
        }
      },
      "request": {
        "locale": "en-US",
        "requestId": "amzn1.echo-external.request.d97eb518-0b7f-4874-89ca-42484b06f904",
        "timestamp": "2019-02-28T11:19:11Z",
        "type": "LaunchRequest"
      },
      "version": "1.0",
      "session": {
        "application": {
          "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
        },
        "new": true,
        "sessionId": "SessionID.45cfa7ac-0c21-491f-8a32-9f79bd6e7ae3",
        "user": {
          "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
        }
      }
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:288
    Response Envelope:
    {
      "version": "1.0",
      "response": {
        "outputSpeech": {
          "type": "SSML",
          "ssml": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>"
        },
        "reprompt": {
          "outputSpeech": {
            "type": "SSML",
            "ssml": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>"
          }
        },
        "shouldEndSession": false,
        "card": {
          "type": "Simple",
          "title": "Hello World",
          "content": "Welcome to the Alexa Skills Kit, you can say hello!"
        }
      },
      "userAgent": "ask-node/2.4.0 Node/v11.10.0",
      "sessionAttributes": {},
      "cardContent": "Welcome to the Alexa Skills Kit, you can say hello!",
      "cardTitle": "Hello World",
      "prompt": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>",
      "reprompt": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>",
      "sessionEnded": false
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:323
    File: index.test.yml Test: AMAZON.HelpIntent. Ask for help and then for a fact. Utterance: AMAZON.HelpIntent

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:326
    Request Envelope:
    {
      "context": {
        "System": {
          "application": {
            "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
          },
          "device": {
            "supportedInterfaces": {
              "AudioPlayer": {},
              "Display": {},
              "VideoApp": {}
            }
          },
          "user": {
            "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
          }
        },
        "Display": {},
        "AudioPlayer": {
          "playerActivity": "IDLE"
        }
      },
      "request": {
        "locale": "en-US",
        "requestId": "amzn1.echo-external.request.3bf889c3-01c7-4cea-9a07-7a0ba08a41a7",
        "timestamp": "2019-02-28T11:19:11Z",
        "type": "IntentRequest",
        "intent": {
          "name": "AMAZON.HelpIntent"
        }
      },
      "version": "1.0",
      "session": {
        "application": {
          "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
        },
        "new": false,
        "sessionId": "SessionID.45cfa7ac-0c21-491f-8a32-9f79bd6e7ae3",
        "user": {
          "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
        },
        "attributes": {}
      }
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:288
    Response Envelope:
    {
      "version": "1.0",
      "response": {
        "outputSpeech": {
          "type": "SSML",
          "ssml": "<speak>You can say hello to me!</speak>"
        },
        "reprompt": {
          "outputSpeech": {
            "type": "SSML",
            "ssml": "<speak>You can say hello to me!</speak>"
          }
        },
        "shouldEndSession": false,
        "card": {
          "type": "Simple",
          "title": "Hello World",
          "content": "You can say hello to me!"
        }
      },
      "userAgent": "ask-node/2.4.0 Node/v11.10.0",
      "sessionAttributes": {},
      "cardContent": "You can say hello to me!",
      "cardTitle": "Hello World",
      "prompt": "<speak>You can say hello to me!</speak>",
      "reprompt": "<speak>You can say hello to me!</speak>",
      "sessionEnded": false
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:323
    File: index.test.yml Test: AMAZON.HelpIntent. Ask for help and then for a fact. Utterance: HelloWorldIntent

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:326
    Request Envelope:
    {
      "context": {
        "System": {
          "application": {
            "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
          },
          "device": {
            "supportedInterfaces": {
              "AudioPlayer": {},
              "Display": {},
              "VideoApp": {}
            }
          },
          "user": {
            "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
          }
        },
        "Display": {},
        "AudioPlayer": {
          "playerActivity": "IDLE"
        }
      },
      "request": {
        "locale": "en-US",
        "requestId": "amzn1.echo-external.request.341e9bd5-285b-425a-bd7d-1fdef7509943",
        "timestamp": "2019-02-28T11:19:11Z",
        "type": "IntentRequest",
        "intent": {
          "name": "HelloWorldIntent"
        }
      },
      "version": "1.0",
      "session": {
        "application": {
          "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
        },
        "new": false,
        "sessionId": "SessionID.45cfa7ac-0c21-491f-8a32-9f79bd6e7ae3",
        "user": {
          "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
        },
        "attributes": {}
      }
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:288
    Response Envelope:
    {
      "version": "1.0",
      "response": {
        "outputSpeech": {
          "type": "SSML",
          "ssml": "<speak>Hello World!</speak>"
        },
        "card": {
          "type": "Simple",
          "title": "Hello World",
          "content": "Hello World!"
        }
      },
      "userAgent": "ask-node/2.4.0 Node/v11.10.0",
      "sessionAttributes": {},
      "cardContent": "Hello World!",
      "cardTitle": "Hello World",
      "prompt": "<speak>Hello World!</speak>"
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:323
    File: index.test.yml Test: AMAZON.StopIntent Utterance: LaunchRequest

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:326
    Request Envelope:
    {
      "context": {
        "System": {
          "application": {
            "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
          },
          "device": {
            "supportedInterfaces": {
              "AudioPlayer": {},
              "Display": {},
              "VideoApp": {}
            }
          },
          "user": {
            "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
          }
        },
        "Display": {},
        "AudioPlayer": {
          "playerActivity": "IDLE"
        }
      },
      "request": {
        "locale": "en-US",
        "requestId": "amzn1.echo-external.request.60c4481b-1907-404d-93cb-3bc59d3fd3e8",
        "timestamp": "2019-02-28T11:19:11Z",
        "type": "LaunchRequest"
      },
      "version": "1.0",
      "session": {
        "application": {
          "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
        },
        "new": true,
        "sessionId": "SessionID.51a55fc4-930f-4417-90a6-768eb2bff351",
        "user": {
          "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
        }
      }
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:288
    Response Envelope:
    {
      "version": "1.0",
      "response": {
        "outputSpeech": {
          "type": "SSML",
          "ssml": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>"
        },
        "reprompt": {
          "outputSpeech": {
            "type": "SSML",
            "ssml": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>"
          }
        },
        "shouldEndSession": false,
        "card": {
          "type": "Simple",
          "title": "Hello World",
          "content": "Welcome to the Alexa Skills Kit, you can say hello!"
        }
      },
      "userAgent": "ask-node/2.4.0 Node/v11.10.0",
      "sessionAttributes": {},
      "cardContent": "Welcome to the Alexa Skills Kit, you can say hello!",
      "cardTitle": "Hello World",
      "prompt": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>",
      "reprompt": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>",
      "sessionEnded": false
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:323
    File: index.test.yml Test: AMAZON.StopIntent Utterance: AMAZON.StopIntent

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:326
    Request Envelope:
    {
      "context": {
        "System": {
          "application": {
            "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
          },
          "device": {
            "supportedInterfaces": {
              "AudioPlayer": {},
              "Display": {},
              "VideoApp": {}
            }
          },
          "user": {
            "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
          }
        },
        "Display": {},
        "AudioPlayer": {
          "playerActivity": "IDLE"
        }
      },
      "request": {
        "locale": "en-US",
        "requestId": "amzn1.echo-external.request.105a42d3-df9c-4269-b2ec-28f0dac0f5f6",
        "timestamp": "2019-02-28T11:19:11Z",
        "type": "IntentRequest",
        "intent": {
          "name": "AMAZON.StopIntent"
        }
      },
      "version": "1.0",
      "session": {
        "application": {
          "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
        },
        "new": false,
        "sessionId": "SessionID.51a55fc4-930f-4417-90a6-768eb2bff351",
        "user": {
          "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
        },
        "attributes": {}
      }
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:288
    Response Envelope:
    {
      "version": "1.0",
      "response": {
        "outputSpeech": {
          "type": "SSML",
          "ssml": "<speak>Goodbye!</speak>"
        },
        "card": {
          "type": "Simple",
          "title": "Hello World",
          "content": "Goodbye!"
        }
      },
      "userAgent": "ask-node/2.4.0 Node/v11.10.0",
      "sessionAttributes": {},
      "cardContent": "Goodbye!",
      "cardTitle": "Hello World",
      "prompt": "<speak>Goodbye!</speak>"
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:323
    File: index.test.yml Test: AMAZON.CancelIntent Utterance: LaunchRequest

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:326
    Request Envelope:
    {
      "context": {
        "System": {
          "application": {
            "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
          },
          "device": {
            "supportedInterfaces": {
              "AudioPlayer": {},
              "Display": {},
              "VideoApp": {}
            }
          },
          "user": {
            "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
          }
        },
        "Display": {},
        "AudioPlayer": {
          "playerActivity": "IDLE"
        }
      },
      "request": {
        "locale": "en-US",
        "requestId": "amzn1.echo-external.request.310d489d-72e2-4ef5-82ba-519805ed0c1c",
        "timestamp": "2019-02-28T11:19:11Z",
        "type": "LaunchRequest"
      },
      "version": "1.0",
      "session": {
        "application": {
          "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
        },
        "new": true,
        "sessionId": "SessionID.70138a15-f6bf-48e9-a686-d18658bc26c3",
        "user": {
          "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
        }
      }
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:288
    Response Envelope:
    {
      "version": "1.0",
      "response": {
        "outputSpeech": {
          "type": "SSML",
          "ssml": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>"
        },
        "reprompt": {
          "outputSpeech": {
            "type": "SSML",
            "ssml": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>"
          }
        },
        "shouldEndSession": false,
        "card": {
          "type": "Simple",
          "title": "Hello World",
          "content": "Welcome to the Alexa Skills Kit, you can say hello!"
        }
      },
      "userAgent": "ask-node/2.4.0 Node/v11.10.0",
      "sessionAttributes": {},
      "cardContent": "Welcome to the Alexa Skills Kit, you can say hello!",
      "cardTitle": "Hello World",
      "prompt": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>",
      "reprompt": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>",
      "sessionEnded": false
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:323
    File: index.test.yml Test: AMAZON.CancelIntent Utterance: AMAZON.CancelIntent

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:326
    Request Envelope:
    {
      "context": {
        "System": {
          "application": {
            "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
          },
          "device": {
            "supportedInterfaces": {
              "AudioPlayer": {},
              "Display": {},
              "VideoApp": {}
            }
          },
          "user": {
            "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
          }
        },
        "Display": {},
        "AudioPlayer": {
          "playerActivity": "IDLE"
        }
      },
      "request": {
        "locale": "en-US",
        "requestId": "amzn1.echo-external.request.a21a4031-7188-4ae3-86f0-435998975fc7",
        "timestamp": "2019-02-28T11:19:11Z",
        "type": "IntentRequest",
        "intent": {
          "name": "AMAZON.CancelIntent"
        }
      },
      "version": "1.0",
      "session": {
        "application": {
          "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
        },
        "new": false,
        "sessionId": "SessionID.70138a15-f6bf-48e9-a686-d18658bc26c3",
        "user": {
          "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
        },
        "attributes": {}
      }
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:288
    Response Envelope:
    {
      "version": "1.0",
      "response": {
        "outputSpeech": {
          "type": "SSML",
          "ssml": "<speak>Goodbye!</speak>"
        },
        "card": {
          "type": "Simple",
          "title": "Hello World",
          "content": "Goodbye!"
        }
      },
      "userAgent": "ask-node/2.4.0 Node/v11.10.0",
      "sessionAttributes": {},
      "cardContent": "Goodbye!",
      "cardTitle": "Hello World",
      "prompt": "<speak>Goodbye!</speak>"
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:323
    File: index.test.yml Test: AMAZON.FallbackIntent Utterance: LaunchRequest

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:326
    Request Envelope:
    {
      "context": {
        "System": {
          "application": {
            "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
          },
          "device": {
            "supportedInterfaces": {
              "AudioPlayer": {},
              "Display": {},
              "VideoApp": {}
            }
          },
          "user": {
            "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
          }
        },
        "Display": {},
        "AudioPlayer": {
          "playerActivity": "IDLE"
        }
      },
      "request": {
        "locale": "en-US",
        "requestId": "amzn1.echo-external.request.4426b311-4234-42af-9b8a-f74b00c914aa",
        "timestamp": "2019-02-28T11:19:11Z",
        "type": "LaunchRequest"
      },
      "version": "1.0",
      "session": {
        "application": {
          "applicationId": "amzn1.echo-sdk-ams.app.ecff1ff0-e6b8-4e64-b285-10605a573286"
        },
        "new": true,
        "sessionId": "SessionID.f17f58eb-0e65-4001-a38e-73748b27f429",
        "user": {
          "userId": "amzn1.ask.account.e37bc414-4540-42f4-911f-8b8f3c150286"
        }
      }
    }

  console.log ../../../../../.nvm/versions/node/v11.10.0/lib/node_modules/bespoken-tools/node_modules/skill-testing-ml/dist/lib/runner/TestRunner.js:288
    Response Envelope:
    {
      "version": "1.0",
      "response": {
        "outputSpeech": {
          "type": "SSML",
          "ssml": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>"
        },
        "reprompt": {
          "outputSpeech": {
            "type": "SSML",
            "ssml": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>"
          }
        },
        "shouldEndSession": false,
        "card": {
          "type": "Simple",
          "title": "Hello World",
          "content": "Welcome to the Alexa Skills Kit, you can say hello!"
        }
      },
      "userAgent": "ask-node/2.4.0 Node/v11.10.0",
      "sessionAttributes": {},
      "cardContent": "Welcome to the Alexa Skills Kit, you can say hello!",
      "cardTitle": "Hello World",
      "prompt": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>",
      "reprompt": "<speak>Welcome to the Alexa Skills Kit, you can say hello!</speak>",
      "sessionEnded": false
    }

---------------|----------|----------|----------|----------|-------------------|
File           |  % Stmts | % Branch |  % Funcs |  % Lines | Uncovered Line #s |
---------------|----------|----------|----------|----------|-------------------|
All files      |    68.57 |      100 |        0 |    68.57 |                   |
 lambda/custom |    88.89 |      100 |      100 |    88.89 |                   |
  index.js     |    88.89 |      100 |      100 |    88.89 |          81,84,86 |
 test          |        0 |      100 |        0 |        0 |                   |
  context.js   |        0 |      100 |        0 |        0 |           1,2,4,7 |
  index.js     |        0 |      100 |      100 |        0 |           1,2,3,4 |
---------------|----------|----------|----------|----------|-------------------|
Test Suites: 1 failed, 1 total
Tests:       5 failed, 3 passed, 8 total
Snapshots:   0 total
Time:        2.79s
Ran all test suites.


