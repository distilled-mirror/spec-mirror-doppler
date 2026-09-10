---
updatedAt: 2025-05-29T17:01:08.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# List

Get all users within a workplace

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
    "/v3/workplace/users": {
      "get": {
        "summary": "List",
        "description": "Get all users within a workplace",
        "operationId": "users-list",
        "parameters": [
          {
            "name": "page",
            "in": "query",
            "description": "The page of users to fetch",
            "schema": {
              "type": "integer",
              "format": "int32",
              "default": 1
            }
          },
          {
            "name": "email",
            "in": "query",
            "description": "Filter results to only include the user with the provided email address",
            "schema": {
              "type": "string"
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
                    "value": "{\n  \"workplace_users\": [\n    {\n      \"id\": \"45786c9a-8c97-4f5b-a35b-ce941796502b\",\n      \"access\": \"owner\",\n      \"created_at\": \"2020-09-01T23:57:27.052Z\",\n      \"user\": {\n        \"email\": \"test@example.com\",\n        \"name\": \"John Appleseed\",\n        \"username\": \"john\",\n        \"profile_image_url\": \"\"\n      }\n    }\n  ],\n  \"page\": 1,\n  \"success\": true\n}"
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