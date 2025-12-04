**Simple Books API — Postman Collection**

This repository contains a Postman collection for the Simple Books API. It includes examples of API testing using GET, POST, PATCH, and DELETE requests, along with tests, variables, and workflow automation.

**What This Collection Does**
1. API Status Check

GET /status

Confirms the API is running

Tests status code 200 and "status": "OK"

2. Register API Client

POST /api-clients

Creates a new API client

Generates an access token used for authentication

Tests status code 201

3. Get Books (Multiple GET Requests)

Retrieve list of all books

Retrieve only non-fiction books (filtered)

Extracts the first available non-fiction book

Saves bookId as a global variable

Retrieve books with limits (3 books, 20 books)

Retrieve a single book by ID

Validates status 200

Checks that stock is above 0

Checks that price exists and is above 0

4. Create an Order (POST)

POST /orders

Requires Bearer Token using {{accessToken}}

Uses a random customer name

Saves orderId for later requests

Tests status code 201

5. Get Orders (GET)

Retrieve all orders

Retrieve a specific order

Requires Bearer Token

Tests status code 200

6. Update an Order (PATCH)

PATCH /orders/:orderId

Updates the customer name

Tests status code 204

7. Delete an Order (DELETE)

DELETE /orders/:orderId

Requires Bearer Token

Tests status code 204


**Test Case Types Included**

Status code checks (200, 201, 204)

Response body validation

Filtering array responses

Dynamic variables (bookId, orderId, accessToken) - I use environment variables to test in staging and QA environment and global variables for both.

Randomized input ({{$randomFullName}})

Workflow chaining (setNextRequest) I skip request to create API for an automated 2nd/3rd, etc. test run as it has been already created during 1st test run.
