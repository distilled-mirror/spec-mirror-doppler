---
updatedAt: 2025-05-29T17:02:07.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# OIDC (Service Account Identity)

Authenticate via a Service Account Identity with OIDC. Returns a short lived API token.

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
    "/v3/auth/oidc": {
      "post": {
        "summary": "OIDC (Service Account Identity)",
        "description": "Authenticate via a Service Account Identity with OIDC. Returns a short lived API token.",
        "operationId": "auth-oidc",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "token",
                  "identity"
                ],
                "properties": {
                  "token": {
                    "type": "string",
                    "description": "the OIDC token string from your OIDC provider (likely CI)"
                  },
                  "identity": {
                    "type": "string",
                    "description": "Identity ID from the Doppler Dashboard"
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
                    "value": "{\n  \"token\": \"dp.said.bAqhcVzrhy5cRHkOlNTc0Ve6w5NUDCpcutm8vGE9myi\",\n  \"expires_at\": \"2025-01-17T16:46:46.171Z\"\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "token": {
                      "type": "string",
                      "example": "dp.said.bAqhcVzrhy5cRHkOlNTc0Ve6w5NUDCpcutm8vGE9myi"
                    },
                    "expires_at": {
                      "type": "string",
                      "example": "2025-01-17T16:46:46.171Z"
                    }
                  }
                }
              }
            }
          }
        },
        "deprecated": false,
        "security": []
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