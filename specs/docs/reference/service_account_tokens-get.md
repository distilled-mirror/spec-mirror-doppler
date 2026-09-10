---
updatedAt: 2025-05-29T17:02:01.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Retrieve

Retrieve information about a single service account API token.

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
      "get": {
        "summary": "Retrieve",
        "description": "Retrieve information about a single service account API token.",
        "operationId": "service_account_tokens-get",
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
          "200": {
            "description": "200",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"api_token\": {\n    \"name\": \"token\",\n    \"slug\": \"00000000-0000-0000-0000-000000000000\",\n    \"created_at\": \"2023-03-14T00:00:00.000Z\",\n    \"last_seen_at\": \"2023-06-22T00:00:00.000Z\",\n    \"expires_at\": \"2023-08-01T00:00:00.000Z\"\n  },\n  \"success\": true\n}"
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
                        "last_seen_at": {
                          "type": "string",
                          "example": "2023-06-22T00:00:00.000Z"
                        },
                        "expires_at": {
                          "type": "string",
                          "example": "2023-08-01T00:00:00.000Z"
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