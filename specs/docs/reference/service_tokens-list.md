---
updatedAt: 2025-05-29T17:01:54.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# List

Service Tokens

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
    "/v3/configs/config/tokens": {
      "get": {
        "summary": "List",
        "description": "Service Tokens",
        "operationId": "service_tokens-list",
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
          }
        ],
        "responses": {
          "200": {
            "description": "200",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"tokens\": [\n    {\n      \"name\": \"AWS Lambda\",\n      \"slug\": \"56c69f96-3045-11ea-978f-2e728ce88125\",\n      \"created_at\": \"2019-11-19T07:19:01.073Z\",\n      \"config\": \"dev\",\n      \"environment\": \"dev\",\n      \"project\": \"ed0c2a68b6t\",\n      \"expires_at\": null\n    }\n  ]\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "tokens": {
                      "type": "array",
                      "items": {
                        "type": "object",
                        "properties": {
                          "name": {
                            "type": "string",
                            "example": "AWS Lambda"
                          },
                          "slug": {
                            "type": "string",
                            "example": "56c69f96-3045-11ea-978f-2e728ce88125"
                          },
                          "created_at": {
                            "type": "string",
                            "example": "2019-11-19T07:19:01.073Z"
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
                            "example": "ed0c2a68b6t"
                          },
                          "expires_at": {}
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