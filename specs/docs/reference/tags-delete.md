---
updatedAt: 2026-10-06T02:23:00.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Delete

Delete a tag. A tag can't be deleted while it's assigned to any project, so remove it from every project first. Requires the `tags_delete` workplace permission.

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
    "/v3/workplace/tags/tag/{tag}": {
      "delete": {
        "summary": "Delete",
        "operationId": "tags-delete",
        "deprecated": false,
        "description": "Delete a tag. A tag can't be deleted while it's assigned to any project, so remove it from every project first. Requires the `tags_delete` workplace permission.",
        "parameters": [
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
            "description": "The tag was deleted. The response has no body."
          },
          "400": {
            "description": "The tag is assigned to one or more projects.",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"messages\": [\n    \"This tag cannot be deleted because it is assigned to one or more projects.\"\n  ],\n  \"success\": false\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "messages": {
                      "type": "array",
                      "items": {
                        "type": "string",
                        "example": "This tag cannot be deleted because it is assigned to one or more projects."
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