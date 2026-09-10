---
updatedAt: 2025-05-29T17:01:58.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# List

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
    "/v3/workplace/service_accounts": {
      "get": {
        "summary": "List",
        "description": "",
        "operationId": "service_accounts-list",
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
          }
        ],
        "responses": {
          "200": {
            "description": "200",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"service_accounts\": [{\n    \"name\": \"sa\",\n    \"slug\": \"00000000-0000-0000-0000-000000000000\",\n    \"created_at\": \"2023-08-01T00:00:00.000Z\",\n    \"workplace_role\": {\n      \"name\": \"Custom\",\n      \"permissions\": [\"team\"],\n      \"identifier\": \"custom\",\n      \"created_at\": \"2023-08-01T00:00:00.000Z\",\n      \"is_custom_role\": false,\n      \"is_inline_role\": false\n    }\n  }]\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "service_accounts": {
                      "type": "array",
                      "items": {
                        "type": "object",
                        "properties": {
                          "name": {
                            "type": "string",
                            "example": "sa"
                          },
                          "slug": {
                            "type": "string",
                            "example": "00000000-0000-0000-0000-000000000000"
                          },
                          "created_at": {
                            "type": "string",
                            "example": "2023-08-01T00:00:00.000Z"
                          },
                          "workplace_role": {
                            "type": "object",
                            "properties": {
                              "name": {
                                "type": "string",
                                "example": "Custom"
                              },
                              "permissions": {
                                "type": "array",
                                "items": {
                                  "type": "string",
                                  "example": "team"
                                }
                              },
                              "identifier": {
                                "type": "string",
                                "example": "custom"
                              },
                              "created_at": {
                                "type": "string",
                                "example": "2023-08-01T00:00:00.000Z"
                              },
                              "is_custom_role": {
                                "type": "boolean",
                                "example": false,
                                "default": true
                              },
                              "is_inline_role": {
                                "type": "boolean",
                                "example": false,
                                "default": true
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