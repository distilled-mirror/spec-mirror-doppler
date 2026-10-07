---
updatedAt: 2026-10-06T02:23:00.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Assign

Assign an existing tag to a project. Requires the `enclave_project_tags_manage` project permission. A project can have up to 100 tags.

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
    "/v3/projects/project/tags": {
      "post": {
        "summary": "Assign",
        "operationId": "project_tags-assign",
        "deprecated": false,
        "description": "Assign an existing tag to a project. Requires the `enclave_project_tags_manage` project permission. A project can have up to 100 tags.",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "required": true,
            "description": "The project's slug.",
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
                "required": [
                  "tag"
                ],
                "properties": {
                  "tag": {
                    "type": "string",
                    "description": "The slug of the tag to assign."
                  }
                }
              }
            }
          }
        },
        "responses": {
          "200": {
            "description": "The assigned tag.",
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
            "description": "The project has reached its tag limit.",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"messages\": [\n    \"Your project has reached its limit of 100 tags.\"\n  ],\n  \"success\": false\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "messages": {
                      "type": "array",
                      "items": {
                        "type": "string",
                        "example": "Your project has reached its limit of 100 tags."
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
          },
          "409": {
            "description": "The tag is already assigned to the project.",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{\n  \"messages\": [\n    \"This tag is already assigned to this project.\"\n  ],\n  \"success\": false\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "messages": {
                      "type": "array",
                      "items": {
                        "type": "string",
                        "example": "This tag is already assigned to this project."
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