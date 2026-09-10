---
updatedAt: 2025-05-29T17:02:00.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# List

List information about existing service account API tokens.

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
    "/v3/workplace/service_accounts/service_account/{service_account}/tokens": {
      "get": {
        "summary": "List",
        "description": "List information about existing service account API tokens.",
        "operationId": "service_account_tokens-list",
        "parameters": [
          {
            "name": "page",
            "in": "query",
            "schema": {
              "type": "integer",
              "format": "int32",
              "default": 1
            }
          },
          {
            "name": "per_page",
            "in": "query",
            "schema": {
              "type": "integer",
              "format": "int32",
              "default": 20
            }
          },
          {
            "name": "service_account",
            "in": "path",
            "description": "Slug of the service account",
            "schema": {
              "type": "string"
            },
            "required": true
          }
        ],
        "responses": {
          "200": {
            "description": "200",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"api_tokens\": [{\n    \"name\": \"token\",\n    \"slug\": \"00000000-0000-0000-0000-000000000000\",\n    \"created_at\": \"2023-08-01T00:00:00.000Z\",\n    \"last_seen_at\": \"2024-01-05T00:00:00.000Z\",\n    \"expires_at\": \"2024-02-01T00:00:00.000Z\"\n  }],\n  \"success\": true\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "api_tokens": {
                      "type": "array",
                      "items": {
                        "type": "object",
                        "properties": {
                          "name": {
                            "type": "string",
                            "example": "token"
                          },
                          "slug": {
                            "type": "string",
                            "example": "00000000-0000-0000-0000-000000000000"
                          },
                          "created_at": {
                            "type": "string",
                            "example": "2023-08-01T00:00:00.000Z"
                          },
                          "last_seen_at": {
                            "type": "string",
                            "example": "2024-01-05T00:00:00.000Z"
                          },
                          "expires_at": {
                            "type": "string",
                            "example": "2024-02-01T00:00:00.000Z"
                          }
                        }
                      }
                    },
                    "success": {
                      "type": "boolean",
                      "example": true,
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