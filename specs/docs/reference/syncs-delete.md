---
updatedAt: 2025-05-29T17:01:52.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Delete

Delete an existing sync.

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
    "/v3/configs/config/syncs/sync": {
      "delete": {
        "summary": "Delete",
        "description": "Delete an existing sync.",
        "operationId": "syncs-delete",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "description": "The project slug",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "config",
            "in": "query",
            "description": "The config slug",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "sync",
            "in": "query",
            "description": "The sync slug",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "delete_from_target",
            "in": "query",
            "description": "Whether or not to delete the synced data from the target integration",
            "required": true,
            "schema": {
              "type": "boolean"
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
                    "value": "{}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {}
                }
              }
            }
          },
          "400": {
            "description": "400",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {}
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