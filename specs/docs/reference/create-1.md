---
updatedAt: 2025-12-19T21:35:50.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Create

Create a new change request with one or more change request units

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
    "/v3/workplace/change_requests": {
      "post": {
        "description": "",
        "operationId": "post_v3workplacechange_requests",
        "responses": {
          "200": {
            "description": "",
            "content": {
              "application/json": {
                "schema": {
                  "type": "object",
                  "properties": {
                    "changeRequest": {
                      "type": "object",
                      "properties": {
                        "id": {
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
        "parameters": [],
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "properties": {
                  "title": {
                    "type": "string"
                  },
                  "description": {
                    "type": "string"
                  },
                  "assigned": {
                    "type": "array",
                    "items": {
                      "properties": {
                        "type": {
                          "type": "string",
                          "enum": [
                            "WorkplaceUser",
                            "ServiceAccount"
                          ]
                        },
                        "slug": {
                          "type": "string"
                        }
                      },
                      "type": "object",
                      "required": [
                        "type",
                        "slug"
                      ]
                    }
                  },
                  "units": {
                    "type": "array",
                    "items": {
                      "properties": {
                        "action": {
                          "type": "string",
                          "default": "create",
                          "enum": [
                            "create"
                          ]
                        },
                        "id": {
                          "type": "string"
                        },
                        "target": {
                          "type": "object",
                          "properties": {
                            "project": {
                              "type": "string"
                            },
                            "config": {
                              "type": "string"
                            }
                          },
                          "required": [
                            "project",
                            "config"
                          ]
                        },
                        "status": {
                          "type": "string",
                          "default": "open",
                          "enum": [
                            "draft",
                            "open"
                          ]
                        },
                        "updates": {
                          "type": "array",
                          "items": {
                            "properties": {
                              "name": {
                                "type": "string"
                              },
                              "value": {
                                "type": "string"
                              },
                              "shouldDelete": {
                                "type": "boolean",
                                "description": "Whether to delete the secret from target config when applied"
                              },
                              "visType": {
                                "type": "integer",
                                "description": "0 = masked, 1 = unmasked, 2 = restricted",
                                "enum": [
                                  0,
                                  1,
                                  2
                                ]
                              },
                              "valueType": {
                                "type": "object",
                                "properties": {
                                  "type": {
                                    "type": "string"
                                  }
                                }
                              },
                              "generationSettings": {
                                "type": "object",
                                "properties": {}
                              },
                              "originalSecretUpdateName": {
                                "type": "string"
                              }
                            },
                            "type": "object",
                            "required": [
                              "name"
                            ]
                          }
                        }
                      },
                      "type": "object",
                      "required": [
                        "action",
                        "target",
                        "updates"
                      ]
                    }
                  }
                },
                "required": [
                  "title",
                  "assigned",
                  "units"
                ]
              },
              "examples": {}
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