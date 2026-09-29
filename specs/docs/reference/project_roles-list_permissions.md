---
updatedAt: 2025-05-29T17:01:22.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# List Permissions

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
    "/v3/projects/permissions": {
      "get": {
        "summary": "List Permissions",
        "description": "",
        "operationId": "project_roles-list_permissions",
        "responses": {
          "200": {
            "description": "200",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"permissions\": [\"enclave_config_logs\"]\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "permissions": {
                      "type": "array",
                      "items": {
                        "type": "string",
                        "example": "enclave_config_logs"
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