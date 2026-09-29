---
updatedAt: 2025-05-29T17:01:38.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Update Note

Set a note on a secret

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
    "/v3/projects/project/note": {
      "post": {
        "summary": "Update Note",
        "description": "Set a note on a secret",
        "operationId": "secrets-update_note",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "description": "Unique identifier for the project object.",
            "schema": {
              "type": "string",
              "default": "PROJECT_NAME"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "secret",
                  "note"
                ],
                "properties": {
                  "secret": {
                    "type": "string",
                    "description": "The name of the secret",
                    "default": "SECRET_NAME"
                  },
                  "note": {
                    "type": "string",
                    "description": "The note you want to set on the secret. This note will be applied to the specified secret in all environments.",
                    "default": "YOUR_NOTE"
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
                    "value": "{\n  \"secret\": \"FOO\",\n  \"note\": \"bar\"\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "secret": {
                      "type": "string",
                      "example": "FOO"
                    },
                    "note": {
                      "type": "string",
                      "example": "bar"
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