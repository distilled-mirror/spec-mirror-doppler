---
updatedAt: 2025-05-29T17:01:52.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Issue Lease

Issue a lease for a dynamic secret

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
    "/v3/configs/config/dynamic_secrets/dynamic_secret/leases": {
      "post": {
        "summary": "Issue Lease",
        "description": "Issue a lease for a dynamic secret",
        "operationId": "dynamic_secrets-issue_lease",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "project",
                  "config",
                  "dynamic_secret",
                  "ttl_sec"
                ],
                "properties": {
                  "project": {
                    "type": "string",
                    "description": "The project where the dynamic secret is located"
                  },
                  "config": {
                    "type": "string",
                    "description": "The config where the dynamic secret is located"
                  },
                  "dynamic_secret": {
                    "type": "string",
                    "description": "The name of the dynamic secret for which to issue this lease"
                  },
                  "ttl_sec": {
                    "type": "integer",
                    "description": "The number of seconds until this lease is automatically revoked",
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
                    "value": "{\n    \"success\": true,\n    \"id\": \"59ed03c9-63a7-4789-9187-a3d858355353\",\n    \"expires_at\": \"2022-02-18T20:36:28.427Z\",\n    \"value\": {  }\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "success": {
                      "type": "boolean",
                      "example": true,
                      "default": true
                    },
                    "id": {
                      "type": "string",
                      "example": "59ed03c9-63a7-4789-9187-a3d858355353"
                    },
                    "expires_at": {
                      "type": "string",
                      "example": "2022-02-18T20:36:28.427Z"
                    },
                    "value": {
                      "type": "object",
                      "properties": {}
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