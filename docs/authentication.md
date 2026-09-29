# Authentication

The Customer Support API uses API keys to authenticate requests.

## API keys

Each API request must include a valid API key in the `Authorization` header.

Use the following format:

```http
Authorization: Bearer YOUR_API_KEY
```

Replace `YOUR_API_KEY` with your API key.

## Example request

```http
GET /v1/customers/cus_12345
Authorization: Bearer YOUR_API_KEY
```

## Security

Keep your API key secure and do not expose it in client-side code, public repositories, or other publicly accessible locations.

Do not share your API key with other users.

## Authentication errors

If a request does not include a valid API key, the API returns:

```http
401 Unauthorized
```

A `401 Unauthorized` response indicates that the request could not be authenticated.
