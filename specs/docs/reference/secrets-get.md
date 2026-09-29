---
updatedAt: 2026-09-16T15:28:19.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Retrieve

Secret

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
    "/v3/configs/config/secret": {
      "get": {
        "summary": "Retrieve",
        "description": "Secret",
        "operationId": "secrets-get",
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
            "name": "name",
            "in": "query",
            "description": "Name of the secret.",
            "required": true,
            "schema": {
              "type": "string",
              "default": "SECRET_NAME"
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
                    "value": "{\n  \"name\": \"DATABASE\",\n  \"value\": {\n    \"raw\": \"${USER}@aws.dynamodb.com:9876\",\n    \"computed\": \"brian@aws.dynamodb.com:9876\",\n    \"note\": \"\"\n  }\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "name": {
                      "type": "string",
                      "example": "DATABASE"
                    },
                    "value": {
                      "type": "object",
                      "properties": {
                        "raw": {
                          "type": "string",
                          "example": "${USER}@aws.dynamodb.com:9876"
                        },
                        "computed": {
                          "type": "string",
                          "example": "brian@aws.dynamodb.com:9876"
                        },
                        "note": {
                          "type": "string",
                          "example": ""
                        },
                        "rawVisibility": {
                          "type": "string",
                          "enum": [
                            "unmasked",
                            "masked",
                            "restricted"
                          ]
                        },
                        "computedVisibility": {
                          "type": "string"
                        },
                        "rawValueType": {
                          "type": "object",
                          "properties": {
                            "type": {
                              "type": "string"
                            }
                          }
                        },
                        "computedValueType": {
                          "type": "object",
                          "properties": {
                            "type": {
                              "type": "string"
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