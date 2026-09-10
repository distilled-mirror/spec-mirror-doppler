---
updatedAt: 2025-05-29T17:02:01.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Create

Generate a new service account API token.

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
      "post": {
        "summary": "Create",
        "description": "Generate a new service account API token.",
        "operationId": "service_account_tokens-create",
        "parameters": [
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
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "name": {
                    "type": "string",
                    "description": "The display name of the API token"
                  },
                  "expires_at": {
                    "type": "string",
                    "description": "The datetime at which the API token should expire. If not provided, the API token will remain vaild indefinitely unless manually revoked",
                    "format": "date-time"
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
                    "value": "{\n  \"api_token\": {\n    \"name\": \"token\",\n    \"slug\": \"00000000-0000-0000-0000-000000000000\",\n    \"created_at\": \"2023-03-14T00:00:00.000Z\",\n    \"last_seen_at\": null,\n    \"expires_at\": \"2023-08-01T00:00:00.000Z\"\n  },\n  \"api_key\": \"dp.sa.0000000000000000000000000000\",\n  \"success\": true\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "api_token": {
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
                          "example": "2023-03-14T00:00:00.000Z"
                        },
                        "last_seen_at": {},
                        "expires_at": {
                          "type": "string",
                          "example": "2023-08-01T00:00:00.000Z"
                        }
                      }
                    },
                    "api_key": {
                      "type": "string",
                      "example": "dp.sa.0000000000000000000000000000"
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