---
updatedAt: 2025-05-29T17:01:37.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# List Names

Secret Names

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
    "/v3/configs/config/secrets/names": {
      "get": {
        "summary": "List Names",
        "description": "Secret Names",
        "operationId": "secrets-names",
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
          },
          {
            "name": "include_dynamic_secrets",
            "in": "query",
            "description": "Whether or not to issue leases and include dynamic secret values for the config",
            "schema": {
              "type": "boolean",
              "default": false
            }
          },
          {
            "name": "include_managed_secrets",
            "in": "query",
            "description": "Whether to include Doppler's auto-generated (managed) secrets",
            "schema": {
              "type": "boolean",
              "default": true
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
                    "value": "{\n  \"names\": [\n    \"STRIPE\",\n    \"ALGOLIA\",\n    \"DATABASE\",\n    \"USER\"\n  ]\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "names": {
                      "type": "array",
                      "items": {
                        "type": "string",
                        "example": "STRIPE"
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