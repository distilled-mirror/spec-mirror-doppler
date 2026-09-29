---
updatedAt: 2025-05-29T17:01:33.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# List

Config Logs

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
    "/v3/configs/config/logs": {
      "get": {
        "summary": "List",
        "description": "Config Logs",
        "operationId": "config_logs-list",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "description": "Unique identifier for the project object.",
            "required": true,
            "schema": {
              "type": "string",
              "default": "PROJECT_NAME"
            }
          },
          {
            "name": "config",
            "in": "query",
            "description": "Name of the config object.",
            "required": true,
            "schema": {
              "type": "string",
              "default": "CONFIG_NAME"
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
                    "value": "{\n  \"page\": 1,\n  \"logs\": [\n    {\n      \"id\": \"WaRMMyxHUg4lOKR\",\n      \"text\": \"Defaults were updated which resulted in this config's secrets being modified\",\n      \"html\": \"Defaults were updated which resulted in this config's secrets being modified\",\n      \"rollback\": false,\n      \"created_at\": \"2019-11-19T07:19:01.073Z\",\n      \"config\": \"dev\",\n      \"environment\": \"dev\",\n      \"project\": \"ed0c2a68b6t\",\n      \"user\": {\n        \"email\": \"jake@piedpiper.com\",\n        \"name\": \"Jake Sun\",\n        \"username\": \"jake\",\n        \"profile_image_url\": \"https://www.gravatar.com/avatar/84da5be2b398382c676bfca6b38dae41?s=500&d=retro\"\n      }\n    }\n  ]\n}"
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
                    "logs": {
                      "type": "array",
                      "items": {
                        "type": "object",
                        "properties": {
                          "id": {
                            "type": "string",
                            "example": "WaRMMyxHUg4lOKR"
                          },
                          "text": {
                            "type": "string",
                            "example": "Defaults were updated which resulted in this config's secrets being modified"
                          },
                          "html": {
                            "type": "string",
                            "example": "Defaults were updated which resulted in this config's secrets being modified"
                          },
                          "rollback": {
                            "type": "boolean",
                            "example": false,
                            "default": true
                          },
                          "created_at": {
                            "type": "string",
                            "example": "2019-11-19T07:19:01.073Z"
                          },
                          "config": {
                            "type": "string",
                            "example": "dev"
                          },
                          "environment": {
                            "type": "string",
                            "example": "dev"
                          },
                          "project": {
                            "type": "string",
                            "example": "ed0c2a68b6t"
                          },
                          "user": {
                            "type": "object",
                            "properties": {
                              "email": {
                                "type": "string",
                                "example": "jake@piedpiper.com"
                              },
                              "name": {
                                "type": "string",
                                "example": "Jake Sun"
                              },
                              "username": {
                                "type": "string",
                                "example": "jake"
                              },
                              "profile_image_url": {
                                "type": "string",
                                "example": "https://www.gravatar.com/avatar/84da5be2b398382c676bfca6b38dae41?s=500&d=retro"
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