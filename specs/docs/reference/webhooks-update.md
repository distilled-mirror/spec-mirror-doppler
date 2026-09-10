---
updatedAt: 2025-05-29T17:02:03.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Update

Webhook

Parameters for the PATCH endpoint are all optional. When undefined is provided, the field will not be changed. When null is provided, the field will be cleared.

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
      "patch": {
        "summary": "Update",
        "description": "Webhook",
        "operationId": "webhooks-update",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "description": "The project's name",
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "slug",
            "in": "path",
            "description": "Webhook's slug",
            "schema": {
              "type": "string"
            },
            "required": true
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
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
                  "name": {
                    "type": "string",
                    "description": "Name of the webhook."
                  },
                  "enableConfigs": {
                    "type": "array",
                    "description": "Config slugs that the webhook should be enabled for",
                    "items": {
                      "type": "string"
                    }
                  },
                  "disableConfigs": {
                    "type": "array",
                    "description": "Config slugs that the webhook should be disabled for",
                    "items": {
                      "type": "string"
                    }
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