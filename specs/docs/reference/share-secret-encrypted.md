---
updatedAt: 2025-05-29T17:02:08.000Z
---

Fetch the complete documentation index at: https://docs.doppler.com/llms.txt. Use this file to discover all available pages before exploring further. Append .md to any documentation page URL to get its markdown version.

# E2E Encrypted

Generate a Doppler Share link by sending an encrypted secret. The receive flow the user goes through will be end-to-end encrypted where the encrypted secret will be decrypted on the browser.

## Encryption Examples

```javascript Node.js
// Imports
const crypto = require("crypto");
const pbkdf2Async = util.promisify(crypto.pbkdf2);

// Constants
const algorithm = "aes-256-gcm";
const keyLength = 256 / 8;
const ivLength = 12;
const saltLength = 16;
const saltRounds = 100000;
const authTagLength = 16;

// Encryption
async function encrypt(plainText) {
  // Generate Password
  const password = crypto.randomBytes(32).toString("hex");
  const hashedPassword = crypto.createHash("sha256").update(password).digest("hex");

  // Derive key with PBKD2
  const salt = crypto.randomBytes(saltLength);
  const iv = crypto.randomBytes(ivLength);
  const key = await pbkdf2Async(password, salt, saltRounds, keyLength, "sha256");
  
  // Encrypt plain text
  const cipher = crypto.createCipheriv(algorithm, key, iv);
  const encryptedData = Buffer.concat([cipher.update(plainText, "utf8"), cipher.final()]);
  const authTag = cipher.getAuthTag();

  return {
    encrypted_secret: Buffer.concat([salt, iv, authTag, encryptedData]).toString("base64"),
    password: password,
    hashedPassword: hashedPassword
  };
}

// Testing
encrypt("SECRET TO ENCRYPT").then(payload => {
  console.log(payload);
})
```
```javascript Browser
class CryptoLib {
  constructor() {
    this._encoder = new TextEncoder();
    this._decoder = new TextDecoder();
    this._saltRounds = 100000;
    this._keyLength = 256;
    this._ivLength = 12;
    this._saltLength = 16;
    this._authTagLength = 16;
  }

  randomString(length) {
    const validChars = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789";
    let array = this.randomArray(length);
    array = array.map((x) => validChars.charCodeAt(x % validChars.length));
    return String.fromCharCode(...array);
  }

  randomArray(length) {
    return window.crypto.getRandomValues(new Uint8Array(length));
  }

  // Source: https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/digest#converting_a_digest_to_a_hex_string
  async sha256(text) {
    const msgUint8 = this._encoder.encode(text); // encode as (utf-8) Uint8Array
    const hashBuffer = await crypto.subtle.digest("SHA-256", msgUint8); // hash the message
    const hashArray = Array.from(new Uint8Array(hashBuffer)); // convert buffer to byte array
    const hashHex = hashArray.map((b) => b.toString(16).padStart(2, "0")).join(""); // convert bytes to hex string
    return hashHex;
  }

  async generatePassword() {
    const password = this.randomString(64);

    return {
      password: password,
      hashedPassword: await this.sha256(password),
    };
  }

  async encrypt(secret) {
    const { password, hashedPassword } = await this.generatePassword();
    const salt = this.randomArray(this._saltLength);
    const iv = this.randomArray(this._ivLength);
    const aesKey = await this._deriveKey(password, salt, this._saltRounds, ["encrypt"]);
    const encryptedContent = await window.crypto.subtle.encrypt(
      {
        name: "AES-GCM",
        iv: iv,
        tagLength: this._authTagLength * 8,
      },
      aesKey,
      this._encoder.encode(secret)
    );
    const authTag = new Uint8Array(encryptedContent.slice(encryptedContent.byteLength - this._authTagLength));
    const encryptedContentArray = new Uint8Array(encryptedContent.slice(0, encryptedContent.byteLength - this._authTagLength));
    const buffer = new Uint8Array(salt.byteLength + iv.byteLength + authTag.byteLength + encryptedContentArray.byteLength);
    buffer.set(salt, 0);
    buffer.set(iv, salt.byteLength);
    buffer.set(authTag, salt.byteLength + iv.byteLength);
    buffer.set(encryptedContentArray, salt.byteLength + iv.byteLength + authTag.byteLength);

    return {
      encryptedSecret: this._bufferToBase64(buffer),
      password: password,
      hashedPassword: hashedPassword,
      kdf: "pbkdf2",
      saltRounds: this._saltRounds,
    };
  }

  async _deriveKey(password, salt, saltRounds, keyUsage) {
    const passwordKey = await window.crypto.subtle.importKey("raw", this._encoder.encode(password), "PBKDF2", false, [
      "deriveKey",
    ]);

    return window.crypto.subtle.deriveKey(
      {
        name: "PBKDF2",
        salt: salt,
        iterations: saltRounds,
        hash: "SHA-256",
      },
      passwordKey,
      { name: "AES-GCM", length: this._keyLength },
      false,
      keyUsage
    );
  }

  _bufferToBase64(buffer) {
    return btoa(String.fromCharCode.apply(null, buffer));
  }
}

// Testing
const cryptoLib = new CryptoLib();
cryptoLib.encrypt("SECRET TO ENCRYPT").then(payload => {
  console.log(payload);
})
```

