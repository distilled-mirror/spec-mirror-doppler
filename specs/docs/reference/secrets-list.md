---
updatedAt: 2026-09-16T15:30:58.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# List

Secrets

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
    "/v3/configs/config/secrets": {
      "get": {
        "summary": "List",
        "description": "Secrets",
        "operationId": "secrets-list",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "description": "Unique identifier for the project object.",
            "required": true,
            "schema": {
              "type": "string",
              "default": "PROJECT_NAME"
            }
          },
          {
            "name": "config",
            "in": "query",
            "description": "Name of the config object.",
            "required": true,
            "schema": {
              "type": "string",
              "default": "CONFIG_NAME"
            }
          },
          {
            "name": "accepts",
            "in": "header",
            "description": "Available options are: **application/json**, **text/plain**",
            "schema": {
              "type": "string",
              "default": "application/json"
            }
          },
          {
            "name": "include_dynamic_secrets",
            "in": "query",
            "description": "Whether or not to issue leases and include dynamic secret values for the config",
            "schema": {
              "type": "boolean",
              "default": false
            }
          },
          {
            "name": "dynamic_secrets_ttl_sec",
            "in": "query",
            "description": "The number of seconds until dynamic leases expire. Must be used with `include_dynamic_secrets`. Defaults to 1800 (30 minutes).",
            "schema": {
              "type": "integer",
              "format": "int32"
            }
          },
          {
            "name": "secrets",
            "in": "query",
            "description": "A comma-separated list of secrets to include in the response",
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "include_managed_secrets",
            "in": "query",
            "description": "Whether to include Doppler's auto-generated (managed) secrets",
            "schema": {
              "type": "boolean",
              "default": true
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
                    "value": {
                      "secrets": {
                        "STRIPE": {
                          "raw": "sk_test_9YxLnoLDdvOPn2dfjBVPB",
                          "computed": "sk_test_9YxLnoLDdvOPn2dfjBVPB",
                          "note": "",
                          "rawVisibility": {
                            "type": "masked"
                          },
                          "computedVisibility": {
                            "type": "masked"
                          }
                        },
                        "ALGOLIA": {
                          "raw": "N9TOPUCTO",
                          "computed": "N9TOPUCTO",
                          "note": "",
                          "rawVisibility": {
                            "type": "masked"
                          },
                          "computedVisibility": {
                            "type": "masked"
                          }
                        },
                        "DATABASE": {
                          "raw": "${USER}@aws.dynamodb.com:9876",
                          "computed": "brian@aws.dynamodb.com:9876",
                          "note": "",
                          "rawVisibility": {
                            "type": "restricted"
                          },
                          "computedVisibility": {
                            "type": "restricted"
                          }
                        },
                        "USER": {
                          "raw": "brian",
                          "computed": "brian",
                          "note": "",
                          "rawVisibility": {
                            "type": "unmasked"
                          },
                          "computedVisibility": {
                            "type": "unmasked"
                          }
                        }
                      }
                    }
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "secrets": {
                      "type": "object",
                      "properties": {
                        "STRIPE": {
                          "type": "object",
                          "properties": {
                            "raw": {
                              "type": "string",
                              "example": "sk_test_9YxLnoLDdvOPn2dfjBVPB"
                            },
                            "computed": {
                              "type": "string",
                              "example": "sk_test_9YxLnoLDdvOPn2dfjBVPB"
                            },
                            "note": {
                              "type": "string",
                              "example": ""
                            },
                            "rawVisibility": {
                              "type": "object",
                              "example": "masked",
                              "properties": {
                                "type": {
                                  "type": "string"
                                }
                              }
                            },
                            "computedVisibility": {
                              "type": "object",
                              "example": "masked",
                              "properties": {
                                "type": {
                                  "type": "string"
                                }
                              }
                            }
                          }
                        },
                        "ALGOLIA": {
                          "type": "object",
                          "properties": {
                            "raw": {
                              "type": "string",
                              "example": "N9TOPUCTO"
                            },
                            "computed": {
                              "type": "string",
                              "example": "N9TOPUCTO"
                            },
                            "note": {
                              "type": "string",
                              "example": ""
                            },
                            "rawVisibility": {
                              "type": "object",
                              "example": "masked",
                              "properties": {
                                "type": {
                                  "type": "string"
                                }
                              }
                            },
                            "computedVisibility": {
                              "type": "object",
                              "example": "masked",
                              "properties": {
                                "type": {
                                  "type": "string"
                                }
                              }
                            }
                          }
                        },
                        "DATABASE": {
                          "type": "object",
                          "properties": {
                            "raw": {
                              "type": "string",
                              "example": "${USER}@aws.dynamodb.com:9876"
                            },
                            "computed": {
                              "type": "string",
                              "example": "brian@aws.dynamodb.com:9876"
                            },
                            "note": {
                              "type": "string",
                              "example": ""
                            },
                            "rawVisibility": {
                              "type": "object",
                              "example": "restricted",
                              "properties": {
                                "type": {
                                  "type": "string"
                                }
                              }
                            },
                            "computedVisibility": {
                              "type": "object",
                              "example": "restricted",
                              "properties": {
                                "type": {
                                  "type": "string"
                                }
                              }
                            }
                          }
                        },
                        "USER": {
                          "type": "object",
                          "properties": {
                            "raw": {
                              "type": "string",
                              "example": "brian"
                            },
                            "computed": {
                              "type": "string",
                              "example": "brian"
                            },
                            "note": {
                              "type": "string",
                              "example": ""
                            },
                            "rawVisibility": {
                              "type": "object",
                              "example": "unmasked",
                              "properties": {
                                "type": {
                                  "type": "string"
                                }
                              }
                            },
                            "computedVisibility": {
                              "type": "object",
                              "example": "unmasked",
                              "properties": {
                                "type": {
                                  "type": "string"
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