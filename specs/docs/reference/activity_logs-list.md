---
updatedAt: 2025-05-29T17:01:17.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# List

Activity Logs

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
    "/v3/logs": {
      "get": {
        "summary": "List",
        "description": "Activity Logs",
        "operationId": "activity_logs-list",
        "parameters": [
          {
            "name": "page",
            "in": "query",
            "description": "Page number",
            "schema": {
              "type": "string",
              "default": "1"
            }
          },
          {
            "name": "per_page",
            "in": "query",
            "description": "Items per page",
            "schema": {
              "type": "integer",
              "format": "int32",
              "default": 20
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
                    "value": "{\n  \"page\": 1,\n  \"logs\": [\n    {\n      \"id\": \"emwk7ra70oem3xa\",\n      \"text\": \"Modified Development defaults in Pied Piper Demo project\",\n      \"html\": \"Modified <a href='/workplace/103/projects/wk7radvodfneb/defaults?stage=dev'>Development's</a> defaults in <a href='/workplace/wk7radvodfneb/pipelines/410'>Pied Piper Demo</a> project\",\n      \"created_at\": \"2019-04-01T21:40:34.891Z\",\n      \"config\": null,\n      \"environment\": \"dev\",\n      \"project\": \"wk7radvodfneb\",\n      \"user\": {\n        \"email\": \"adam@piedpiper.com\",\n        \"name\": \"Adam Smitth\",\n        \"profile_image_url\": \"https://www.gravatar.com/avatar/082c73740a33762db7c5cc7481833e1e?s=500&d=retro\"\n      }\n    }\n  ]\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "page": {
                      "type": "integer",
                      "example": 1,
                      "default": 0
                    },
                    "logs": {
                      "type": "array",
                      "items": {
                        "type": "object",
                        "properties": {
                          "id": {
                            "type": "string",
                            "example": "emwk7ra70oem3xa"
                          },
                          "text": {
                            "type": "string",
                            "example": "Modified Development defaults in Pied Piper Demo project"
                          },
                          "html": {
                            "type": "string",
                            "example": "Modified <a href='/workplace/103/projects/wk7radvodfneb/defaults?stage=dev'>Development's</a> defaults in <a href='/workplace/wk7radvodfneb/pipelines/410'>Pied Piper Demo</a> project"
                          },
                          "created_at": {
                            "type": "string",
                            "example": "2019-04-01T21:40:34.891Z"
                          },
                          "config": {},
                          "environment": {
                            "type": "string",
                            "example": "dev"
                          },
                          "project": {
                            "type": "string",
                            "example": "wk7radvodfneb"
                          },
                          "user": {
                            "type": "object",
                            "properties": {
                              "email": {
                                "type": "string",
                                "example": "adam@piedpiper.com"
                              },
                              "name": {
                                "type": "string",
                                "example": "Adam Smitth"
                              },
                              "profile_image_url": {
                                "type": "string",
                                "example": "https://www.gravatar.com/avatar/082c73740a33762db7c5cc7481833e1e?s=500&d=retro"
                              }
                            }
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