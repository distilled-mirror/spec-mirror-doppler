---
updatedAt: 2025-05-29T17:01:09.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Retrieve

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
    "/v3/workplace/users/{slug}": {
      "get": {
        "summary": "Retrieve",
        "description": "Get a specific user in a workplace",
        "operationId": "users-get",
        "parameters": [
          {
            "name": "slug",
            "in": "path",
            "description": "The slug of the workplace user",
            "schema": {
              "type": "string"
            },
            "required": true
          }
        ],
        "responses": {
          "200": {
            "description": "200",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"workplace_user\": {\n    \"id\": \"9629f890-eb33-426c-8694-28ce363b44f0\",\n    \"access\": \"owner\",\n    \"created_at\": \"2021-01-08T02:43:20.524Z\",\n    \"user\": {\n      \"email\": \"test@example.com\",\n      \"name\": \"John Appleseed\",\n      \"username\": \"john\",\n      \"profile_image_url\": \"\"\n    }\n  },\n  \"success\": true\n}"
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
                              "example": "test@example.com"
                            },
                            "name": {
                              "type": "string",
                              "example": "John Appleseed"
                            },
                            "username": {
                              "type": "string",
                              "example": "john"
                            },
                            "profile_image_url": {
                              "type": "string",
                              "example": ""
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