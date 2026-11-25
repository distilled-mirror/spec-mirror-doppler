---
updatedAt: 2026-11-13T05:57:48.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Retrieve Role

Retrieve one of the member's roles on the project.

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
      "get": {
        "summary": "Retrieve Role",
        "description": "Retrieve one of the member's roles on the project.",
        "operationId": "project_members-roles-get",
        "parameters": [
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
            "name": "type",
            "in": "path",
            "schema": {
              "type": "string",
              "enum": [
                "workplace_user",
                "group",
                "invite",
                "service_account"
              ]
            },
            "required": true
          },
          {
            "name": "slug",
            "in": "path",
            "description": "Member's slug",
            "schema": {
              "type": "string"
            },
            "required": true
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
          "200": {
            "description": "OK",
            "content": {
              "application/json": {
                "schema": {
                  "type": "object",
                  "properties": {
                    "role": {
                      "type": "object",
                      "properties": {
                        "role": {
                          "type": "object",
                          "properties": {
                            "identifier": {
                              "type": "string",
                              "example": "collaborator"
                            }
                          }
                        },
                        "access_all_environments": {
                          "type": "boolean",
                          "example": false,
                          "default": true
                        },
                        "environments": {
                          "type": "array",
                          "items": {
                            "type": "string",
                            "example": "dev"
                          }
                        },
                        "configs": {
                          "type": "array",
                          "items": {
                            "type": "string",
                            "example": "prd_aws"
                          }
                        }
                      }
                    }
                  }
                },
                "examples": {
                  "Result": {
                    "value": "{\n  \"role\": {\n    \"role\": {\n    \t\"identifier\": \"collaborator\"\n    },\n    \"access_all_environments\": false,\n    \"environments\": [\"stg\"],\n    \"configs\": []\n  }\n}"
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