---
updatedAt: 2025-05-29T17:01:54.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Create

Service Token

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
    "/v3/configs/config/tokens": {
      "post": {
        "summary": "Create",
        "description": "Service Token",
        "operationId": "service_tokens-create",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "project",
                  "config",
                  "name"
                ],
                "properties": {
                  "project": {
                    "type": "string",
                    "description": "Unique identifier for the project object.",
                    "default": "PROJECT_NAME"
                  },
                  "config": {
                    "type": "string",
                    "description": "Name of the config object.",
                    "default": "CONFIG_NAME"
                  },
                  "name": {
                    "type": "string",
                    "description": "Name of the service token.",
                    "default": "TOKEN_NAME"
                  },
                  "expire_at": {
                    "type": "string",
                    "description": "Unix timestamp of when token should expire.",
                    "format": "date-time"
                  },
                  "access": {
                    "type": "string",
                    "description": "Token's capabilities.",
                    "default": "read",
                    "enum": [
                      "read",
                      "read/write"
                    ]
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
                    "value": "{\n  \"token\": {\n    \"name\": \"AWS Lambda\",\n    \"slug\": \"56c69f96-3045-11ea-978f-2e728ce88125\",\n    \"created_at\": \"2019-11-19T07:19:01.073Z\",\n    \"key\": \"dp.st.gJ23agW5s09x4TKLMJMc4OPIr9fCm3bIs0QAC2L5\",\n    \"config\": \"dev\",\n    \"environment\": \"dev\",\n    \"project\": \"ed0c2a68b6t\",\n    \"expires_at\": null,\n    \"access\": \"read\"\n  }\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "token": {
                      "type": "object",
                      "properties": {
                        "name": {
                          "type": "string",
                          "example": "AWS Lambda"
                        },
                        "slug": {
                          "type": "string",
                          "example": "56c69f96-3045-11ea-978f-2e728ce88125"
                        },
                        "created_at": {
                          "type": "string",
                          "example": "2019-11-19T07:19:01.073Z"
                        },
                        "key": {
                          "type": "string",
                          "example": "dp.st.gJ23agW5s09x4TKLMJMc4OPIr9fCm3bIs0QAC2L5"
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
                        "expires_at": {},
                        "access": {
                          "type": "string",
                          "example": "read"
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