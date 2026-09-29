---
updatedAt: 2025-05-29T17:01:11.000Z
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
    "/v3/workplace/roles": {
      "get": {
        "summary": "List",
        "description": "",
        "operationId": "workplace_roles-list",
        "responses": {
          "200": {
            "description": "200",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"roles\": [{\n    \"name\": \"custom\",\n    \"permissions\": [\"team\"],\n    \"identifier\": \"custom\",\n    \"created_at\": \"2023-08-01T00:00:00.000Z\",\n    \"is_custom_role\": false,\n    \"is_inline_role\": false\n\t}]\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "roles": {
                      "type": "array",
                      "items": {
                        "type": "object",
                        "properties": {
                          "name": {
                            "type": "string",
                            "example": "custom"
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