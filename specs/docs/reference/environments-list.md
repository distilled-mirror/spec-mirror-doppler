---
updatedAt: 2025-05-29T17:01:26.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# List

Environments

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
      "get": {
        "summary": "List",
        "description": "Environments",
        "operationId": "environments-list",
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
        "responses": {
          "200": {
            "description": "200",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"environments\": [\n    {\n      \"id\": \"dev\",\n      \"name\": \"Development\",\n      \"initial_fetch_at\": \"2019-11-21T03:45:47.982Z\",\n      \"created_at\": \"2019-11-19T07:19:00.476Z\",\n      \"project\": \"ed0c2a68b6\"\n    },\n    {\n      \"id\": \"stg\",\n      \"name\": \"Staging\",\n      \"initial_fetch_at\": null,\n      \"created_at\": \"2019-11-19T07:19:00.484Z\",\n      \"project\": \"ed0c2a68b6\"\n    },\n    {\n      \"id\": \"prd\",\n      \"name\": \"Production\",\n      \"initial_fetch_at\": null,\n      \"created_at\": \"2019-11-19T07:19:00.492Z\",\n      \"project\": \"ed0c2a68b6\"\n    }\n  ],\n  \"page\": 1\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "environments": {
                      "type": "array",
                      "items": {
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
                    },
                    "page": {
                      "type": "integer",
                      "example": 1,
                      "default": 0
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