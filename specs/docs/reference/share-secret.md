---
updatedAt: 2025-05-29T17:02:07.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Plain Text

Generate a Doppler Share link by sending a plain text secret. This endpoint is not end-to-end encrypted as you are sending the secret in plain text. At no point do we store the plain text secret or the password in our systems. The receive flow the user goes through will be end-to-end encrypted where the encrypted secret will be decrypted on the browser.

# OpenAPI definition

```json
{
  "openapi": "3.1.0",
  "info": {
    "title": "share",
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
        "type": "http",
        "scheme": "basic"
      }
    }
  },
  "security": [
    {
      "sec0": []
    }
  ],
  "paths": {
    "/v1/share/secrets/plain": {
      "post": {
        "summary": "Plain Text",
        "description": "Generate a Doppler Share link by sending a plain text secret. This endpoint is not end-to-end encrypted as you are sending the secret in plain text. At no point do we store the plain text secret or the password in our systems. The receive flow the user goes through will be end-to-end encrypted where the encrypted secret will be decrypted on the browser.",
        "operationId": "share-secret",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "secret"
                ],
                "properties": {
                  "secret": {
                    "type": "string",
                    "description": "Plain text secret to share.",
                    "default": "TEST SECRET"
                  },
                  "expire_views": {
                    "type": "integer",
                    "description": "Number of views before the link expires. Valid ranges: 1 to 50. -1 for unlimited.",
                    "default": 1,
                    "format": "int32"
                  },
                  "expire_days": {
                    "type": "integer",
                    "description": "Number of days before the link expires. Valid range: 1 to 90.",
                    "default": 1,
                    "format": "int32"
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
                    "value": "{\n  \"url\": \"https://share.doppler.com/s/oarjigpajqtodoqefoua9o1iisdfaocgfbulmaez\",\n  \"authenticated_url\": \"https://share.doppler.com/s/oarjigpajqtodoqefoua9o1iisdfaocgfbulmaez#GZPgKEngtasgXHftCjimCwjPquZV7qwwzo8qb1m7rgvjlWXFr8C5jHOuXtxW1SBC\",\n  \"password\": \"GZPgKEngtasgXHftCjimCwjPquZV7qwwzo8qb1m7rgvjlWXFr8C5jHOuXtxW1SBC\",\n  \"success\": true\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "url": {
                      "type": "string",
                      "example": "https://share.doppler.com/s/oarjigpajqtodoqefoua9o1iisdfaocgfbulmaez"
                    },
                    "authenticated_url": {
                      "type": "string",
                      "example": "https://share.doppler.com/s/oarjigpajqtodoqefoua9o1iisdfaocgfbulmaez#GZPgKEngtasgXHftCjimCwjPquZV7qwwzo8qb1m7rgvjlWXFr8C5jHOuXtxW1SBC"
                    },
                    "password": {
                      "type": "string",
                      "example": "GZPgKEngtasgXHftCjimCwjPquZV7qwwzo8qb1m7rgvjlWXFr8C5jHOuXtxW1SBC"
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