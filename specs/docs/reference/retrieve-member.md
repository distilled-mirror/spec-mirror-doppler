---
updatedAt: 2025-05-29T17:01:58.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Retrieve Member

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
    "/v3/workplace/groups/group/{group_slug}/members/{member_type}/{member_slug}": {
      "get": {
        "summary": "Retrieve Member",
        "description": "",
        "operationId": "retrieve-member",
        "parameters": [
          {
            "name": "group_slug",
            "in": "path",
            "description": "The group's slug",
            "schema": {
              "type": "string"
            },
            "required": true
          },
          {
            "name": "member_type",
            "in": "path",
            "schema": {
              "type": "string",
              "enum": [
                "workplace_user"
              ]
            },
            "required": true
          },
          {
            "name": "member_slug",
            "in": "path",
            "description": "The member's slug",
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
                    "value": "{\n  \"group\": {\n    \"name\": \"group\",\n    \"slug\": \"00000000-0000-0000-0000-000000000000\",\n    \"created_at\": \"2023-08-01T00:00:00.000Z\",\n    \"default_project_role\": {\n      \"identifier\": \"no_access\"\n    },\n    \"projects\": [{\n    \t\"name\": \"Project\",\n      \"slug\": \"project\",\n      \"role\": {\n        \"identifier\": \"viewer\"\n      }\n    }],\n    \"members\": [{\n      \"type\": \"workplace_user\",\n      \"slug\": \"00000000-0000-0000-0000-000000000000\"\n    }]\n  }\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "group": {
                      "type": "object",
                      "properties": {
                        "name": {
                          "type": "string",
                          "example": "group"
                        },
                        "slug": {
                          "type": "string",
                          "example": "00000000-0000-0000-0000-000000000000"
                        },
                        "created_at": {
                          "type": "string",
                          "example": "2023-08-01T00:00:00.000Z"
                        },
                        "default_project_role": {
                          "type": "object",
                          "properties": {
                            "identifier": {
                              "type": "string",
                              "example": "no_access"
                            }
                          }
                        },
                        "projects": {
                          "type": "array",
                          "items": {
                            "type": "object",
                            "properties": {
                              "name": {
                                "type": "string",
                                "example": "Project"
                              },
                              "slug": {
                                "type": "string",
                                "example": "project"
                              },
                              "role": {
                                "type": "object",
                                "properties": {
                                  "identifier": {
                                    "type": "string",
                                    "example": "viewer"
                                  }
                                }
                              }
                            }
                          }
                        },
                        "members": {
                          "type": "array",
                          "items": {
                            "type": "object",
                            "properties": {
                              "type": {
                                "type": "string",
                                "example": "workplace_user"
                              },
                              "slug": {
                                "type": "string",
                                "example": "00000000-0000-0000-0000-000000000000"
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
          "404": {
            "description": "404",
            "content": {
              "text/plain": {
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