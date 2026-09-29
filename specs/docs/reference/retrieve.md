---
updatedAt: 2025-10-01T15:30:10.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Retrieve

Get a specific identity

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
    "/v3/workplace/service_accounts/service_account/{service_account}/identities/identity/{identity}": {
      "get": {
        "description": "",
        "operationId": "get_v3workplaceservice_accountsservice_account{service_account}identitiesidentity{identity}",
        "responses": {
          "200": {
            "description": "",
            "content": {
              "application/json": {
                "schema": {
                  "type": "object",
                  "properties": {
                    "identity": {
                      "type": "object",
                      "properties": {
                        "slug": {
                          "type": "string"
                        },
                        "name": {
                          "type": "string"
                        },
                        "method": {
                          "type": "string",
                          "enum": [
                            "oidc"
                          ]
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
                                "exact",
                                "wildcard"
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
                          "format": "int32"
                        },
                        "created_at": {
                          "type": "string"
                        },
                        "last_seen_at": {
                          "type": "string"
                        }
                      }
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
            "in": "path",
            "name": "identity",
            "schema": {
              "type": "string"
            },
            "required": true
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