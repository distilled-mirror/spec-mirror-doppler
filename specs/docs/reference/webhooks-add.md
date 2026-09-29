---
updatedAt: 2025-05-29T17:02:02.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Add

Webhook

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
    "/v3/webhooks": {
      "post": {
        "summary": "Add",
        "description": "Webhook",
        "operationId": "webhooks-add",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "description": "The project's name",
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "url"
                ],
                "properties": {
                  "url": {
                    "type": "string",
                    "description": "The webhook URL. Must be https"
                  },
                  "secret": {
                    "type": "string",
                    "description": "See: https://docs.doppler.com/docs/webhooks#verify-webhook-with-request-signing"
                  },
                  "authentication": {
                    "type": "object",
                    "properties": {
                      "type": {
                        "type": "string",
                        "enum": [
                          "None",
                          "Bearer",
                          "Basic"
                        ]
                      },
                      "token": {
                        "type": "string",
                        "description": "Used when type = Bearer"
                      },
                      "username": {
                        "type": "string",
                        "description": "Used when type = Basic"
                      },
                      "password": {
                        "type": "string",
                        "description": "Used when type = Basic"
                      }
                    }
                  },
                  "payload": {
                    "type": "string",
                    "description": "See: https://docs.doppler.com/docs/webhooks#default-payload",
                    "format": "json"
                  },
                  "enableConfigs": {
                    "type": "array",
                    "description": "Config slugs that the webhook should be enabled for",
                    "items": {
                      "type": "string"
                    }
                  },
                  "name": {
                    "type": "string",
                    "description": "The name of the webhook."
                  }
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "200",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {}
                }
              }
            }
          },
          "400": {
            "description": "400",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {}
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