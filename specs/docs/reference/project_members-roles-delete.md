---
updatedAt: 2026-11-13T05:57:48.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Delete Role

Remove one of the member's roles on the project. The member keeps any other roles.

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
    "/v3/projects/project/members/member/{type}/{slug}/roles/role/{role}": {
      "delete": {
        "summary": "Delete Role",
        "description": "Remove one of the member's roles on the project. The member keeps any other roles.",
        "operationId": "project_members-roles-delete",
        "parameters": [
          {
            "name": "type",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string",
              "enum": [
                "workplace_user",
                "group",
                "invite",
                "service_account"
              ]
            }
          },
          {
            "name": "slug",
            "in": "path",
            "description": "Member's slug",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "project",
            "in": "query",
            "description": "Project slug",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "role",
            "in": "path",
            "required": true,
            "schema": {
              "type": "string"
            },
            "description": "Identifier of the project role, e.g. `collaborator` or a custom role's identifier"
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