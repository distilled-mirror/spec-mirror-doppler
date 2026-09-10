---
updatedAt: 2025-05-29T17:01:22.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Update

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
    "/v3/projects/roles/role/{role}": {
      "patch": {
        "summary": "Update",
        "description": "",
        "operationId": "project_roles-update",
        "parameters": [
          {
            "name": "role",
            "in": "path",
            "description": "The role's unique identifier",
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
                  "name": {
                    "type": "string",
                    "description": "The name of the role"
                  },
                  "permissions": {
                    "type": "array",
                    "description": "An array containing the permissions the role has. Valid permissions are: `enclave_config_access_logs`, `enclave_config_change_request_policy_manage`, `enclave_config_change_request_review`, `enclave_config_logs`, `enclave_config_secrets_referencing`, `enclave_config_syncs_manage`, `enclave_config_toggle_inheritable`, `enclave_project_config_create`, `enclave_project_config_delete`, `enclave_project_config_duplicate`, `enclave_project_config_dynamic_secrets_leases_write`, `enclave_project_config_dynamic_secrets_manage`, `enclave_project_config_dynamic_secrets_read`, `enclave_project_config_lock`, `enclave_project_config_logs_rollback`, `enclave_project_config_rename`, `enclave_project_config_rotated_secrets_manage`, `enclave_project_config_rotated_secrets_read`, `enclave_project_config_secrets_read`, `enclave_project_config_secrets_write`, `enclave_project_config_service_tokens`, `enclave_project_config_trusted_ips`, `enclave_project_delete`, `enclave_project_environment_all`, `enclave_project_environment_create`, `enclave_project_environment_delete`, `enclave_project_environment_list_all`, `enclave_project_environment_order`, `enclave_project_environment_rename`, `enclave_project_environment_settings_manage`, `enclave_project_inheritance`, `enclave_project_members`, `enclave_project_rename`, `enclave_project_secrets_notes_manage`, `enclave_project_secrets_referencing`, `enclave_project_webhooks`, `enclave_secret_reminders`",
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
                    "value": "{\n  \"role\": {\n    \"name\": \"custom\",\n    \"permissions\": [\"enclave_config_logs\"],\n    \"identifier\": \"custom\",\n    \"created_at\": \"2023-08-01T00:00:00.000Z\",\n    \"is_custom_role\": true\n\t}\n}"
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
                            "example": "enclave_config_logs"
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
                        }
                      }
                    }
                  }
                }
              }
            }
          },
          "404": {
            "description": "404",
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