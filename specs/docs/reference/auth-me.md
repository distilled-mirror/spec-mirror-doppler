---
updatedAt: 2025-05-29T17:02:07.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Me

Get information about a token

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
    "/v3/me": {
      "get": {
        "summary": "Me",
        "description": "Get information about a token",
        "operationId": "auth-me",
        "responses": {
          "200": {
            "description": "200",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"slug\": \"5ba6e0fd-a80a-4c39-9e85-3d5230d44e62\",\n  \"name\": \"Doppler-Test\",\n  \"created_at\": \"2023-06-15T20:17:33.539Z\",\n  \"last_seen_at\": \"2023-06-16T17:09:16.079Z\",\n  \"type\": \"cli\",\n  \"token_preview\": \"dp.ct...b8aked\",\n  \"workplace\": {\n    \"slug\": \"2faa85f6610102d983522\",\n    \"name\": \"Doppler University\"\n  }\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "slug": {
                      "type": "string",
                      "example": "5ba6e0fd-a80a-4c39-9e85-3d5230d44e62"
                    },
                    "name": {
                      "type": "string",
                      "example": "Doppler-Test"
                    },
                    "created_at": {
                      "type": "string",
                      "example": "2023-06-15T20:17:33.539Z"
                    },
                    "last_seen_at": {
                      "type": "string",
                      "example": "2023-06-16T17:09:16.079Z"
                    },
                    "type": {
                      "type": "string",
                      "example": "cli"
                    },
                    "token_preview": {
                      "type": "string",
                      "example": "dp.ct...b8aked"
                    },
                    "workplace": {
                      "type": "object",
                      "properties": {
                        "slug": {
                          "type": "string",
                          "example": "2faa85f6610102d983522"
                        },
                        "name": {
                          "type": "string",
                          "example": "Doppler University"
                        }
                      }
                    },
                    "principal": {
                      "type": "object",
                      "properties": {
                        "type": {
                          "type": "string"
                        },
                        "slug": {
                          "type": "string"
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