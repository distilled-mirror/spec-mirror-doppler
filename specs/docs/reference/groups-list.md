---
updatedAt: 2025-05-29T17:01:55.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# List

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
    "/v3/workplace/groups": {
      "get": {
        "summary": "List",
        "description": "",
        "operationId": "groups-list",
        "parameters": [
          {
            "name": "page",
            "in": "query",
            "schema": {
              "type": "integer",
              "format": "int32",
              "default": 1
            }
          },
          {
            "name": "per_page",
            "in": "query",
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
                    "value": "{\n  \"groups\": [{\n    \"name\": \"group\",\n    \"slug\": \"00000000-0000-0000-0000-000000000000\",\n    \"created_at\": \"2023-08-01T00:00:00.000Z\",\n    \"default_project_role\": {\n      \"identifier\": \"no_access\"\n    }\n  }]\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "groups": {
                      "type": "array",
                      "items": {
                        "type": "object",
                        "properties": {
                          "name": {
                            "type": "string",
                            "example": "group"
                          },
                          "slug": {
                            "type": "string",
                            "example": "00000000-0000-0000-0000-000000000000"
                          },
                          "created_at": {
                            "type": "string",
                            "example": "2023-08-01T00:00:00.000Z"
                          },
                          "default_project_role": {
                            "type": "object",
                            "properties": {
                              "identifier": {
                                "type": "string",
                                "example": "no_access"
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