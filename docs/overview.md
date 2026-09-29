# API overview

The Customer Support API provides a set of endpoints for managing customer information, support tickets, and support history.

## Core resources

The API is organized around three main resources:

* **Customers** — information about customers using the support service.
* **Tickets** — support requests created by customers or support agents.
* **Support tickets** — support requests associated with a customer, which can be used to review previous support activity.

## Common workflows

Typical API workflows include:

1. Retrieve a customer's information.
2. Retrieve the customer's support tickets.
3. Create a support ticket.
4. Retrieve an existing ticket.
5. Update the status of a ticket.

## API format

The API uses HTTP requests and JSON responses.

Requests and responses use standard HTTP methods and status codes.

## Base URL

For this documentation demo, the API uses the following fictional base URL:

`https://api.example.com/v1`

> This is a fictional API created for documentation purposes. It is not a live service.
