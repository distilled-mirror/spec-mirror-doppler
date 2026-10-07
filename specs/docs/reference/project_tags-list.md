---
updatedAt: 2026-10-06T02:23:00.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# List

List the tags assigned to a project, sorted by name. Anyone who can view the project can list its tags.

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
    "/v3/projects/project/tags": {
      "get": {
        "summary": "List",
        "operationId": "project_tags-list",
        "deprecated": false,
        "description": "List the tags assigned to a project, sorted by name. Anyone who can view the project can list its tags.",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "required": true,
            "description": "The project's slug.",
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "The project's tags.",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"tags\": [\n    {\n      \"slug\": \"backend\",\n      \"name\": \"Backend\",\n      \"color\": \"blue\",\n      \"created_at\": \"2026-10-05T19:04:21.930Z\"\n    },\n    {\n      \"slug\": \"pci\",\n      \"name\": \"PCI\",\n      \"color\": \"red\",\n      \"created_at\": \"2026-10-05T19:04:22.118Z\"\n    }\n  ]\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "tags": {
                      "type": "array",
                      "items": {
                        "type": "object",
                        "properties": {
                          "slug": {
                            "type": "string",
                            "description": "The tag's unique identifier. Use it to refer to the tag in other API calls. Can't be changed.",
                            "example": "pci"
                          },
                          "name": {
                            "type": "string",
                            "description": "The tag's display name.",
                            "example": "PCI"
                          },
                          "color": {
                            "type": "string",
                            "enum": [
                              "gray",
                              "purple",
                              "blue",
                              "green",
                              "yellow",
                              "orange",
                              "red",
                              "pink"
                            ],
                            "description": "The tag's color.",
                            "example": "red"
                          },
                          "created_at": {
                            "type": "string",
                            "description": "Date and time the tag was created.",
                            "example": "2026-10-05T19:04:22.118Z"
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