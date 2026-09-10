---
updatedAt: 2025-05-29T17:01:32.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Inherits

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
    "/v3/configs/config/inherits": {
      "post": {
        "summary": "Inherits",
        "description": "",
        "operationId": "configs-inherits",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "project",
                  "config",
                  "inherits"
                ],
                "properties": {
                  "project": {
                    "type": "string",
                    "description": "Unique identifier for the project object of the config doing the inheriting.",
                    "default": "PROJECT_NAME"
                  },
                  "config": {
                    "type": "string",
                    "description": "Name of the config object doing the inheriting.",
                    "default": "CONFIG_NAME"
                  },
                  "inherits": {
                    "type": "array",
                    "description": "Array of objects indicating which configs are being inherited.",
                    "items": {
                      "properties": {
                        "project": {
                          "type": "string",
                          "description": "Unique identifier for the project object of the config being inherited.",
                          "default": "PROJECT_NAME"
                        },
                        "config": {
                          "type": "string",
                          "description": "Name of the config object being inherited.",
                          "default": "CONFIG_NAME"
                        }
                      },
                      "required": [
                        "project",
                        "config"
                      ],
                      "type": "object"
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
                    "value": "{\n  \"config\": {\n    \"name\": \"prd_gcp\",\n    \"root\": false,\n    \"inheritable\": false,\n    \"inheriting\": true,\n    \"inherits\": [\n      {\n        \"project\": \"project1\",\n        \"config\": \"dev\"\n      },\n      {\n        \"project\": \"project2\",\n        \"config\": \"dev\"\n      }\n    ],\n    \"inheritedBy\": [],\n    \"locked\": false,\n    \"initial_fetch_at\": \"2022-03-04T17:09:41.098Z\",\n    \"last_fetch_at\": \"2024-12-06T16:57:34.288Z\",\n    \"created_at\": \"2022-02-02T22:33:34.200Z\",\n    \"environment\": \"prd\",\n    \"project\": \"ed0c2a68b6\",\n    \"slug\": \"541bfc63-5c7f-4f68-88f7-ea1105dac98f\"\n  },\n  \"success\": true\n}"
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
                          "example": false,
                          "default": true
                        },
                        "inheriting": {
                          "type": "boolean",
                          "example": true,
                          "default": true
                        },
                        "inherits": {
                          "type": "array",
                          "items": {
                            "type": "object",
                            "properties": {
                              "project": {
                                "type": "string",
                                "example": "project1"
                              },
                              "config": {
                                "type": "string",
                                "example": "dev"
                              }
                            }
                          }
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