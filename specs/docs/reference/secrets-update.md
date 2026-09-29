---
updatedAt: 2025-05-29T17:01:37.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Update

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
      "post": {
        "summary": "Update",
        "description": "Secrets",
        "operationId": "secrets-update",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "project",
                  "config"
                ],
                "properties": {
                  "project": {
                    "type": "string",
                    "description": "Unique identifier for the project object.",
                    "default": "PROJECT_NAME"
                  },
                  "config": {
                    "type": "string",
                    "description": "Name of the config object.",
                    "default": "CONFIG_NAME"
                  },
                  "secrets": {
                    "type": "object",
                    "description": "Either `secrets` or `change_requests` is required (can't use both). Object of secrets you would like to save to the config. Try it with the sample secrets below.",
                    "properties": {
                      "STRIPE": {
                        "type": "string",
                        "default": "sk_test_9YxLnoLDdvOPn2dfjBVPB"
                      },
                      "ALGOLIA": {
                        "type": "string",
                        "default": "N9TOPUCTO"
                      },
                      "DATABASE": {
                        "type": "string",
                        "default": "${USER}@aws.dynamodb.com:9876"
                      }
                    }
                  },
                  "change_requests": {
                    "type": "array",
                    "description": "Either `secrets` or `change_requests` is required (can't use both). Object of secrets you would like to save to the config. Try it with the sample secrets below.",
                    "items": {
                      "properties": {
                        "name": {
                          "type": "string",
                          "description": "The name of the secret."
                        },
                        "originalName": {
                          "type": "string",
                          "description": "The original name of the secret. Use `null` (an actual `null`, not the string `null`) or omit this parameter for new secrets. If it differs from `name` then a rename is inferred."
                        },
                        "value": {
                          "type": "string",
                          "description": "The value the secret should have. Use `null` (an actual `null`, not the string `null`) to leave the existing secret value unchanged."
                        },
                        "originalValue": {
                          "type": "string",
                          "description": "The value you expect the secret to have before `name` is applied. If specified, the request will only be processed if the provided value matches what's found in Doppler."
                        },
                        "visibility": {
                          "type": "string",
                          "description": "Must be set to either `masked`, `unmasked`, or `restricted`."
                        },
                        "originalVisibility": {
                          "type": "string",
                          "description": "Must be set to either `masked`, `unmasked`, or `restricted`. The visibility you expect the secret to have before `visibility` is applied. If specified, the request will only be processed if the provided visibility matches what's found in Doppler."
                        },
                        "shouldPromote": {
                          "type": "boolean",
                          "description": "Defaults to `false`. Can only be set to `true` if the config being updated is a branch config. If set to `true`, the provided secret will be set in both the branch config as well as the root config in that environment."
                        },
                        "shouldDelete": {
                          "type": "boolean",
                          "description": "Defaults to `false`. If set to `true`, will delete the secret matching the `name` field."
                        },
                        "shouldConverge": {
                          "type": "boolean",
                          "description": "Defaults to `false`. Can only be set to `true` if the config being updated is a branch config and there is a secret with the same name in the root config. In this case, the branch secret will inherit the value and visibility type from the root secret."
                        },
                        "valueType": {
                          "type": "object",
                          "description": "The default valueType (string) will result in no validations being applied.",
                          "properties": {
                            "type": {
                              "type": "string",
                              "enum": [
                                "string",
                                "json",
                                "json5",
                                "boolean",
                                "integer",
                                "decimal",
                                "email",
                                "url",
                                "uuidv4",
                                "cuid2",
                                "ulid",
                                "datetime8601",
                                "date8601",
                                "yaml"
                              ]
                            }
                          }
                        },
                        "originalValueType": {
                          "type": "object",
                          "description": "The valueType you expect the secret to have before `valueType` is applied. If specified, the request will only be processed if the provided valueType matches what's found in Doppler.",
                          "properties": {
                            "type": {
                              "type": "string",
                              "enum": [
                                "string",
                                "json",
                                "json5",
                                "boolean",
                                "integer",
                                "decimal",
                                "email",
                                "url",
                                "uuidv4",
                                "cuid2",
                                "ulid",
                                "datetime8601",
                                "date8601",
                                "yaml"
                              ]
                            }
                          }
                        }
                      },
                      "required": [
                        "name",
                        "originalName",
                        "value"
                      ],
                      "type": "object"
                    }
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
                    "value": "{\n  \"secrets\": {\n    \"STRIPE\": {\n      \"raw\": \"sk_test_9YxLnoLDdvOPn2dfjBVPB\",\n      \"computed\": \"sk_test_9YxLnoLDdvOPn2dfjBVPB\",\n      \"note\": \"\"\n    },\n    \"ALGOLIA\": {\n      \"raw\": \"N9TOPUCTO\",\n      \"computed\": \"N9TOPUCTO\",\n      \"note\": \"\"\n    },\n    \"DATABASE\": {\n    \t\"raw\": \"${USER}@aws.dynamodb.com:9876\",\n      \"computed\": \"brian@aws.dynamodb.com:9876\",\n      \"note\": \"\"\n    }\n  }\n}"
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