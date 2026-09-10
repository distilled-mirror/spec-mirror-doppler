---
updatedAt: 2025-05-29T17:01:31.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Inheritable

Update the inheritability of a config.

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
    "/v3/configs/config/inheritable": {
      "post": {
        "summary": "Inheritable",
        "description": "Update the inheritability of a config.",
        "operationId": "configs-inheritable",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "project",
                  "config",
                  "inheritable"
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
                  },
                  "inheritable": {
                    "type": "boolean",
                    "description": "Boolean determining if the config is inheritable or not.",
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
                    "value": "{\n  \"config\": {\n    \"name\": \"prd_gcp\",\n    \"root\": false,\n    \"inheritable\": true,\n    \"inheriting\": false,\n    \"inherits\": [],\n    \"inheritedBy\": [],\n    \"locked\": false,\n    \"initial_fetch_at\": \"2022-03-04T17:09:41.098Z\",\n    \"last_fetch_at\": \"2024-12-06T16:57:34.288Z\",\n    \"created_at\": \"2022-02-02T22:33:34.200Z\",\n    \"environment\": \"prd\",\n    \"project\": \"ed0c2a68b6\",\n    \"slug\": \"541bfc63-5c7f-4f68-88f7-ea1105dac98f\"\n  },\n  \"success\": true\n}"
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
                          "example": "prd_gcp"
                        },
                        "root": {
                          "type": "boolean",
                          "example": false,
                          "default": true
                        },
                        "inheritable": {
                          "type": "boolean",
                          "example": true,
                          "default": true
                        },
                        "inheriting": {
                          "type": "boolean",
                          "example": false,
                          "default": true
                        },
                        "inherits": {
                          "type": "array"
                        },
                        "inheritedBy": {
                          "type": "array"
                        },
                        "locked": {
                          "type": "boolean",
                          "example": false,
                          "default": true
                        },
                        "initial_fetch_at": {
                          "type": "string",
                          "example": "2022-03-04T17:09:41.098Z"
                        },
                        "last_fetch_at": {
                          "type": "string",
                          "example": "2024-12-06T16:57:34.288Z"
                        },
                        "created_at": {
                          "type": "string",
                          "example": "2022-02-02T22:33:34.200Z"
                        },
                        "environment": {
                          "type": "string",
                          "example": "prd"
                        },
                        "project": {
                          "type": "string",
                          "example": "ed0c2a68b6"
                        },
                        "slug": {
                          "type": "string",
                          "example": "541bfc63-5c7f-4f68-88f7-ea1105dac98f"
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