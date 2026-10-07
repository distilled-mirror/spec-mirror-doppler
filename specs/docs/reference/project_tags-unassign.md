---
updatedAt: 2026-10-06T02:23:00.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Unassign

Remove a tag from a project. The tag itself isn't deleted. Requires the `enclave_project_tags_manage` project permission.

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
    "/v3/projects/project/tags/tag/{tag}": {
      "delete": {
        "summary": "Unassign",
        "operationId": "project_tags-unassign",
        "deprecated": false,
        "description": "Remove a tag from a project. The tag itself isn't deleted. Requires the `enclave_project_tags_manage` project permission.",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "required": true,
            "description": "The project's slug.",
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "tag",
            "in": "path",
            "required": true,
            "description": "The tag's slug.",
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "204": {
            "description": "The tag was removed from the project. The response has no body."
          },
          "400": {
            "description": "The tag isn't assigned to the project.",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"messages\": [\n    \"This tag is not assigned to this project.\"\n  ],\n  \"success\": false\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "messages": {
                      "type": "array",
                      "items": {
                        "type": "string",
                        "example": "This tag is not assigned to this project."
                      }
                    },
                    "success": {
                      "type": "boolean",
                      "example": false
                    }
                  }
                }
              }
            }
          },
          "404": {
            "description": "The tag doesn't exist.",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"messages\": [\n    \"Tag does not exist\"\n  ],\n  \"success\": false\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "messages": {
                      "type": "array",
                      "items": {
                        "type": "string",
                        "example": "Tag does not exist"
                      }
                    },
                    "success": {
                      "type": "boolean",
                      "example": false
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