---
updatedAt: 2026-09-16T15:09:08.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# List

Webhooks

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
      "get": {
        "summary": "List",
        "description": "Webhooks",
        "operationId": "webhooks-list",
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
                  "properties": {
                    "webhooks": {
                      "type": "array",
                      "items": {
                        "properties": {
                          "id": {
                            "type": "string",
                            "description": "Webhook's slug"
                          },
                          "name": {
                            "type": "string",
                            "description": "Webhook's name"
                          },
                          "url": {
                            "type": "string",
                            "description": "Webhook's URL"
                          },
                          "enabled": {
                            "type": "boolean",
                            "description": "Whether the webhook is enabled or disabled"
                          },
                          "hasSecret": {
                            "type": "boolean",
                            "description": "Whether the webhook has a secret set. See: https://docs.doppler.com/docs/webhooks#verify-webhook-with-request-signing"
                          },
                          "authentication": {
                            "type": "object",
                            "description": "Webhook's authentication type",
                            "properties": {
                              "type": {
                                "type": "string",
                                "enum": [
                                  "None",
                                  "Basic",
                                  "Bearer"
                                ]
                              }
                            }
                          },
                          "enabledConfigs": {
                            "type": "array",
                            "description": "The configs the webhook will trigger for",
                            "items": {
                              "type": "string"
                            }
                          },
                          "canManage": {
                            "type": "boolean",
                            "description": "Whether the requestor has permission to modify the webhook"
                          }
                        },
                        "type": "object"
                      }
                    }
                  },
                  "required": [
                    "webhooks"
                  ]
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