---
updatedAt: 2025-05-29T17:01:07.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Update

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
    "/v3/workplace": {
      "post": {
        "summary": "Update",
        "description": "",
        "operationId": "workplace-update",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "name": {
                    "type": "string",
                    "description": "Workplace name"
                  },
                  "billing_email": {
                    "type": "string"
                  },
                  "security_email": {
                    "type": "string"
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
                    "value": "{\n  \"workplace\": {\n    \"id\": \"188f5\",\n    \"name\": \"Test Workplace\",\n    \"billing_email\": \"billing@example.com\",\n    \"security_email\": \"security@example.com\"\n  }\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "workplace": {
                      "type": "object",
                      "properties": {
                        "id": {
                          "type": "string",
                          "example": "188f5"
                        },
                        "name": {
                          "type": "string",
                          "example": "Test Workplace"
                        },
                        "billing_email": {
                          "type": "string",
                          "example": "billing@example.com"
                        },
                        "security_email": {
                          "type": "string",
                          "example": "security@example.com"
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