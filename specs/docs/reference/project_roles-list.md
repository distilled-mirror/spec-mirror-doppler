---
updatedAt: 2025-05-29T17:01:21.000Z
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
    "/v3/projects/roles": {
      "get": {
        "summary": "List",
        "description": "",
        "operationId": "project_roles-list",
        "responses": {
          "200": {
            "description": "200",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"roles\": [{\n    \"name\": \"custom\",\n    \"permissions\": [\"enclave_config_logs\"],\n    \"identifier\": \"custom\",\n    \"created_at\": \"2023-08-01T00:00:00.000Z\",\n    \"is_custom_role\": false\n\t}]\n}"
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