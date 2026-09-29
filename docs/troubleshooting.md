# Troubleshooting

This guide explains common errors you may encounter when using the Customer Support API and how to resolve them.

## Common issues

The following sections cover common authentication, request, and resource errors.
## 401 Unauthorized

A `401 Unauthorized` response indicates that the API could not authenticate your request.

### Common causes

* The `Authorization` header is missing.
* The API key is invalid.
* The API key is incorrectly formatted.

### How to resolve it

Check that your request includes a valid API key in the `Authorization` header:

```text
Authorization: Bearer YOUR_API_KEY
```

Make sure there are no extra spaces or characters in the header and that you are using the correct API key.

## 404 Not Found

A `404 Not Found` response indicates that the requested resource could not be found.

### Common causes

* The customer ID is incorrect or does not exist.
* The ticket ID is incorrect or does not exist.
* The customer associated with a new ticket does not exist.

### How to resolve it

Check that the ID in your request is correct.

For example, when retrieving a customer:

```text
GET /v1/customers/cus_12345
```

Make sure that `cus_12345` is the ID of an existing customer.

If you are creating a ticket, also check that the `customer_id` in the request body refers to an existing customer.

## 400 Bad Request

A `400 Bad Request` response indicates that the request contains invalid or missing data.

### Common causes

* A required field is missing from the request body.
* A field contains an invalid value.
* The request body is not valid JSON.

### How to resolve it

Check the request body and make sure that all required fields are included.

For example, when creating a ticket, the following fields are required:

```json id="m5tq2f"
{
  "customer_id": "cus_12345",
  "subject": "Unable to access account",
  "description": "The customer cannot log in."
}
```

If you are updating a ticket, make sure that the `status` value is one of the accepted values:

* `open`
* `in_progress`
* `resolved`
