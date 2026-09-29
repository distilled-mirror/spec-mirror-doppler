---
updatedAt: 2025-05-29T17:00:57.000Z
agentTools:
  projectIndex: https://docs.doppler.com/llms.txt
---

# API Reference

The Doppler API is organized around REST. Our API has predictable resource-oriented URLs, accepts JSON-encoded request bodies, returns JSON-encoded responses, and uses standard HTTP response codes, authentication, and verbs.

## Authentication

Doppler's API uses high entropy tokens to authenticate requests.

> 🚧
>
> Tokens can carry many privileges, so be sure to keep them secure! Do not store your secret tokens in an `.env` file or share them in publicly accessible areas such as GitHub, client-side code, etc.

There are six types of tokens:

**CLI Tokens**

* Provide read/write access to all resources on your account
* Generated via the `login` command in the Doppler CLI

**Personal Tokens**

* Provide read/write access to all resources on your account
* Generated from the Tokens > Personal page on the Doppler Dashboard

**Service Tokens**

* Provide read or read/write access to secrets within a specific config
* Generated from the Project > Config > Access page on the Doppler Dashboard

**Service Account Tokens**

* Provide access to a granular set of resources within your workplace
* These tokens are attached to a Service Account
* [Read more](https://docs.doppler.com/docs/service-accounts) about generating Service Account Tokens

**Service Account Identity Tokens**

* Provide access to a granular set of resources within your workplace
* These short lived tokens are attached to a Service Account Identity and Service Account
* [Read more](https://docs.doppler.com/docs/service-account-identities) about obtaining Service Account Identity Tokens

**SCIM Tokens**:

* Provide read/write access to users and groups within your workplace. This may be used by your Identity Provider (IdP)
* Generated from the Tokens > SCIM page on the Doppler Dashboard (requires SCIM to be enabled)

**Audit Tokens**

* Provide read-only access to users and groups within your workplace
* Generated from the Tokens > Audit page on the Doppler Dashboard

All API requests must be made over HTTPS. Calls made over plain HTTP will redirect to HTTPS. API requests without authentication may also fail.

Authentication to the API is performed by providing a bearer token to the [HTTP Authorization](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization) header.

```shell Basic Auth
curl --request GET \
    --url 'https://api.doppler.com/v3/configs/config/secrets/download?format=json' \
    --header "Authorization: Bearer <TOKEN>"
```

## Rate Limits

Doppler's servers enforce rate limits to ensure our APIs remain responsive as we grow. These rate limits vary depending on your plan. The first rate limit is tied to an individual IP address and limits the number of requests that can be performed per minute. The second rate limit is tied to an individual API key. Most of the time these rate limits overlap but can differ when you take into account failed authorization attempts.

| Plan       | Reads/min | Secret reads/min | Writes/min |
| :--------- | :-------- | :--------------- | :--------- |
| Developer  | 240       | 120              | 60         |
| Team       | 480       | 240              | 120        |
| Enterprise | 480       | 480              | 240        |

### Rate Limit Headers

All API request responses include headers that provide information about your current rate limit. You can use these headers to know what rate limit is being applied, how many requests you have left, and when the limit reset will be happening. If you hit a rate limit, the API will respond with a 429 response code.

| Header Name             | Description                                                                        |
| :---------------------- | :--------------------------------------------------------------------------------- |
| `x-ratelimit-limit`     | Rate limit being applied to the current request (e.g., 480, 240, 120, 60).         |
| `x-ratelimit-remaining` | Number of requests remaining before the limit is hit.                              |
| `x-ratelimit-reset`     | Unix timestamp for when the limit bucket resets.                                   |
| `retry-after`           | Suggested wait period in seconds. This is only returned after a rate limit is hit. |

## Errors

Doppler uses conventional HTTP response codes to indicate the success or failure of an API request. In general, codes in the 2xx range indicate success, codes in the 4xx range indicate a client error (e.g. missing a required parameter), and codes in the 5xx range indicate an error with Doppler's servers.