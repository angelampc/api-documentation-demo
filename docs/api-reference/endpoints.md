# API Reference

## Customers

### Retrieve a customer

`GET /v1/customers/{customer_id}`

Retrieves information about a specific customer.

#### Path parameters

| Parameter     | Type   | Required | Description                            |
| ------------- | ------ | -------- | -------------------------------------- |
| `customer_id` | string | Yes      | The unique identifier of the customer. |

#### Example request

```bash
curl https://api.example.com/v1/customers/cus_12345 \
  -H "Authorization: Bearer YOUR_API_KEY"
```

#### Example response

```json
{
  "id": "cus_12345",
  "name": "Maria Silva",
  "email": "maria@example.com",
  "created_at": "2026-09-20T10:30:00Z"
}
```

#### Response

Returns the requested customer object.

| Status code        | Description                                |
| ------------------ | ------------------------------------------ |
| `200 OK`           | The customer was successfully retrieved.   |
| `401 Unauthorized` | The request could not be authenticated.    |
| `404 Not Found`    | The specified customer could not be found. |
