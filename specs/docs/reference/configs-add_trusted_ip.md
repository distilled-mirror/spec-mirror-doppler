---
updatedAt: 2025-05-29T17:01:35.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Add

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
    "/v3/configs/config/trusted_ips": {
      "post": {
        "summary": "Add",
        "description": "",
        "operationId": "configs-add_trusted_ip",
        "parameters": [
          {
            "name": "project",
            "in": "query",
            "required": true,
            "schema": {
              "type": "string"
            }
          },
          {
            "name": "config",
            "in": "query",
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
                  "ip"
                ],
                "properties": {
                  "ip": {
                    "type": "string",
                    "description": "An IP address or CIDR range"
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
                  "IP added": {
                    "value": "{\n  \"ip\": \"0.0.0.0/0\"\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "ip": {
                      "type": "string",
                      "example": "0.0.0.0/0"
                    }
                  }
                }
              }
            }
          },
          "204": {
            "description": "204",
            "content": {
              "application/json": {
                "examples": {
                  "IP exists": {
                    "value": ""
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