---
updatedAt: 2025-05-29T17:01:20.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Update

Project

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
    "/v3/projects/project": {
      "post": {
        "summary": "Update",
        "description": "Project",
        "operationId": "projects-update",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "project",
                  "name"
                ],
                "properties": {
                  "project": {
                    "type": "string",
                    "description": "Unique identifier for the project object.",
                    "default": "PROJECT_NAME"
                  },
                  "name": {
                    "type": "string",
                    "description": "Name of the project.",
                    "default": "PROJECT_NEW_NAME"
                  },
                  "description": {
                    "type": "string",
                    "description": "Description of the project.",
                    "default": "PROJECT_DESCRIPTION"
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
                    "value": "{\n  \"project\": {\n    \"id\": \"ed0c2a68b6\",\n    \"name\": \"Compression\",\n    \"description\": \"Super rad middle-out compression algo.\",\n    \"created_at\": \"2019-03-26T03:16:20.233Z\"\n  }\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "project": {
                      "type": "object",
                      "properties": {
                        "id": {
                          "type": "string",
                          "example": "ed0c2a68b6"
                        },
                        "name": {
                          "type": "string",
                          "example": "Compression"
                        },
                        "description": {
                          "type": "string",
                          "example": "Super rad middle-out compression algo."
                        },
                        "created_at": {
                          "type": "string",
                          "example": "2019-03-26T03:16:20.233Z"
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