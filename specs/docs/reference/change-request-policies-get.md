---
updatedAt: 2025-05-29T17:02:05.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Retrieve

Fetch an existing change request policy

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
    "/v3/workplace/change_request_policies/change_request_policy/{slug}": {
      "get": {
        "summary": "Retrieve",
        "description": "Fetch an existing change request policy",
        "operationId": "change-request-policies-get",
        "parameters": [
          {
            "name": "slug",
            "in": "path",
            "description": "Unique id of the policy",
            "schema": {
              "type": "string"
            },
            "required": true
          }
        ],
        "responses": {
          "200": {
            "description": "200",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n    \"policy\": {\n        \"id\": \"00000000-0000-0000-0000-000000000000\",\n        \"name\": \"Reviewer Policy\",\n        \"description\": \"A description of the policy.\",\n        \"rules\": [\n //         {\n //             \"type\": \"RequiredReviewer\",\n //             \"count\": 1,\n //             \"subjects\": [\n //                 {\n //                     \"type\": \"WorkplaceUser\",\n //                     \"slug\": \"00000000-0000-0000-0000-000000000000\",\n //                     \"name\": \"John Developer\",\n //                     \"description\": \"john.dev@doppler.com\",\n //                     \"isActive\": true,\n //                     \"image\": \"https://www.gravatar.com/avatar/0000\"\n //                 }\n //             ]\n //         }\n        ],\n        \"targets\": {\n            \"allProjects\": false,\n            \"projects\": {\n//              \"example-project-a\": {\n//                  \"all\": true\n//              },\n//              \"example-project-b\": {\n//                  \"all\": false,\n//                  \"envSlugs\": [\"dev\"],\n//                  \"configNames\": []\n//              },\n//              \"example-project-c\": {\n//                  \"all\": false,\n//                  \"envSlugs\": [],\n//                 \"configNames\": [\"prd_infra\"]\n//              }\n            }\n        }\n    },\n    \"success\": true\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "policy": {
                      "type": "object",
                      "properties": {
                        "id": {
                          "type": "string",
                          "example": "00000000-0000-0000-0000-000000000000"
                        },
                        "name": {
                          "type": "string",
                          "example": "Reviewer Policy"
                        },
                        "description": {
                          "type": "string",
                          "example": "A description of the policy."
                        },
                        "rules": {
                          "type": "array"
                        },
                        "targets": {
                          "type": "object",
                          "properties": {
                            "allProjects": {
                              "type": "boolean",
                              "example": false,
                              "default": true
                            },
                            "projects": {
                              "type": "object",
                              "properties": {}
                            }
                          }
                        }
                      }
                    },
                    "success": {
                      "type": "boolean",
                      "example": true,
                      "default": true
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