---
updatedAt: 2025-05-29T17:02:10.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Workplace Users

Get all users of a workplace

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
    "/v3/workplace/users": {
      "get": {
        "summary": "Workplace Users",
        "description": "Get all users of a workplace",
        "operationId": "audit-list_users",
        "parameters": [
          {
            "name": "settings",
            "in": "query",
            "description": "If true, the api will return more information if users have e.g. SAML enabled and/or Multi Factor Auth enabled",
            "schema": {
              "type": "boolean",
              "default": false
            }
          },
          {
            "name": "page",
            "in": "query",
            "description": "The page of users to fetch",
            "schema": {
              "type": "integer",
              "format": "int32",
              "default": 1
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
                    "value": "{\n  \"workplace_users\": [\n    {\n      \"id\": \"45786c9a-8c97-4f5b-a35b-ce941796502b\",\n      \"access\": \"owner\",\n      \"created_at\": \"2020-09-01T23:57:27.052Z\",\n      \"user\": {\n        \"email\": \"test@example.com\",\n        \"name\": \"Adam Smith\",\n        \"username\": \"adam_smith\",\n        \"profile_image_url\": \"https://www.gravatar.com/avatar/12345678?s=500&d=retro\",\n        \"mfa_enabled\": false,\n        \"thirdparty_sso_enabled\": true,\n        \"saml_sso_enabled\": false\n      }\n    }\n  ],\n  \"page\": 1,\n  \"success\": true\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "workplace_users": {
                      "type": "array",
                      "items": {
                        "type": "object",
                        "properties": {
                          "id": {
                            "type": "string",
                            "example": "45786c9a-8c97-4f5b-a35b-ce941796502b"
                          },
                          "access": {
                            "type": "string",
                            "example": "owner"
                          },
                          "created_at": {
                            "type": "string",
                            "example": "2020-09-01T23:57:27.052Z"
                          },
                          "user": {
                            "type": "object",
                            "properties": {
                              "email": {
                                "type": "string",
                                "example": "test@example.com"
                              },
                              "name": {
                                "type": "string",
                                "example": "Adam Smith"
                              },
                              "username": {
                                "type": "string",
                                "example": "adam_smith"
                              },
                              "profile_image_url": {
                                "type": "string",
                                "example": "https://www.gravatar.com/avatar/12345678?s=500&d=retro"
                              },
                              "mfa_enabled": {
                                "type": "boolean",
                                "example": false,
                                "default": true
                              },
                              "thirdparty_sso_enabled": {
                                "type": "boolean",
                                "example": true,
                                "default": true
                              },
                              "saml_sso_enabled": {
                                "type": "boolean",
                                "example": false,
                                "default": true
                              }
                            }
                          }
                        }
                      }
                    },
                    "page": {
                      "type": "integer",
                      "example": 1,
                      "default": 0
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