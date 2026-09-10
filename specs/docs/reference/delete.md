---
updatedAt: 2025-10-01T15:36:52.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# Delete

Delete an identity

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
    "/v3/workplace/service_accounts/service_account/{service_account}/identities/identity/{identity}": {
      "delete": {
        "description": "",
        "operationId": "delete_v3workplaceservice_accountsservice_account{service_account}identitiesidentity{identity}",
        "responses": {
          "204": {
            "description": ""
          }
        },
        "parameters": [
          {
            "in": "path",
            "name": "service_account",
            "schema": {
              "type": "string"
            },
            "required": true
          },
          {
            "in": "path",
            "name": "identity",
            "schema": {
              "type": "string"
            },
            "required": true
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