---
updatedAt: 2025-12-19T21:35:50.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Update Assignees

Update the list of assigned reviewers for a change request

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
    "/v3/workplace/change_requests/change_request/{change_request_id}/assignees": {
      "put": {
        "description": "",
        "operationId": "post_v3workplacechange_requestschange_request{change_request_id}",
        "responses": {
          "200": {
            "description": "",
            "content": {
              "application/json": {
                "schema": {
                  "type": "object",
                  "properties": {
                    "assigned": {
                      "type": "array",
                      "items": {
                        "properties": {
                          "type": {
                            "type": "string",
                            "enum": [
                              "WorkplaceUser",
                              "ServiceAccount"
                            ]
                          },
                          "slug": {
                            "type": "string"
                          },
                          "name": {
                            "type": "string"
                          },
                          "email": {
                            "type": "string"
                          },
                          "image": {
                            "type": "string"
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
            "in": "path",
            "name": "change_request_id",
            "schema": {
              "type": "string"
            },
            "required": true
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "assigned": {
                    "type": "array",
                    "items": {
                      "properties": {
                        "type": {
                          "type": "string",
                          "enum": [
                            "WorkplaceUser",
                            "ServiceAccount"
                          ]
                        },
                        "slug": {
                          "type": "string"
                        }
                      },
                      "type": "object",
                      "required": [
                        "type",
                        "slug"
                      ]
                    }
                  }
                },
                "required": [
                  "assigned"
                ]
              }
            }
          }
        }
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