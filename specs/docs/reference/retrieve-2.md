---
updatedAt: 2026-05-20T09:36:44.000Z
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
    "/v3/workplace/integrations/integration/members/{type}/{slug}": {
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
            "in": "path",
            "name": "type",
            "schema": {
              "type": "string",
              "enum": [
                "workplace_user",
                "invite",
                "group",
                "service_account"
              ]
            },
            "required": true
          },
          {
            "in": "path",
            "name": "slug",
            "schema": {
              "type": "string"
            },
            "required": true,
            "description": "Member's slug"
          },
          {
            "in": "query",
            "name": "integration",
            "schema": {
              "type": "string"
            },
            "description": "Integration slug",
            "required": true
          }
        ],
        "operationId": "get_v3-workplace-integrations-integration-members-type-slug",
        "summary": "Retrieve"
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