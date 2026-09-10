---
updatedAt: 2025-05-29T17:02:06.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Update

Update an existing change request policy

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
      "post": {
        "summary": "Update",
        "description": "Update an existing change request policy",
        "operationId": "change-request-policies-update",
        "parameters": [
          {
            "name": "slug",
            "in": "path",
            "description": "The unique identifier of the policy.",
            "schema": {
              "type": "string"
            },
            "required": true
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "name",
                  "rules",
                  "targets"
                ],
                "properties": {
                  "name": {
                    "type": "string",
                    "description": "The name of the policy."
                  },
                  "description": {
                    "type": "string",
                    "description": "An optional description of the policy."
                  },
                  "rules": {
                    "type": "array",
                    "description": "A list of rules the policy enforces.",
                    "items": {
                      "properties": {
                        "type": {
                          "type": "string",
                          "enum": [
                            "\"RequiredReviewer\"",
                            "\"DisallowSelfReview\""
                          ]
                        },
                        "count": {
                          "type": "integer",
                          "description": "The number of required reviewers. Only applies to \"RequiredReviewer\" rules.",
                          "default": 1,
                          "format": "int32"
                        },
                        "subjects": {
                          "type": "array",
                          "description": "A list of required reviewers. If specified, only reviews from reviewers in this list will satisfy the policy. Only applies to \"RequiredReviewer\" rules.",
                          "items": {
                            "properties": {
                              "type": {
                                "type": "string",
                                "description": "The type of the subject.",
                                "enum": [
                                  "\"WorkplaceUser\"",
                                  "\"Group\""
                                ]
                              },
                              "slug": {
                                "type": "string",
                                "description": "The unique identifier of the subject."
                              }
                            },
                            "required": [
                              "type",
                              "slug"
                            ],
                            "type": "object"
                          }
                        }
                      },
                      "required": [
                        "type"
                      ],
                      "type": "object"
                    }
                  },
                  "targets": {
                    "type": "object",
                    "description": "Describes the which projects, environments, and configs the policy applies to.",
                    "properties": {
                      "allProjects": {
                        "type": "boolean",
                        "description": "If true, the policy will apply to every config in the workplace."
                      },
                      "projects": {
                        "type": "string",
                        "description": "A dictionary where the key is the project name, and the value contains information about what within the project the policy should apply to.",
                        "format": "json"
                      }
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
                    "value": "{\n    \"policy\": {\n        \"id\": \"00000000-0000-0000-0000-000000000000\",\n        \"name\": \"New Policy\",\n        \"description\": \"This policy requires 2 reviewers and does not allow self-reviews.\",\n        \"rules\": [\n//          {\n//              \"type\": \"RequiredReviewer\",\n//              \"count\": 2,\n//              \"subjects\": null\n//          },\n//          {\n//              \"type\": \"RequiredReviewer\",\n//              \"count\": 1,\n//              \"subjects\": [\n//                  {\n//                      \"type\": \"WorkplaceUser\",\n//                      \"slug\": \"00000000-0000-0000-0000-000000000000\"\n//                  }\n//              ]\n//          },\n//          {\n//              \"type\": \"DisallowSelfReview\"\n//          }\n        ],\n        \"targets\": {\n            \"allProjects\": false,\n            \"projects\": {\n//              \"example-project-a\": {\n//                  \"all\": true\n//              },\n//              \"example-project-b\": {\n//                  \"all\": false,\n//                  \"envSlugs\": [\"dev\"],\n//                  \"configNames\": []\n//              },\n//              \"example-project-c\": {\n//                  \"all\": false,\n//                  \"envSlugs\": [],\n//                 \"configNames\": [\"prd_infra\"]\n//              }\n            }\n        }\n    },\n    \"success\": true\n}"
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
                          "example": "New Policy"
                        },
                        "description": {
                          "type": "string",
                          "example": "This policy requires 2 reviewers and does not allow self-reviews."
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