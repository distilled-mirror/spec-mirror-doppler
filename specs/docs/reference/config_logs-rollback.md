---
updatedAt: 2025-05-29T17:01:34.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Rollback

Config Log

# OpenAPI definition

```json
{
  "openapi": "3.1.0",
  "info": {
    "title": "core",
    "version": "4"
  },
  "servers": [
    {
      "url": "https://api.doppler.com/"
    }
  ],
  "components": {
    "securitySchemes": {
      "sec0": {
        "type": "oauth2",
        "flows": {}
      }
    }
  },
  "security": [
    {
      "sec0": []
    }
  ],
  "paths": {
    "/v3/configs/config/logs/log/rollback": {
      "post": {
        "summary": "Rollback",
        "description": "Config Log",
        "operationId": "config_logs-rollback",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "description": "Unique identifier for the project object.",
            "required": true,
            "schema": {
              "type": "string",
              "default": "PROJECT_NAME"
            }
          },
          {
            "name": "config",
            "in": "query",
            "description": "Name of the config object.",
            "required": true,
            "schema": {
              "type": "string",
              "default": "CONFIG_NAME"
            }
          },
          {
            "name": "log",
            "in": "query",
            "description": "Unique identifier for the log object.",
            "required": true,
            "schema": {
              "type": "string",
              "default": "LOG_ID"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "200",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"log\": {\n    \"id\": \"koVGA1cgzkFnTHx\",\n    \"text\": \"Rolled back log WaRMMyxHUg4lOKR\",\n    \"html\": \"Rolled back log <a  href='https://doppler.internal:3030/workplace/2ada3/enclave/484/configs/2026/logs?id=WaRMMyxHUg4lOKR'>WaRMMyxHUg4lOKR</a>\",\n    \"diff\": [\n      {\n        \"name\": \"STRIPE\",\n        \"removed\": \"sk_test_9YxLnoLDdvOPn2dfjBVPB\"\n      },\n      {\n        \"name\": \"ALGOLIA\",\n        \"removed\": \"N9TOPUBTO\"\n      }\n    ],\n    \"rollback\": true,\n    \"created_at\": \"2019-11-24T02:25:54.761Z\",\n    \"config\": \"dev\",\n    \"environment\": \"dev\",\n    \"project\": \"ed0c2a68b6\",\n    \"user\": {\n      \"email\": \"jake@piedpiper.com\",\n      \"name\": \"Jake Sun\",\n      \"username\": \"jake\",\n      \"profile_image_url\": \"https://www.gravatar.com/avatar/84da5be2b398382c676bfca6b38dae41?s=500&d=retro\"\n    }\n  }\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "log": {
                      "type": "object",
                      "properties": {
                        "id": {
                          "type": "string",
                          "example": "koVGA1cgzkFnTHx"
                        },
                        "text": {
                          "type": "string",
                          "example": "Rolled back log WaRMMyxHUg4lOKR"
                        },
                        "html": {
                          "type": "string",
                          "example": "Rolled back log <a  href='https://doppler.internal:3030/workplace/2ada3/enclave/484/configs/2026/logs?id=WaRMMyxHUg4lOKR'>WaRMMyxHUg4lOKR</a>"
                        },
                        "diff": {
                          "type": "array",
                          "items": {
                            "type": "object",
                            "properties": {
                              "name": {
                                "type": "string",
                                "example": "STRIPE"
                              },
                              "removed": {
                                "type": "string",
                                "example": "sk_test_9YxLnoLDdvOPn2dfjBVPB"
                              }
                            }
                          }
                        },
                        "rollback": {
                          "type": "boolean",
                          "example": true,
                          "default": true
                        },
                        "created_at": {
                          "type": "string",
                          "example": "2019-11-24T02:25:54.761Z"
                        },
                        "config": {
                          "type": "string",
                          "example": "dev"
                        },
                        "environment": {
                          "type": "string",
                          "example": "dev"
                        },
                        "project": {
                          "type": "string",
                          "example": "ed0c2a68b6"
                        },
                        "user": {
                          "type": "object",
                          "properties": {
                            "email": {
                              "type": "string",
                              "example": "jake@piedpiper.com"
                            },
                            "name": {
                              "type": "string",
                              "example": "Jake Sun"
                            },
                            "username": {
                              "type": "string",
                              "example": "jake"
                            },
                            "profile_image_url": {
                              "type": "string",
                              "example": "https://www.gravatar.com/avatar/84da5be2b398382c676bfca6b38dae41?s=500&d=retro"
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        },
        "deprecated": false
      }
    }
  },
  "x-readme": {
    "headers": [],
    "explorer-enabled": true,
    "proxy-enabled": false
  },
  "x-readme-fauxas": true
}
```