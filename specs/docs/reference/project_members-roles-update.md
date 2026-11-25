---
updatedAt: 2026-11-13T05:57:48.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Update Role

Replace the environments and configs one of the member's roles applies to.

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
      "patch": {
        "summary": "Update Role",
        "description": "Replace the environments and configs one of the member's roles applies to.",
        "operationId": "project_members-roles-update",
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
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "environments"
                ],
                "properties": {
                  "environments": {
                    "type": "array",
                    "description": "Environment slugs this role applies to",
                    "items": {
                      "type": "string"
                    }
                  },
                  "configs": {
                    "type": "array",
                    "description": "Config names this role applies to. Omit to keep the role's current configs. See: https://docs.doppler.com/docs/advanced-permissions#grant-access-to-individual-configs",
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
                    "value": "{\n  \"member\": {\n    \"type\": \"workplace_user\",\n    \"slug\": \"00000000-0000-0000-0000-000000000000\",\n    \"role\": {\n    \t\"identifier\": \"viewer\"\n    },\n    \"access_all_environments\": false,\n    \"environments\": [\"dev\"],\n    \"roles\": [{\n    \t\"role\": {\n    \t\t\"identifier\": \"viewer\"\n    \t},\n    \t\"access_all_environments\": false,\n    \t\"environments\": [\"dev\"],\n    \t\"configs\": []\n    }, {\n    \t\"role\": {\n    \t\t\"identifier\": \"collaborator\"\n    \t},\n    \t\"access_all_environments\": false,\n    \t\"environments\": [\"stg\"],\n    \t\"configs\": []\n    }]\n  }\n}"
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
                        },
                        "roles": {
                          "type": "array",
                          "description": "Every role the member holds on the project, oldest first. `role` and `environments` describe the first entry.",
                          "items": {
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
  "x-readme": {
    "headers": [],
    "explorer-enabled": true,
    "proxy-enabled": false
  },
  "x-readme-fauxas": true
}
```