---
updatedAt: 2025-12-19T21:35:50.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Update

Update an existing change request's metadata and/or units

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
    "/v3/workplace/change_requests/change_request/{change_request_id}": {
      "post": {
        "description": "",
        "operationId": "put_v3workplacechange_requestschange_request{change_request_id}",
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
        "parameters": [
          {
            "in": "path",
            "name": "change_request_id",
            "schema": {
              "type": "string"
            },
            "required": true
          }
        ],
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
                        "slug",
                        "type"
                      ]
                    }
                  },
                  "units": {
                    "type": "array",
                    "items": {
                      "properties": {
                        "action": {
                          "type": "string",
                          "description": "",
                          "enum": [
                            "create",
                            "update"
                          ]
                        },
                        "id": {
                          "type": "string",
                          "description": ""
                        },
                        "status": {
                          "type": "string",
                          "description": "",
                          "enum": [
                            "draft",
                            "open"
                          ],
                          "default": "open"
                        },
                        "updates": {
                          "type": "array",
                          "items": {
                            "properties": {
                              "action": {
                                "type": "string",
                                "default": "",
                                "enum": [
                                  "upsert",
                                  "delete"
                                ]
                              },
                              "name": {
                                "type": "string"
                              },
                              "value": {
                                "type": "string"
                              },
                              "shouldDelete": {
                                "type": "boolean",
                                "default": "",
                                "description": "Whether to delete the secret from target config when applied"
                              },
                              "visType": {
                                "type": "integer",
                                "enum": [
                                  0,
                                  1,
                                  2
                                ],
                                "description": "0 = masked, 1 = unmasked, 2 = restricted"
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
                        "updates"
                      ]
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