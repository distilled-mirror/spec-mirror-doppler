---
updatedAt: 2025-05-29T17:01:21.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Retrieve

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
    "/v3/projects/roles/role/{role}": {
      "get": {
        "summary": "Retrieve",
        "description": "",
        "operationId": "project_roles-get",
        "parameters": [
          {
            "name": "role",
            "in": "path",
            "description": "The role's unique identifier",
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
                    "value": "{\n  \"role\": {\n    \"name\": \"custom\",\n    \"permissions\": [\"enclave_config_logs\"],\n    \"identifier\": \"custom\",\n    \"created_at\": \"2023-08-01T00:00:00.000Z\",\n    \"is_custom_role\": false\n\t}\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "role": {
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
                            "example": "enclave_config_logs"
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
                        }
                      }
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
                    "value": ""
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