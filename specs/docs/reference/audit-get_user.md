---
updatedAt: 2025-05-29T17:02:10.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Workplace User

Get a specific user in a workplace

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
    "/v3/workplace/users/{workplace_user_id}": {
      "get": {
        "summary": "Workplace User",
        "description": "Get a specific user in a workplace",
        "operationId": "audit-get_user",
        "parameters": [
          {
            "name": "workplace_user_id",
            "in": "path",
            "description": "The ID of the workplace user",
            "schema": {
              "type": "string"
            },
            "required": true
          },
          {
            "name": "settings",
            "in": "query",
            "description": "If true, the api will return more information if the user has e.g. SAML enabled and/or Multi Factor Auth enabled",
            "schema": {
              "type": "boolean"
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
                    "value": "{\n  \"workplace_user\": {\n    \"id\": \"9629f890-eb33-426c-8694-28ce363b44f0\",\n    \"access\": \"owner\",\n    \"created_at\": \"2021-01-08T02:43:20.524Z\",\n    \"user\": {\n      \"email\": \"ruud.visser@doppler.com\",\n      \"name\": \"Ruud Visser\",\n      \"username\": \"ruud\",\n      \"profile_image_url\": \"https://lh3.googleusercontent.com/a-/AOh14Ggx8--xAHCMfmrNwV3hVGWrwSicyaALmjvu5of1=s96-c\",\n      \"mfa_enabled\": false,\n      \"thirdparty_sso_enabled\": true,\n      \"saml_sso_enabled\": false\n    }\n  },\n  \"success\": true\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "workplace_user": {
                      "type": "object",
                      "properties": {
                        "id": {
                          "type": "string",
                          "example": "9629f890-eb33-426c-8694-28ce363b44f0"
                        },
                        "access": {
                          "type": "string",
                          "example": "owner"
                        },
                        "created_at": {
                          "type": "string",
                          "example": "2021-01-08T02:43:20.524Z"
                        },
                        "user": {
                          "type": "object",
                          "properties": {
                            "email": {
                              "type": "string",
                              "example": "ruud.visser@doppler.com"
                            },
                            "name": {
                              "type": "string",
                              "example": "Ruud Visser"
                            },
                            "username": {
                              "type": "string",
                              "example": "ruud"
                            },
                            "profile_image_url": {
                              "type": "string",
                              "example": "https://lh3.googleusercontent.com/a-/AOh14Ggx8--xAHCMfmrNwV3hVGWrwSicyaALmjvu5of1=s96-c"
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