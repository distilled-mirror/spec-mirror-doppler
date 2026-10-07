---
updatedAt: 2026-10-06T02:23:00.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Update

Rename a tag or change its color. You must specify at least one of `name` or `color`. A tag's slug can't be changed. Requires the `tags_update` workplace permission.

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
    "/v3/workplace/tags/tag/{tag}": {
      "patch": {
        "summary": "Update",
        "operationId": "tags-update",
        "deprecated": false,
        "description": "Rename a tag or change its color. You must specify at least one of `name` or `color`. A tag's slug can't be changed. Requires the `tags_update` workplace permission.",
        "parameters": [
          {
            "name": "tag",
            "in": "path",
            "required": true,
            "description": "The tag's slug.",
            "schema": {
              "type": "string"
            }
          }
        ],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [],
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
                    "description": "The tag's color."
                  }
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "The updated tag.",
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
            "description": "Neither `name` nor `color` was specified, or the name is invalid or already used.",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"messages\": [\n    \"You must specify name or color\"\n  ],\n  \"success\": false\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "messages": {
                      "type": "array",
                      "items": {
                        "type": "string",
                        "example": "You must specify name or color"
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
          },
          "404": {
            "description": "The tag doesn't exist.",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"messages\": [\n    \"Tag does not exist\"\n  ],\n  \"success\": false\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "messages": {
                      "type": "array",
                      "items": {
                        "type": "string",
                        "example": "Tag does not exist"
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