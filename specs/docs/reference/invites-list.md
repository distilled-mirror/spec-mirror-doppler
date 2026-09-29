---
updatedAt: 2025-05-29T17:01:55.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

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
    "/v3/workplace/invites": {
      "get": {
        "summary": "List",
        "description": "",
        "operationId": "invites-list",
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
                    "value": "{\n  \"invites\": [{\n    \"slug\": \"00000000-0000-0000-0000-000000000000\",\n    \"email\": \"doppler@example.com\",\n    \"created_at\": \"2023-08-01T00:00:00.000Z\",\n    \"workplace_role\": {\n      \"name\": \"Custom\",\n      \"permissions\": [\"team\"],\n      \"identifier\": \"custom\",\n      \"created_at\": \"2023-08-01T00:00:00.000Z\",\n      \"is_custom_role\": false,\n      \"is_inline_role\": false\n    }\n  }]\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "invites": {
                      "type": "array",
                      "items": {
                        "type": "object",
                        "properties": {
                          "slug": {
                            "type": "string",
                            "example": "00000000-0000-0000-0000-000000000000"
                          },
                          "email": {
                            "type": "string",
                            "example": "doppler@example.com"
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