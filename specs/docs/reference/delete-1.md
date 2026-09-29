---
updatedAt: 2026-05-20T09:40:23.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

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
    "/v3/workplace/integrations/integration/members/{type}/{slug}": {
      "delete": {
        "description": "",
        "responses": {
          "204": {
            "description": ""
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
            "required": true,
            "description": "Integration slug"
          }
        ],
        "operationId": "delete_v3-workplace-integrations-integration-members-type-slug",
        "summary": "Delete"
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