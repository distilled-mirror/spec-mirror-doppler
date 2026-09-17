---
updatedAt: 2026-09-16T15:03:42.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Retrieve

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
    "/v3/webhooks/webhook/{slug}": {
      "get": {
        "summary": "Retrieve",
        "description": "Webhook",
        "operationId": "webhooks-get",
        "parameters": [
          {
            "name": "slug",
            "in": "path",
            "description": "Webhook's slug",
            "schema": {
              "type": "string"
            },
            "required": true
          },
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
                    "webhook": {
                      "type": "object",
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
                          "properties": {
                            "type": {
                              "type": "string",
                              "enum": [
                                "None",
                                "Basic",
                                "Bearer"
                              ]
                            }
                          },
                          "description": "Webhook's authentication type"
                        },
                        "enabledConfigs": {
                          "type": "array",
                          "items": {
                            "type": "string"
                          },
                          "description": "The configs the webhook will trigger for"
                        },
                        "canManage": {
                          "type": "boolean",
                          "description": "Whether the requestor has permission to modify the webhook"
                        }
                      }
                    }
                  },
                  "required": [
                    "webhook"
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
        }
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