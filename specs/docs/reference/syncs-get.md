---
updatedAt: 2025-05-29T17:01:51.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Retrieve

Retrieve an existing secrets sync.

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
    "/v3/configs/config/syncs/sync": {
      "get": {
        "summary": "Retrieve",
        "description": "Retrieve an existing secrets sync.",
        "operationId": "syncs-get",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "description": "The project slug",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "config",
            "in": "query",
            "description": "The config slug",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "sync",
            "in": "query",
            "description": "The sync slug",
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
                    "value": "{\n\t\"sync\": {\n  \t\"slug\": \"00000000-0000-0000-0000-000000000000\",\n  \t\"integration\": \"00000000-0000-0000-0000-000000000000\",\n    \"project\": \"backend\",\n    \"config\": \"prd\",\n    \"enabled\": true,\n    \"lastSyncedAt\": \"2023-08-01T00:00:00.000Z\"\n  }\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "sync": {
                      "type": "object",
                      "properties": {
                        "slug": {
                          "type": "string",
                          "example": "00000000-0000-0000-0000-000000000000"
                        },
                        "integration": {
                          "type": "string",
                          "example": "00000000-0000-0000-0000-000000000000"
                        },
                        "project": {
                          "type": "string",
                          "example": "backend"
                        },
                        "config": {
                          "type": "string",
                          "example": "prd"
                        },
                        "enabled": {
                          "type": "boolean",
                          "example": true,
                          "default": true
                        },
                        "lastSyncedAt": {
                          "type": "string",
                          "example": "2023-08-01T00:00:00.000Z"
                        }
                      }
                    }
                  }
                }
              }
            }
          },
          "400": {
            "description": "400",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {}
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