# OpenAPI definition

```json
{
  "openapi": "3.1.0",
  "info": {
    "title": "share",
    "version": "4"
  },
  "servers": [
    {
      "url": "https://api.doppler.com"
    }
  ],
  "components": {
    "securitySchemes": {
      "sec0": {
        "type": "http",
        "scheme": "basic"
      }
    }
  },
  "security": [
    {
      "sec0": []
    }
  ],
  "paths": {
    "/v1/share/secrets/encrypted": {
      "post": {
        "summary": "E2E Encrypted",
        "description": "Generate a Doppler Share link by sending an encrypted secret. The receive flow the user goes through will be end-to-end encrypted where the encrypted secret will be decrypted on the browser.",
        "operationId": "share-secret-encrypted",
        "requestBody": {
          "content": {
            "application/json": {
              "schema": {
                "type": "object",
                "required": [
                  "encrypted_secret",
                  "hashed_password",
                  "encryption_kdf",
                  "encryption_salt_rounds"
                ],
                "properties": {
                  "encrypted_secret": {
                    "type": "string",
                    "description": "Ecrypted secret using AES-GCM with a symmetric key derived from a cryptographically random 64 character passphrase using PBKDF2. 1,000,000 salt rounds required. Then base64 encode the encrypted secret.",
                    "default": "<BASE64 ENCODED, ENCRYPTED SECRET>"
                  },
                  "hashed_password": {
                    "type": "string",
                    "description": "SHA256 hash of the password. This is NOT the hash of the derived encryption key.",
                    "default": "<SHA256 HASH>"
                  },
                  "expire_views": {
                    "type": "integer",
                    "description": "Number of views before the link expires. Valid ranges: 1 to 50. -1 for unlimited.",
                    "default": 1,
                    "format": "int32"
                  },
                  "expire_days": {
                    "type": "integer",
                    "description": "Number of days before the link expires. Valid range: 1 to 90.",
                    "default": 1,
                    "format": "int32"
                  },
                  "encryption_kdf": {
                    "type": "string",
                    "description": "The key derivation function used. Must by \"pbkdf2\".",
                    "default": "pbkdf2"
                  },
                  "encryption_salt_rounds": {
                    "type": "integer",
                    "description": "Number of salt rounds used by KDF. Must be \"1000000\".",
                    "default": 1000000,
                    "format": "int32"
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
                    "value": "{\n  \"url\": \"https://share.doppler.com/s/oarjigpajqtodoqefoua9o1iisdfaocgfbulmaez#GZPgKEngtasgXHftCjimCwjPquZV7qwwzo8qb1m7rgvjlWXFr8C5jHOuXtxW1SBC\",\n  \"success\": true\n}"
                  }
                },
                "schema": {
                  "type": "object",
                  "properties": {
                    "url": {
                      "type": "string",
                      "example": "https://share.doppler.com/s/oarjigpajqtodoqefoua9o1iisdfaocgfbulmaez#GZPgKEngtasgXHftCjimCwjPquZV7qwwzo8qb1m7rgvjlWXFr8C5jHOuXtxW1SBC"
                    },
                    "success": {
                      "type": "boolean",
                      "example": true,
                      "default": true
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