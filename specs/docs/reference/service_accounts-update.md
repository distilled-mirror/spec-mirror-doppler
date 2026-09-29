---
updatedAt: 2025-05-29T17:01:59.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

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
    "/v3/workplace/service_accounts/service_account/{slug}": {
      "patch": {
        "summary": "Update",
        "description": "",
        "operationId": "service_accounts-update",
        "parameters": [
          {
            "name": "slug",
            "in": "path",
            "description": "Slug of the service account",
            "schema": {
              "type": "string"
            },
            "required": true
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "name": {
                    "type": "string"
                  },
                  "workplace_role": {
                    "type": "object",
                    "description": "You may provide an identifier OR permissions, but not both",
                    "properties": {
                      "identifier": {
                        "type": "string",
                        "description": "Identifier of an existing workplace role"
                      },
                      "permissions": {
                        "type": "array",
                        "description": "Workplace permissions to grant",
                        "items": {
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
        "responses": {
          "200": {
            "description": "200",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"service_account\": {\n    \"name\": \"sa\",\n    \"slug\": \"00000000-0000-0000-0000-000000000000\",\n    \"created_at\": \"2023-08-01T00:00:00.000Z\",\n    \"workplace_role\": {\n      \"name\": \"None\",\n      \"permissions\": [],\n      \"identifier\": \"no_access\",\n      \"created_at\": \"2023-08-01T00:00:00.000Z\",\n      \"is_custom_role\": false,\n      \"is_inline_role\": false\n    }\n  }\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "service_account": {
                      "type": "object",
                      "properties": {
                        "name": {
                          "type": "string",
                          "example": "sa"
                        },
                        "slug": {
                          "type": "string",
                          "example": "00000000-0000-0000-0000-000000000000"
                        },
                        "created_at": {
                          "type": "string",
                          "example": "2023-08-01T00:00:00.000Z"
                        },
                        "workplace_role": {
                          "type": "object",
                          "properties": {
                            "name": {
                              "type": "string",
                              "example": "None"
                            },
                            "permissions": {
                              "type": "array"
                            },
                            "identifier": {
                              "type": "string",
                              "example": "no_access"
                            },
                            "created_at": {
                              "type": "string",
                              "example": "2023-08-01T00:00:00.000Z"
                            },
                            "is_custom_role": {
                              "type": "boolean",
                              "example": false,
                              "default": true
                            },
                            "is_inline_role": {
                              "type": "boolean",
                              "example": false,
                              "default": true
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
          "404": {
            "description": "404",
            "content": {
              "text/plain": {
                "examples": {
                  "Result": {
                    "value": ""
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