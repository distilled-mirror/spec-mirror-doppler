---
updatedAt: 2025-12-19T21:35:50.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Apply Unit

Apply a change request unit's updates to the target config

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
    "/v3/workplace/change_requests/change_request/{change_request_id}/units/unit/{unit_id}/apply": {
      "post": {
        "description": "",
        "operationId": "post_v3workplacechange_requestschange_request{change_request_id}unitsunit{unit_id}apply",
        "responses": {
          "200": {
            "description": "",
            "content": {
              "application/json": {
                "schema": {
                  "type": "object",
                  "properties": {
                    "unit": {
                      "type": "object",
                      "properties": {
                        "id": {
                          "type": "string"
                        },
                        "status": {
                          "type": "string",
                          "enum": [
                            "applied"
                          ],
                          "default": "applied"
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
            "name": "change_request_id",
            "schema": {
              "type": "string"
            },
            "required": true
          },
          {
            "in": "path",
            "name": "unit_id",
            "schema": {
              "type": "string"
            },
            "required": true
          }
        ]
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