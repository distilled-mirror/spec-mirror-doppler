---
updatedAt: 2026-08-26T17:52:11.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Retrieve

Retrieve an existing integration

## Federation

Integrations that authenticate keylessly return a `federation` object describing the identity Doppler presents to your cloud. It is `null` for every other integration, including those of a keyless-capable type that were connected with a stored credential.

Grant this identity access in your cloud after creating the connection. Until you do, Doppler can authenticate but has no permissions, and the connection reports no error because a keyless connection's access isn't verified at create time.

### GCP

| Field     | Type   | Description                                                                            |
| :-------- | :----- | :------------------------------------------------------------------------------------- |
| kind      | string | Always `gcp`.                                                                          |
| principal | string | The IAM principal to grant roles to, beginning with `principal://iam.googleapis.com/`. |

```json
{
  "integration": {
    "slug": "00000000-0000-0000-0000-000000000000",
    "name": "my-integration",
    "type": "gcp_secret_manager",
    "federation": {
      "kind": "gcp",
      "principal": "principal://iam.googleapis.com/projects/123456789012/locations/global/workloadIdentityPools/doppler/subject/workplace:my-workplace:connection:00000000-0000-0000-0000-000000000000"
    }
  }
}
```

### Azure

| Field    | Type   | Description                                                         |
| :------- | :----- | :------------------------------------------------------------------ |
| kind     | string | Always `azure`.                                                     |
| issuer   | string | The issuer to enter on the app registration's federated credential. |
| subject  | string | The subject identifier to enter on the federated credential.        |
| audience | string | The audience to enter on the federated credential.                  |

```json
{
  "integration": {
    "slug": "00000000-0000-0000-0000-000000000000",
    "name": "my-integration",
    "type": "azure_rotated_service_principal",
    "federation": {
      "kind": "azure",
      "issuer": "https://api.doppler.com",
      "subject": "workplace:my-workplace:connection:00000000-0000-0000-0000-000000000000",
      "audience": "api://AzureADTokenExchange"
    }
  }
}
```

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
    "/v3/integrations/integration": {
      "get": {
        "summary": "Retrieve",
        "description": "Retrieve an existing integration",
        "operationId": "integrations-get",
        "parameters": [
          {
            "name": "integration",
            "in": "query",
            "description": "The integration slug",
            "required": true,
            "schema": {
              "type": "string"
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
                    "value": "{\n  \"integration\": {\n    \"slug\": \"00000000-0000-0000-0000-000000000000\",\n    \"name\": \"my-integration\",\n    \"type\": \"gcp_secret_manager\",\n    \"federation\": {\n      \"kind\": \"gcp\",\n      \"principal\": \"principal://iam.googleapis.com/projects/123456789012/locations/global/workloadIdentityPools/doppler/subject/workplace:my-workplace:connection:00000000-0000-0000-0000-000000000000\"\n    }\n  }\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "integration": {
                      "type": "object",
                      "properties": {
                        "slug": {
                          "type": "string",
                          "example": "00000000-0000-0000-0000-000000000000"
                        },
                        "name": {
                          "type": "string",
                          "example": "my-integration"
                        },
                        "type": {
                          "type": "string",
                          "example": "aws"
                        },
                        "federation": {
                          "description": "The keyless federation identity Doppler presents to your cloud, or null if this connection does not use keyless authentication. Grant this identity access after creating the connection.",
                          "oneOf": [
                            {
                              "type": "object",
                              "title": "GCP",
                              "properties": {
                                "kind": {
                                  "type": "string",
                                  "const": "gcp"
                                },
                                "principal": {
                                  "type": "string",
                                  "description": "The IAM principal to grant roles to.",
                                  "example": "principal://iam.googleapis.com/projects/123456789012/locations/global/workloadIdentityPools/doppler/subject/workplace:my-workplace:connection:00000000-0000-0000-0000-000000000000"
                                }
                              },
                              "required": [
                                "kind",
                                "principal"
                              ]
                            },
                            {
                              "type": "object",
                              "title": "Azure",
                              "properties": {
                                "kind": {
                                  "type": "string",
                                  "const": "azure"
                                },
                                "issuer": {
                                  "type": "string",
                                  "description": "The issuer to enter on the app registration's federated credential.",
                                  "example": "https://api.doppler.com"
                                },
                                "subject": {
                                  "type": "string",
                                  "description": "The subject identifier to enter on the federated credential.",
                                  "example": "workplace:my-workplace:connection:00000000-0000-0000-0000-000000000000"
                                },
                                "audience": {
                                  "type": "string",
                                  "description": "The audience to enter on the federated credential.",
                                  "example": "api://AzureADTokenExchange"
                                }
                              },
                              "required": [
                                "kind",
                                "issuer",
                                "subject",
                                "audience"
                              ]
                            },
                            {
                              "type": "null"
                            }
                          ]
                        }
                      }
                    }
                  }
                }
              }
            }
          },
          "400": {
            "description": "400",
            "content": {
              "application/json": {
                "examples": {
                  "Result": {
                    "value": "{}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {}
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