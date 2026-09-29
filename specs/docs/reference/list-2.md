---
updatedAt: 2026-05-20T09:32:24.000Z
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
    "/v3/integrations/integration/members": {
      "get": {
        "description": "",
        "responses": {
          "200": {
            "description": "",
            "content": {
              "application/json": {
                "schema": {
                  "type": "object",
                  "properties": {
                    "members": {
                      "type": "array",
                      "items": {
                        "properties": {
                          "type": {
                            "type": "string",
                            "enum": [
                              "workplace_user",
                              "invite",
                              "group",
                              "service_account"
                            ]
                          },
                          "slug": {
                            "type": "string"
                          },
                          "role": {
                            "type": "object",
                            "properties": {
                              "identifier": {
                                "type": "string"
                              }
                            }
                          }
                        },
                        "type": "object"
                      }
                    }
                  }
                }
              }
            }
          }
        },
        "parameters": [
          {
            "in": "query",
            "name": "integration",
            "schema": {
              "type": "string"
            },
            "required": true,
            "description": "Integration slug"
          },
          {
            "in": "query",
            "name": "page",
            "schema": {
              "type": "integer",
              "format": "int32",
              "default": "1"
            }
          },
          {
            "in": "query",
            "name": "per_page",
            "schema": {
              "type": "integer",
              "format": "int32",
              "default": "20"
            }
          }
        ],
        "operationId": "get_v3-integrations-integration-members",
        "summary": "List"
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