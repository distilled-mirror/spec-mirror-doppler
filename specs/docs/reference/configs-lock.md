---
updatedAt: 2025-05-29T17:01:31.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Lock

Prevent the config from being renamed or deleted.

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
    "/v3/configs/config/lock": {
      "post": {
        "summary": "Lock",
        "description": "Prevent the config from being renamed or deleted.",
        "operationId": "configs-lock",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "project",
                  "config"
                ],
                "properties": {
                  "project": {
                    "type": "string",
                    "description": "Unique identifier for the project object.",
                    "default": "PROJECT_NAME"
                  },
                  "config": {
                    "type": "string",
                    "description": "Name of the config.",
                    "default": "CONFIG_NAME"
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
                    "value": "{\n  \"config\": {\n    \"name\": \"prd_aws\",\n    \"root\": false,\n    \"locked\": true,\n    \"initial_fetch_at\": \"2019-11-19T07:32:12.000Z\",\n    \"last_fetch_at\": \"2019-11-19T07:36:10.980Z\",\n    \"created_at\": \"2019-11-19T07:19:00.480Z\",\n    \"environment\": \"prd\",\n    \"project\": \"ed0c2a68b6\"\n  }\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "config": {
                      "type": "object",
                      "properties": {
                        "name": {
                          "type": "string",
                          "example": "prd_aws"
                        },
                        "root": {
                          "type": "boolean",
                          "example": false,
                          "default": true
                        },
                        "locked": {
                          "type": "boolean",
                          "example": true,
                          "default": true
                        },
                        "initial_fetch_at": {
                          "type": "string",
                          "example": "2019-11-19T07:32:12.000Z"
                        },
                        "last_fetch_at": {
                          "type": "string",
                          "example": "2019-11-19T07:36:10.980Z"
                        },
                        "created_at": {
                          "type": "string",
                          "example": "2019-11-19T07:19:00.480Z"
                        },
                        "environment": {
                          "type": "string",
                          "example": "prd"
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