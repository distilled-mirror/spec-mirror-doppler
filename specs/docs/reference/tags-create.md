---
updatedAt: 2026-10-06T02:23:00.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Create

Create a tag. Requires the `tags_create` workplace permission. A workplace can have up to 100 tags.

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
    "/v3/workplace/tags": {
      "post": {
        "summary": "Create",
        "operationId": "tags-create",
        "deprecated": false,
        "description": "Create a tag. Requires the `tags_create` workplace permission. A workplace can have up to 100 tags.",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "name"
                ],
                "properties": {
                  "name": {
                    "type": "string",
                    "description": "The tag's name. Between 1 and 32 characters. Must be unique in the workplace, regardless of capitalization."
                  },
                  "color": {
                    "type": "string",
                    "enum": [
                      "gray",
                      "purple",
                      "blue",
                      "green",
                      "yellow",
                      "orange",
                      "red",
                      "pink"
                    ],
                    "description": "The tag's color.",
                    "default": "gray"
                  },
                  "slug": {
                    "type": "string",
                    "description": "The tag's slug. Lowercase letters, numbers, and underscores, up to 32 characters. Must be unique in the workplace. Defaults to the name in lowercase, with each run of other characters replaced by `_`. Can't be changed later."
                  }
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "The created tag.",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"tag\": {\n    \"slug\": \"pci\",\n    \"name\": \"PCI\",\n    \"color\": \"red\",\n    \"created_at\": \"2026-10-05T19:04:22.118Z\"\n  }\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "tag": {
                      "type": "object",
                      "properties": {
                        "slug": {
                          "type": "string",
                          "description": "The tag's unique identifier. Use it to refer to the tag in other API calls. Can't be changed.",
                          "example": "pci"
                        },
                        "name": {
                          "type": "string",
                          "description": "The tag's display name.",
                          "example": "PCI"
                        },
                        "color": {
                          "type": "string",
                          "enum": [
                            "gray",
                            "purple",
                            "blue",
                            "green",
                            "yellow",
                            "orange",
                            "red",
                            "pink"
                          ],
                          "description": "The tag's color.",
                          "example": "red"
                        },
                        "created_at": {
                          "type": "string",
                          "description": "Date and time the tag was created.",
                          "example": "2026-10-05T19:04:22.118Z"
                        }
                      }
                    }
                  }
                }
              }
            }
          },
          "400": {
            "description": "The name or slug is invalid or already used, or the workplace has reached its tag limit.",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"messages\": [\n    \"A tag with this name already exists.\"\n  ],\n  \"success\": false\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "messages": {
                      "type": "array",
                      "items": {
                        "type": "string",
                        "example": "A tag with this name already exists."
                      }
                    },
                    "success": {
                      "type": "boolean",
                      "example": false
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
  "x-readme": {
    "headers": [],
    "explorer-enabled": true,
    "proxy-enabled": false
  },
  "x-readme-fauxas": true
}
```