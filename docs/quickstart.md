# Quickstart

This guide shows you how to make your first request to the Customer Support API.

## Before you start

You need:

* A valid API key
* A tool for making HTTP requests, such as cURL

## Make your first request

Retrieve a customer by ID using the `GET /v1/customers/{customer_id}` endpoint.

Run the following command:

```bash
curl https://api.example.com/v1/customers/cus_12345 \
  -H "Authorization: Bearer YOUR_API_KEY"
```

A successful request returns the customer's information:

```json
{
  "id": "cus_12345",
  "name": "Maria Silva",
  "email": "maria@example.com",
  "created_at": "2026-09-20T10:30:00Z"
}
```

A `200 OK` response indicates that the customer was successfully retrieved.

## Next steps

Now that you have made your first API request, explore the following documentation:

* [Authentication](authentication.md) — Learn how API keys are used to authenticate requests.
* [Customers](concepts/customers.md) — Learn about customer resources.
* [Tickets](concepts/tickets.md) — Learn about support tickets and ticket statuses.
* [API Reference](api-reference/endpoints.md) — Explore available endpoints, parameters, request examples, and response codes.
