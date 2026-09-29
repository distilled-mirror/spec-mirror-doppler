---
updatedAt: 2025-05-29T17:01:34.000Z
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
    "/v3/configs/config/trusted_ips": {
      "get": {
        "summary": "List",
        "description": "",
        "operationId": "configs-list_trusted_ips",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "config",
            "in": "query",
            "required": true,
            "schema": {
              "type": "string"
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
                    "value": "{\n  \"ips\": [\n  \t\"0.0.0.0/0\"\n  ]\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "ips": {
                      "type": "array",
                      "items": {
                        "type": "string",
                        "example": "0.0.0.0/0"
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