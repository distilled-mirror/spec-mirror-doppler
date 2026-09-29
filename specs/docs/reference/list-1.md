---
updatedAt: 2025-12-19T21:35:50.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# List

List existing change requests

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
      "get": {
        "description": "",
        "operationId": "get_v3workplacechange_requests",
        "responses": {
          "200": {
            "description": "",
            "content": {
              "application/json": {
                "schema": {
                  "type": "array",
                  "items": {
                    "type": "object",
                    "properties": {
                      "id": {
                        "type": "string"
                      },
                      "title": {
                        "type": "string"
                      },
                      "status": {
                        "type": "string",
                        "enum": [
                          "open",
                          "closed"
                        ]
                      },
                      "createdAt": {
                        "type": "string",
                        "format": "date-time"
                      },
                      "createdBy": {
                        "type": "object",
                        "properties": {
                          "slug": {
                            "type": "string"
                          },
                          "type": {
                            "type": "string",
                            "enum": [
                              "User",
                              "ServiceAccount"
                            ]
                          },
                          "name": {
                            "type": "string"
                          },
                          "isActive": {
                            "type": "boolean"
                          },
                          "image": {
                            "type": "string"
                          }
                        }
                      },
                      "units": {
                        "type": "array",
                        "items": {
                          "properties": {
                            "id": {
                              "type": "string"
                            },
                            "status": {
                              "type": "string",
                              "enum": [
                                "draft",
                                "open",
                                "applied",
                                "canceled"
                              ]
                            },
                            "target": {
                              "type": "object",
                              "properties": {
                                "project": {
                                  "type": "object",
                                  "properties": {
                                    "slug": {
                                      "type": "string"
                                    },
                                    "name": {
                                      "type": "string"
                                    }
                                  }
                                },
                                "environment": {
                                  "type": "object",
                                  "properties": {
                                    "slug": {
                                      "type": "string"
                                    },
                                    "name": {
                                      "type": "string"
                                    }
                                  }
                                },
                                "config": {
                                  "type": "object",
                                  "properties": {
                                    "slug": {
                                      "type": "string"
                                    },
                                    "name": {
                                      "type": "string"
                                    }
                                  }
                                }
                              }
                            }
                          },
                          "type": "object"
                        }
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
                            },
                            "name": {
                              "type": "string"
                            },
                            "email": {
                              "type": "string"
                            },
                            "image": {
                              "type": "string"
                            }
                          },
                          "type": "object"
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        },
        "parameters": [
          {
            "in": "query",
            "name": "page",
            "schema": {
              "type": "integer",
              "default": "1"
            }
          },
          {
            "in": "query",
            "name": "per_page",
            "schema": {
              "type": "integer",
              "default": "20"
            }
          },
          {
            "in": "query",
            "name": "status",
            "schema": {
              "type": "array",
              "items": {
                "type": "string"
              }
            }
          },
          {
            "in": "query",
            "name": "title",
            "schema": {
              "type": "string"
            }
          }
        ]
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