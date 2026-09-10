---
updatedAt: 2025-05-29T17:01:28.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# List

Fetch all configs.

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
    "/v3/configs": {
      "get": {
        "summary": "List",
        "description": "Fetch all configs.",
        "operationId": "configs-list",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "description": "The project's name",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "environment",
            "in": "query",
            "description": "(optional) the environment from which to list configs",
            "schema": {
              "type": "string",
              "default": "Environment slug"
            }
          },
          {
            "name": "page",
            "in": "query",
            "description": "Page number",
            "schema": {
              "type": "integer",
              "format": "int32",
              "default": 1
            }
          },
          {
            "name": "per_page",
            "in": "query",
            "description": "Items per page",
            "schema": {
              "type": "integer",
              "format": "int32",
              "default": 20
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
                    "value": "{\n  \"page\": 1,\n  \"configs\": [\n    {\n      \"name\": \"dev\",\n      \"root\": true,\n      \"locked\": true,\n      \"initial_fetch_at\": \"2019-11-19T07:36:12.000Z\",\n      \"last_fetch_at\": \"2019-11-19T07:32:10.980Z\",\n      \"created_at\": \"2019-11-19T07:19:00.480Z\",\n      \"environment\": \"dev\",\n      \"project\": \"ed0c2a68b6\"\n    },\n    {\n      \"name\": \"stg\",\n      \"root\": true,\n      \"locked\": true,\n      \"initial_fetch_at\": null,\n      \"last_fetch_at\": null,\n      \"created_at\": \"2019-11-19T07:19:00.488Z\",\n      \"environment\": \"stg\",\n      \"project\": \"ed0c2a68b6\"\n    },\n    {\n      \"name\": \"prd\",\n      \"root\": true,\n      \"locked\": true,\n      \"initial_fetch_at\": null,\n      \"last_fetch_at\": null,\n      \"created_at\": \"2019-11-19T07:19:00.495Z\",\n      \"environment\": \"prd\",\n      \"project\": \"ed0c2a68b6\"\n    }\n  ]\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "page": {
                      "type": "integer",
                      "example": 1,
                      "default": 0
                    },
                    "configs": {
                      "type": "array",
                      "items": {
                        "type": "object",
                        "properties": {
                          "name": {
                            "type": "string",
                            "example": "dev"
                          },
                          "root": {
                            "type": "boolean",
                            "example": true,
                            "default": true
                          },
                          "locked": {
                            "type": "boolean",
                            "example": true,
                            "default": true
                          },
                          "initial_fetch_at": {
                            "type": "string",
                            "example": "2019-11-19T07:36:12.000Z"
                          },
                          "last_fetch_at": {
                            "type": "string",
                            "example": "2019-11-19T07:32:10.980Z"
                          },
                          "created_at": {
                            "type": "string",
                            "example": "2019-11-19T07:19:00.480Z"
                          },
                          "environment": {
                            "type": "string",
                            "example": "dev"
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