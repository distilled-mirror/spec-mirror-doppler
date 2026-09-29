---
updatedAt: 2025-05-29T17:01:13.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Create

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
    "/v3/workplace/roles": {
      "post": {
        "summary": "Create",
        "description": "",
        "operationId": "workplace_roles-create",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "name",
                  "permissions"
                ],
                "properties": {
                  "name": {
                    "type": "string",
                    "description": "The name of the role"
                  },
                  "permissions": {
                    "type": "array",
                    "description": "An array containing the permissions the role has. Valid permissions are: `all_enclave_projects`, `all_enclave_projects_admin`, `analytics_dashboard`, `billing`, `billing_manage`, `change_request_policy_manage`, `change_request_policy_read`, `create_enclave_project`, `custom_roles_manage`, `ekm`, `enclave_inheritance`, `enclave_secrets_referencing`, `logs`, `logs_audit`, `service_account_api_tokens`, `service_account_api_tokens_manage`, `service_account_identities`, `service_account_identities_manage`, `service_accounts`, `service_accounts_manage`, `settings`, `settings_manage`, `team`, `team_manage`, `verified_domains`, `verified_domains_manage`, `workplace_default_environments_manage`, `workplace_default_environments_read`, `workplace_integrations_create`, `workplace_integrations_list`, `workplace_integrations_manage`, `workplace_integrations_read`",
                    "items": {
                      "type": "string"
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
                    "value": "{\n  \"role\": {\n    \"name\": \"custom\",\n    \"permissions\": [\"team\"],\n    \"identifier\": \"custom\",\n    \"created_at\": \"2023-08-01T00:00:00.000Z\",\n    \"is_custom_role\": true,\n    \"is_inline_role\": false\n\t}\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "role": {
                      "type": "object",
                      "properties": {
                        "name": {
                          "type": "string",
                          "example": "custom"
                        },
                        "permissions": {
                          "type": "array",
                          "items": {
                            "type": "string",
                            "example": "team"
                          }
                        },
                        "identifier": {
                          "type": "string",
                          "example": "custom"
                        },
                        "created_at": {
                          "type": "string",
                          "example": "2023-08-01T00:00:00.000Z"
                        },
                        "is_custom_role": {
                          "type": "boolean",
                          "example": true,
                          "default": true
                        },
                        "is_inline_role": {
                          "type": "boolean",
                          "example": false,
                          "default": true
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