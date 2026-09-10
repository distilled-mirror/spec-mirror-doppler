---
updatedAt: 2025-05-29T17:02:01.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Delete

Revoke an existing service account API token.

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
    "/v3/workplace/service_accounts/service_account/{service_account}/tokens/token/{api_token}": {
      "delete": {
        "summary": "Delete",
        "description": "Revoke an existing service account API token.",
        "operationId": "service_account_tokens-delete",
        "parameters": [
          {
            "name": "service_account",
            "in": "path",
            "description": "Slug of the service account",
            "schema": {
              "type": "string"
            },
            "required": true
          },
          {
            "name": "api_token",
            "in": "path",
            "description": "Slug of the API token",
            "schema": {
              "type": "string"
            },
            "required": true
          }
        ],
        "responses": {
          "204": {
            "description": "204",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": ""
                  }
                }
              }
            }
          },
          "404": {
            "description": "404",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{ \n  \"messages\": [\"Service account API token does not exist\"], \n  \"success\": false \n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "messages": {
                      "type": "array",
                      "items": {
                        "type": "string",
                        "example": "Service account API token does not exist"
                      }
                    },
                    "success": {
                      "type": "boolean",
                      "example": false,
                      "default": true
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