---
updatedAt: 2026-05-20T09:31:38.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Add

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
      "post": {
        "description": "",
        "responses": {
          "200": {
            "description": "",
            "content": {
              "application/json": {
                "schema": {
                  "type": "object",
                  "properties": {
                    "member": {
                      "type": "object",
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
          }
        ],
        "operationId": "post_v3-integrations-integration-members",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
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
                    "type": "string"
                  }
                },
                "required": [
                  "type",
                  "slug",
                  "role"
                ]
              }
            }
          }
        },
        "summary": "Add"
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