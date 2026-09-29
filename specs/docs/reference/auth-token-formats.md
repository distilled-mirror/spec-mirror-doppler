---
updatedAt: 2025-05-29T17:01:01.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# Auth Token Formats

Doppler supports various auth tokens for different purposes. Each token uses a unique format to assist with secret scanning/identification.

### CLI Token

Format: `/dp\.ct\.[a-zA-Z0-9]{40,44}/`\
Example: `dp.ct.bAqhcVzrhy5cRHkOlNTc0Ve6w5NUDCpcutm8vGE9myi`

### Personal Token

Format: `/dp\.pt\.[a-zA-Z0-9]{40,44}/`\
Example: `dp.pt.bAqhcVzrhy5cRHkOlNTc0Ve6w5NUDCpcutm8vGE9myi`

### Service Token

Format: `/dp\.st\.(?:[a-z0-9\-_]{2,35}\.)?[a-zA-Z0-9]{40,44}/`\
Example: `dp.st.dev.bAqhcVzrhy5cRHkOlNTc0Ve6w5NUDCpcutm8vGE9myi`

### Service Account Token

Format: `/dp\.sa\.[a-zA-Z0-9]{40,44}/`\
Example: `dp.sa.bAqhcVzrhy5cRHkOlNTc0Ve6w5NUDCpcutm8vGE9myi`

### Service Account Identity Token (short lived)

Format: `/dp\.said\.[a-zA-Z0-9]{40,44}/`\
Example: `dp.said.bAqhcVzrhy5cRHkOlNTc0Ve6w5NUDCpcutm8vGE9myi`

### SCIM Token

Format: `/dp\.scim\.[a-zA-Z0-9]{40,44}/`\
Example: `dp.scim.bAqhcVzrhy5cRHkOlNTc0Ve6w5NUDCpcutm8vGE9myi`

### Audit Token

Format: `/dp\.audit\.[a-zA-Z0-9]{40,44}/`\
Example: `dp.audit.bAqhcVzrhy5cRHkOlNTc0Ve6w5NUDCpcutm8vGE9myi`