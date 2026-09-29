---
updatedAt: 2025-05-29T17:01:52.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Revoke Lease

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
    "/v3/configs/config/dynamic_secrets/dynamic_secret/leases/lease": {
      "delete": {
        "summary": "Revoke Lease",
        "description": "",
        "operationId": "dynamic_secrets-revoke_lease",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "project",
                  "config",
                  "dynamic_secret",
                  "slug"
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
                    "description": "The name of the dynamic secret from which this lease was issued"
                  },
                  "slug": {
                    "type": "string",
                    "description": "The slug of the lease to revoke"
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
                    "value": "{ \"success\": true }"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
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