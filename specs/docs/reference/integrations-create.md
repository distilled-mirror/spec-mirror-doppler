---
updatedAt: 2026-08-26T17:52:11.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Create

Create a new external integration.

Some integration types support keyless authentication, where Doppler authenticates with a short-lived OIDC token instead of a stored credential. For those types, `authMethod` selects the mode and determines which other fields are required. See [Keyless Authentication](https://docs.doppler.com/docs/gcp-secret-manager#keyless-authentication) for how the trust relationship is established.

Keyless connections are created without their access being verified, since the identity they authenticate as contains the connection ID that this request returns. Grant that identity access in your cloud after creating the connection, using the `federation` object on the [Retrieve](https://docs.doppler.com/docs/integrations-get) response.

## AWS Secrets Manager and Parameter Store

Type: `aws_secrets_manager` or `aws_parameter_store`

### Data Object

| Field                  | Type   | Description                                                                                                                                                               |
| :--------------------- | :----- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| aws\_assume\_role\_arn | string | The ARN of the AWS role that Doppler should use to assume into your AWS account. See [docs](https://docs.doppler.com/docs/aws-secrets-manager) for configuration details. |

## Azure Vault (Service Principal)

Type: `azure_vault_service_principal`

### Data Object

| Field          | Type   | Description                                                                                                 |
| :------------- | :----- | :---------------------------------------------------------------------------------------------------------- |
| client\_id     | string | The Service Principal Client ID. See [docs](https://docs.doppler.com/docs/azure-key-vault#custom-service-principal) for details.      |
| client\_secret | string | The Service Principal Client Secret. See [docs](https://docs.doppler.com/docs/azure-key-vault#custom-service-principal)  for details. |
| tenant\_id     | string | The Service Principal Tenant ID. See [docs](https://docs.doppler.com/docs/azure-key-vault#custom-service-principal)   for details.    |

## Azure Service Principal (Rotated and Dynamic)

Type: `azure_rotated_service_principal` or `azure_dynamic_service_principal`

These types support keyless authentication. See [docs](https://docs.doppler.com/docs/azure-service-principal) for setup details.

### Data Object

| Field        | Type   | Description                                                                                                                    |
| :----------- | :----- | :----------------------------------------------------------------------------------------------------------------------------- |
| authMethod   | string | `oidc` for keyless authentication or `clientSecret`. Defaults to `clientSecret` when omitted.                                  |
| clientId     | string | The Application (Client) ID of the managing Service Principal.                                                                 |
| tenantId     | string | The Directory (Tenant) ID of the managing Service Principal.                                                                   |
| clientSecret | string | The managing Service Principal's client secret value. Required when `authMethod` is `clientSecret`, rejected when it's `oidc`. |

## CircleCI

Type: `circleci`

### Data Object

| Field      | Type   | Description                                                                                 |
| :--------- | :----- | :------------------------------------------------------------------------------------------ |
| api\_token | string | A CircleCI API token. See [docs](https://docs.doppler.com/docs/circleci) for setup details. |

## Fly.io

Type: `flyio`

### Data Object

| Field    | Type   | Description                                                                          |
| :------- | :----- | :----------------------------------------------------------------------------------- |
| api\_key | string | A Fly.io API key. See [docs](https://docs.doppler.com/docs/flyio) for setup details. |

## GCP Cloud SQL

Type: `gcp_cloudsql_mysql`, `gcp_cloudsql_postgres`, or `gcp_cloudsql_sqlserver`

These types support keyless authentication. See [docs](https://docs.doppler.com/docs/gcp_cloudsql) for setup details.

### Data Object

| Field                             | Type   | Description                                                                                                                             |
| :-------------------------------- | :----- | :-------------------------------------------------------------------------------------------------------------------------------------- |
| authMethod                        | string | `oidc` for keyless authentication or `key`. Defaults to `key` when omitted.                                                             |
| gcpKey                            | object | The IAM Service Account JSON key. Required when `authMethod` is `key`.                                                                  |
| gcp\_workload\_identity\_provider | string | The full resource name of the workload identity provider, beginning with `//iam.googleapis.com/`. Required when `authMethod` is `oidc`. |
| gcp\_project\_id                  | string | The GCP project ID. Required when `authMethod` is `oidc`.                                                                               |

Supplying both `gcpKey` and `gcp_workload_identity_provider` is rejected.

## GCP Secret Manager

Type: `gcp_secret_manager`

This type supports keyless authentication. See [docs](https://docs.doppler.com/docs/gcp-secret-manager) for setup details.

### Data Object

| Field                             | Type   | Description                                                                                                                             |
| :-------------------------------- | :----- | :-------------------------------------------------------------------------------------------------------------------------------------- |
| authMethod                        | string | `oidc` for keyless authentication or `key`. Defaults to `key` when omitted.                                                             |
| gcp\_key                          | object | The IAM Service Account JSON key. Required when `authMethod` is `key`. See [docs](https://docs.doppler.com/docs/gcp-secret-manager) for details.                  |
| gcp\_workload\_identity\_provider | string | The full resource name of the workload identity provider, beginning with `//iam.googleapis.com/`. Required when `authMethod` is `oidc`. |
| gcp\_project\_id                  | string | The GCP project ID. Required when `authMethod` is `oidc`.                                                                               |
| gcp\_secret\_prefix               | string | The prefix added to any secret created by this integration in GCP. See [docs](https://docs.doppler.com/docs/gcp-secret-manager) for details.                      |

Supplying both `gcp_key` and `gcp_workload_identity_provider` is rejected.

## Terraform Cloud

Type: `terraform_cloud`

### Data Object

| Field    | Type   | Description                                                                                             |
| :------- | :----- | :------------------------------------------------------------------------------------------------------ |
| api\_key | string | A Terraform Cloud API key. See [docs](https://docs.doppler.com/docs/terraform-cloud) for setup details. |

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
    "/v3/integrations": {
      "post": {
        "summary": "Create",
        "description": "Create a new external integration.",
        "operationId": "integrations-create",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "type",
                  "name"
                ],
                "properties": {
                  "type": {
                    "type": "string",
                    "description": "The integration type"
                  },
                  "name": {
                    "type": "string",
                    "description": "The name of the integration"
                  },
                  "data": {
                    "type": "object",
                    "description": "The authentication data for the integration",
                    "properties": {}
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