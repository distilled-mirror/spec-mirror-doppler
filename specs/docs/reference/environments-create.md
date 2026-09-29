---
updatedAt: 2025-05-29T17:01:26.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Create

Environment

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
    "/v3/environments": {
      "post": {
        "summary": "Create",
        "description": "Environment",
        "operationId": "environments-create",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "description": "The project's name",
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
                  "name",
                  "slug"
                ],
                "properties": {
                  "name": {
                    "type": "string"
                  },
                  "slug": {
                    "type": "string"
                  },
                  "personal_configs": {
                    "type": "boolean",
                    "description": "Whether or not to enable personal configs for the environment",
                    "default": false
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
                    "value": "{\n  \"environment\": {\n    \"id\": \"dev\",\n    \"name\": \"Development\",\n    \"initial_fetch_at\": \"2019-11-21T03:45:47.982Z\",\n    \"created_at\": \"2019-11-19T07:19:00.476Z\",\n    \"project\": \"ed0c2a68b6\"\n  }\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "environment": {
                      "type": "object",
                      "properties": {
                        "id": {
                          "type": "string",
                          "example": "dev"
                        },
                        "name": {
                          "type": "string",
                          "example": "Development"
                        },
                        "initial_fetch_at": {
                          "type": "string",
                          "example": "2019-11-21T03:45:47.982Z"
                        },
                        "created_at": {
                          "type": "string",
                          "example": "2019-11-19T07:19:00.476Z"
                        },
                        "project": {
                          "type": "string",
                          "example": "ed0c2a68b6"
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