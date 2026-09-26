---
updatedAt: 2026-09-25T16:29:17.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Create

Create a new secrets sync.

## General

Each sync integration type has its own configuration parameters which must be provided in the `data` field. Some parameter values are completely user-defined (e.g. AWS Secret Manager path) but others are identifiers from the external service (e.g. Fly.io app ID). You can use the [Integration > Get Options](https://docs.doppler.com/reference/get-options) endpoint to fetch all available options for a particular integration.

Below are the `data` fields for each integration type:

## AWS Secrets Manager

| Field                | Type                               | Description                                                                           |
| :------------------- | :--------------------------------- | :------------------------------------------------------------------------------------ |
| path                 | string                             | The path of the AWS Secret Manager secret                                             |
| region               | string                             | The AWS region to create the secret (e.g. us-east-1)                                  |
| tags                 | object\<string, string> (optional) | Tags to attach to the AWS secrets                                                     |
| use\_doppler\_suffix | boolean (optional)                 | Whether or not to append "doppler" to the end of the provided path (defaults to true) |

## AWS Parameter Store

| Field          | Type                               | Description                                                                          |
| :------------- | :--------------------------------- | :----------------------------------------------------------------------------------- |
| path           | string                             | The path of the parameters in AWS                                                    |
| region         | string                             | The AWS region to create the secret (e.g. us-east-1)                                 |
| tags           | object\<string, string> (optional) | Tags to attach to the parameters                                                     |
| secure\_string | boolean (optional)                 | Whether or not the parameters should be created as secure strings (defaults to true) |

## Azure Vault (Service Principal)

| Field                | Type              | Description                                                                                                                                |
| :------------------- | :---------------- | :----------------------------------------------------------------------------------------------------------------------------------------- |
| sync\_strategy       | string            | Determines whether secrets are synced to a single secret (`single-secret`) as a JSON object or multiple discrete secrets (`multi-secret`). |
| vault\_uri           | string            | The Azure Vault URI for the vault secrets will be synced to.                                                                               |
| single\_secret\_name | string (optional) | The name of the secret being synced to when using the `single-secret` sync strategy. Ignored when using `multi-secret` sync strategy.      |

## CircleCI

| Field              | Type   | Description                                                          |
| :----------------- | :----- | :------------------------------------------------------------------- |
| resource\_type     | string | Either "project" or "context", based on the resource type to sync to |
| resource\_id       | string | The resource ID (either project or context) to sync to               |
| organization\_slug | string | The organization slug where the resource is located                  |

## Fly.io

| Field             | Type    | Description                                                                                  |
| :---------------- | :------ | :------------------------------------------------------------------------------------------- |
| app\_id           | string  | The Fly.io app ID to sync to                                                                 |
| restart\_machines | boolean | Whether or not Doppler should automatically restart Fly.io machines after secrets are synced |

## GCP Secret Manager

| Field          | Type              | Description                                                                                                                                                  |
| :------------- | :---------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| sync\_strategy | string            | Determines whether secrets are synced to a single secret (`single-secret`) as a JSON object or multiple discrete secrets (`multi-secret`).                   |
| regions        | array\<string>    | The GCP regions used for replication. Can include any supported GCP region or `["automatic"]`. `automatic` cannot be used if other regions are listed.       |
| format         | string (optional) | Specifies the format secrets will be stored in. Either `env` or `json`. Defaults to `json`.                                                                  |
| name           | string            | The name used to store the secret when sync\_strategy is set to `single-secret` (note that the integration's `gcp_secret_prefix` will be prepended to this). |

## GitHub (Actions, Codespaces, Dependabot, Copilot Agents)

| Field                         | Type                         | Description                                                                                                                                                                         |
| :---------------------------- | :--------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| feature                       | string                       | One of `actions`, `codespaces`, `dependabot`, or `agents` (defaults to `actions`)                                                                                                   |
| sync\_target                  | string                       | Either "repo" or "org", based on the resource type to sync to                                                                                                                       |
| repo\_name                    | string (repo only)           | The GitHub repo name to sync to (only used when `sync_target` is set to "repo")                                                                                                     |
| environment\_name             | string (optional, repo only) | The GitHub repo environment name to sync to (only used when `feature` is set to "actions" and `sync_target` is set to "repo")                                                       |
| org\_scope                    | string (org only)            | Either "all" or "private", based on the which repos you want to have access (only used when `sync_target` is set to "org")                                                          |
| sync\_unmasked\_as\_variables | boolean (optional)           | When enabled, causes secrets with the `unmasked` visibility type to get synced as GitHub Variables (only used when `feature` is set to "actions" or "agents"). Defaults to `false`. |

## GitHub Codespaces

| Field        | Type   | Description                  |
| :----------- | :----- | :--------------------------- |
| feature      | string | Must be exactly `codespaces` |
| sync\_target | string |                              |

## Heroku

| Field         | Type                   | Description                                                       |
| :------------ | :--------------------- | :---------------------------------------------------------------- |
| project\_type | string                 | Either "app" or "pipeline", based on the resource type to sync to |
| pipeline\_id  | string (pipeline only) | The Heroku pipeline ID to sync to                                 |
| stage         | string (pipeline only) | The Heroku pipeline stage to sync to                              |
| app\_id       | string (app only)      | The Heroku app ID to sync to                                      |

## Terraform Cloud

| Field                | Type                       | Description                                                                                         |
| :------------------- | :------------------------- | :-------------------------------------------------------------------------------------------------- |
| sync\_target         | string                     | Either "workspace" or "variableSet", based on the resource type to sync to                          |
| workspace\_id        | string (workspace only)    | The Terraform Cloud workspace ID to sync to                                                         |
| variable\_set\_id    | string (variable set only) | The Terraform Cloud variable set ID to sync to                                                      |
| variable\_sync\_type | string                     | Either "terraform" to sync secrets as Terraform variables or "env" to sync as environment variables |
| name\_transform      | string                     | A name transform to apply before syncing secrets: "none" or "lowercase"                             |

## Vercel

| Field           | Type              | Description                                                                                                                                                                                                        |
| :-------------- | :---------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| team\_id        | string            | The Vercel team ID to sync to, or "personal" for a personal account                                                                                                                                                |
| project\_id     | string            | The Vercel project ID to sync to                                                                                                                                                                                   |
| target\_id      | string            | The Vercel environment to sync to: "production", "preview", "development", or a custom environment ID                                                                                                              |
| preview\_branch | string (optional) | The git branch to scope the variables to (only used when `target_id` is set to "preview")                                                                                                                          |
| variable\_type  | string            | Either "config", "secret", or "dynamic". Dynamic syncs unmasked secrets as Config variables and masked or restricted secrets as Secret variables. The legacy values "encrypted" and "sensitive" are also accepted. |

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
    "/v3/configs/config/syncs": {
      "post": {
        "summary": "Create",
        "description": "Create a new secrets sync.",
        "operationId": "syncs-create",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "description": "The project slug",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "config",
            "in": "query",
            "description": "The config slug",
            "required": true,
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
                  "integration",
                  "data"
                ],
                "properties": {
                  "integration": {
                    "type": "string",
                    "description": "The integration slug which the sync will use"
                  },
                  "data": {
                    "type": "object",
                    "description": "Configuration data for the sync",
                    "properties": {}
                  },
                  "import_option": {
                    "type": "string",
                    "description": "An option indicating if and how Doppler should attempt to import secrets from the sync destination",
                    "default": "none",
                    "enum": [
                      "none",
                      "prefer_doppler",
                      "prefer_integration"
                    ]
                  },
                  "await_initial_sync": {
                    "type": "boolean",
                    "description": "Causes sync creation to wait for the initial sync to complete before returning.",
                    "default": false
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
                    "value": "{\n\t\"sync\": {\n  \t\"slug\": \"00000000-0000-0000-0000-000000000000\",\n  \t\"integration\": \"00000000-0000-0000-0000-000000000000\",\n    \"project\": \"backend\",\n    \"config\": \"prd\",\n    \"enabled\": true,\n    \"lastSyncedAt\": \"2023-08-01T00:00:00.000Z\"\n  }\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "sync": {
                      "type": "object",
                      "properties": {
                        "slug": {
                          "type": "string",
                          "example": "00000000-0000-0000-0000-000000000000"
                        },
                        "integration": {
                          "type": "string",
                          "example": "00000000-0000-0000-0000-000000000000"
                        },
                        "project": {
                          "type": "string",
                          "example": "backend"
                        },
                        "config": {
                          "type": "string",
                          "example": "prd"
                        },
                        "enabled": {
                          "type": "boolean",
                          "example": true,
                          "default": true
                        },
                        "lastSyncedAt": {
                          "type": "string",
                          "example": "2023-08-01T00:00:00.000Z"
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