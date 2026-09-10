---
updatedAt: 2025-12-19T21:35:50.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Retrieve

Retrieve detailed information about a change request

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
      "get": {
        "description": "",
        "operationId": "get_v3workplacechange_requestschange_request{change_request_id}",
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
                        },
                        "title": {
                          "type": "string"
                        },
                        "description": {
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
                                  "canceled",
                                  "applied"
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
                              },
                              "applied": {
                                "type": "object",
                                "properties": {
                                  "configLog": {
                                    "type": "object",
                                    "properties": {
                                      "slug": {
                                        "type": "string"
                                      }
                                    }
                                  },
                                  "activityLog": {
                                    "type": "object",
                                    "properties": {
                                      "slug": {
                                        "type": "string"
                                      }
                                    }
                                  }
                                }
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
                                      "type": "boolean"
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
                                    }
                                  },
                                  "type": "object"
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
                                "description": "",
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
          },
          {
            "in": "query",
            "name": "reveal",
            "schema": {
              "type": "string"
            },
            "description": "Whether to reveal secret values. If defined, any value except \"false\" is treated as true"
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