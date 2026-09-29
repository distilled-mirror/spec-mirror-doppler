---
updatedAt: 2026-05-20T09:31:38.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Update

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
    "/v3/integrations/integration/members/{type}/{slug}": {
      "patch": {
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
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "role": {
                    "type": "string"
                  }
                },
                "required": [
                  "role"
                ]
              }
            }
          }
        },
        "operationId": "patch_v3-integrations-integration-members-type-slug",
        "summary": "Update"
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