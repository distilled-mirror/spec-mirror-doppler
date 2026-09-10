---
updatedAt: 2025-05-29T17:01:57.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Delete

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
    "/v3/workplace/groups/group/{slug}": {
      "delete": {
        "summary": "Delete",
        "description": "",
        "operationId": "groups-delete",
        "parameters": [
          {
            "name": "slug",
            "in": "path",
            "description": "The group's slug",
            "schema": {
              "type": "string"
            },
            "required": true
          }
        ],
        "responses": {
          "204": {
            "description": "204",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": ""
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