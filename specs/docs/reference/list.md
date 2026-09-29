---
updatedAt: 2025-10-01T14:53:41.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# List

List all identities for a service account

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
    "/v3/workplace/service_accounts/service_account/{service_account}/identities": {
      "get": {
        "description": "",
        "operationId": "get_v3workplaceservice_accountsservice_account{service_account}identities",
        "responses": {
          "200": {
            "description": "",
            "content": {
              "application/json": {
                "schema": {
                  "type": "object",
                  "properties": {
                    "identities": {
                      "type": "array",
                      "items": {
                        "properties": {
                          "slug": {
                            "type": "string"
                          },
                          "name": {
                            "type": "string"
                          },
                          "method": {
                            "type": "string"
                          },
                          "config": {
                            "type": "object",
                            "properties": {
                              "discovery_url": {
                                "type": "string"
                              },
                              "claims_type": {
                                "type": "string",
                                "enum": [
                                  "wildcard",
                                  "exact"
                                ]
                              },
                              "claims": {
                                "type": "object",
                                "properties": {
                                  "aud": {
                                    "type": "array",
                                    "items": {
                                      "type": "string"
                                    }
                                  },
                                  "sub": {
                                    "type": "array",
                                    "items": {
                                      "type": "string"
                                    }
                                  }
                                }
                              }
                            }
                          },
                          "ttl_seconds": {
                            "type": "integer",
                            "format": "int32",
                            "default": ""
                          },
                          "created_at": {
                            "type": "string"
                          },
                          "last_seen_at": {
                            "type": "string"
                          }
                        },
                        "type": "object"
                      }
                    },
                    "success": {
                      "type": "boolean",
                      "default": "true"
                    }
                  }
                }
              }
            }
          }
        },
        "parameters": [
          {
            "in": "path",
            "name": "service_account",
            "schema": {
              "type": "string"
            },
            "required": true
          },
          {
            "in": "query",
            "name": "page",
            "schema": {
              "type": "integer",
              "default": "1",
              "format": "int32"
            },
            "required": false
          },
          {
            "in": "query",
            "name": "per_page",
            "schema": {
              "type": "integer",
              "default": "20",
              "format": "int32"
            },
            "required": false
          }
        ]
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