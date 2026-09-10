---
updatedAt: 2025-05-29T17:01:37.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Download

Download Secrets

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
    "/v3/configs/config/secrets/download": {
      "get": {
        "summary": "Download",
        "description": "Download Secrets",
        "operationId": "secrets-download",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "description": "Unique identifier for the project object. Not required if using a Service Token.",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "config",
            "in": "query",
            "description": "Name of the config object. Not required if using a Service Token.",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "format",
            "in": "query",
            "schema": {
              "type": "string",
              "enum": [
                "json",
                "dotnet-json",
                "env",
                "yaml",
                "docker",
                "env-no-quotes"
              ],
              "default": "json"
            }
          },
          {
            "name": "name_transformer",
            "in": "query",
            "description": "Transform secret names to a different case",
            "schema": {
              "type": "string",
              "enum": [
                "camel",
                "upper-camel",
                "lower-snake",
                "tf-var",
                "dotnet",
                "dotnet-env",
                "lower-kebab"
              ]
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
              "format": "int32",
              "default": 1800
            }
          },
          {
            "name": "secrets",
            "in": "query",
            "description": "Comma-delimited list of secrets to include in the download. Defaults to all secrets if left unspecified.",
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
                    "value": "{\n  \"STRIPE\": \"sk_test_9YxLnoLDdvOPn2dfjBVPB\",\n  \"ALGOLIA\": \"N9TOPUCTO\",\n  \"DATABASE\": \"brian@aws.dynamodb.com:9876\",\n  \"USER\": \"brian\"\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "STRIPE": {
                      "type": "string",
                      "example": "sk_test_9YxLnoLDdvOPn2dfjBVPB"
                    },
                    "ALGOLIA": {
                      "type": "string",
                      "example": "N9TOPUCTO"
                    },
                    "DATABASE": {
                      "type": "string",
                      "example": "brian@aws.dynamodb.com:9876"
                    },
                    "USER": {
                      "type": "string",
                      "example": "brian"
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