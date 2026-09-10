---
updatedAt: 2025-05-29T17:02:10.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Workplace

Get information about the workplace

# OpenAPI definition

```json
{
  "openapi": "3.1.0",
  "info": {
    "title": "audit-api",
    "version": "4"
  },
  "servers": [
    {
      "url": "https://api.doppler.com"
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
      "get": {
        "summary": "Workplace",
        "description": "Get information about the workplace",
        "operationId": "audit-get_workplace",
        "parameters": [
          {
            "name": "settings",
            "in": "query",
            "description": "Return more information about workplace configuration, including whether SAML and SCIM are enabled.",
            "schema": {
              "type": "boolean",
              "default": false
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
                    "value": "{\n  \"workplace\": {\n    \"id\": \"188f5\",\n    \"name\": \"Test Workplace\",\n    \"billing_email\": \"billing@test.com\",\n    \"saml_enabled\": false,\n    \"scim_enabled\": false\n  },\n  \"success\": true\n}"
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
                          "example": "billing@test.com"
                        },
                        "saml_enabled": {
                          "type": "boolean",
                          "example": false,
                          "default": true
                        },
                        "scim_enabled": {
                          "type": "boolean",
                          "example": false,
                          "default": true
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