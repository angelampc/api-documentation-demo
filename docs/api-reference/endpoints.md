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

### Retrieve customer tickets

`GET /v1/customers/{customer_id}/tickets`

Retrieves all support tickets associated with a specific customer.

#### Path parameters

| Parameter     | Type   | Required | Description                            |
| ------------- | ------ | -------- | -------------------------------------- |
| `customer_id` | string | Yes      | The unique identifier of the customer. |

#### Example request

```bash
curl https://api.example.com/v1/customers/cus_12345/tickets \
  -H "Authorization: Bearer YOUR_API_KEY"
```

#### Example response

```json
{
  "data": [
    {
      "id": "tic_67890",
      "customer_id": "cus_12345",
      "subject": "Unable to access account",
      "description": "The customer cannot log in.",
      "status": "open",
      "created_at": "2026-09-29T09:15:00Z",
      "updated_at": "2026-09-29T09:15:00Z"
    },
    {
      "id": "tic_67891",
      "customer_id": "cus_12345",
      "subject": "Billing question",
      "description": "The customer has a question about their latest invoice.",
      "status": "resolved",
      "created_at": "2026-09-25T14:20:00Z",
      "updated_at": "2026-09-26T10:05:00Z"
    }
  ]
}
```

#### Response

Returns a list of support tickets associated with the specified customer.

| Status code        | Description                                         |
| ------------------ | --------------------------------------------------- |
| `200 OK`           | The customer's tickets were successfully retrieved. |
| `401 Unauthorized` | The request could not be authenticated.             |
| `404 Not Found`    | The specified customer could not be found.          |

### Create a ticket

`POST /v1/tickets`

Creates a new support ticket for a customer.

#### Request body

| Parameter     | Type   | Required | Description                                    |
| ------------- | ------ | -------- | ---------------------------------------------- |
| `customer_id` | string | Yes      | The unique identifier of the customer.         |
| `subject`     | string | Yes      | A short summary of the support request.        |
| `description` | string | Yes      | A detailed description of the support request. |

#### Example request

```bash
curl -X POST https://api.example.com/v1/tickets \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "customer_id": "cus_12345",
    "subject": "Unable to access account",
    "description": "The customer cannot log in."
  }'
```

#### Example response

```json
{
  "id": "tic_67892",
  "customer_id": "cus_12345",
  "subject": "Unable to access account",
  "description": "The customer cannot log in.",
  "status": "open",
  "created_at": "2026-09-29T14:30:00Z",
  "updated_at": "2026-09-29T14:30:00Z"
}
```

#### Response

Returns the newly created ticket.

| Status code        | Description                                   |
| ------------------ | --------------------------------------------- |
| `201 Created`      | The ticket was successfully created.          |
| `400 Bad Request`  | The request contains invalid or missing data. |
| `401 Unauthorized` | The request could not be authenticated.       |
| `404 Not Found`    | The specified customer could not be found.    |


