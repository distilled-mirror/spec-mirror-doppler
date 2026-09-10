---
updatedAt: 2025-05-29T17:01:23.000Z
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
    "/v3/projects/project/members": {
      "post": {
        "summary": "Add",
        "description": "",
        "operationId": "project_members-add",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "description": "Project slug",
            "required": true,
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "type",
                  "slug"
                ],
                "properties": {
                  "type": {
                    "type": "string",
                    "enum": [
                      "workplace_user",
                      "group",
                      "invite",
                      "service_account"
                    ]
                  },
                  "slug": {
                    "type": "string",
                    "description": "Member's slug"
                  },
                  "role": {
                    "type": "string",
                    "description": "Identifier of the project role"
                  },
                  "environments": {
                    "type": "array",
                    "description": "Environment slugs to grant the member access to",
                    "items": {
                      "type": "string"
                    }
                  }
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "200",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"member\": {\n    \"type\": \"workplace_user\",\n    \"slug\": \"00000000-0000-0000-0000-000000000000\",\n    \"role\": {\n    \t\"identifier\": \"collaborator\"\n    },\n    \"access_all_environments\": false,\n    \"environments\": [\"dev\"]\n  }\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "member": {
                      "type": "object",
                      "properties": {
                        "type": {
                          "type": "string",
                          "example": "workplace_user"
                        },
                        "slug": {
                          "type": "string",
                          "example": "00000000-0000-0000-0000-000000000000"
                        },
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
                        }
                      }
                    }
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