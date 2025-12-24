# REST API Testing

## Introduction

REST API testing verifies that application programming interfaces work as intended and reliably connect frontend applications, backend services, and external systems. From a QA perspective, API testing focuses on validating business logic, data integrity, error handling, security, and performance without relying on the user interface. API tests are faster, more stable, and better suited for CI/CD pipelines than UI tests.

## Web Element Interaction

Not applicable. REST API testing interacts with endpoints via HTTP requests instead of UI elements.

## Locators

Not applicable. APIs are identified by URLs (endpoints) rather than DOM locators.

## Actions

QA engineers perform actions by sending HTTP requests:

* GET to retrieve data
* POST to create resources
* PUT to fully update resources
* PATCH to partially update resources
* DELETE to remove resources

## Assertions

Typical assertions in REST API testing include:

* HTTP status codes
* Response body fields and data types
* Response headers
* Schema validation against OpenAPI / JSON Schema
* Side effects (database records created, updated, or deleted)

## Key Features / Core Concepts

### 1. REST Fundamentals

REST (Representational State Transfer) is an architectural style based on resources identified by URLs. APIs are stateless, meaning each request must contain all information required to process it.

HTTP methods:

* GET: Retrieves data without modifying server state (safe and idempotent).
* POST: Creates new resources (non-idempotent).
* PUT: Replaces an entire resource (idempotent).
* PATCH: Updates specific fields of a resource.
* DELETE: Removes a resource (idempotent in most designs).

Headers such as Content-Type, Accept, and Authorization define data format and security. Responses are usually JSON.

### 2. HTTP Status Codes

Status codes indicate request outcomes and are critical for QA validation.

* 2xx Success

  * 200 OK: Successful retrieval.
  * 201 Created: Resource created, often with Location header.
  * 204 No Content: Successful action with no response body.

* 3xx Redirection

  * 301 Moved Permanently: Resource redirect.

* 4xx Client Errors

  * 400 Bad Request: Invalid or malformed request.
  * 401 Unauthorized: Missing or invalid authentication.
  * 403 Forbidden: Insufficient permissions.
  * 404 Not Found: Resource does not exist.
  * 409 Conflict: Request conflicts with current state.
  * 422 Unprocessable Entity: Validation errors.

* 5xx Server Errors

  * 500 Internal Server Error
  * 502 Bad Gateway
  * 503 Service Unavailable

### 3. Headers and HTTP Mechanics

Headers provide metadata for requests and responses. QA should validate:

* Content-Type and Accept handling
* Authorization headers (Bearer, Basic, API keys)
* Security headers and CORS behavior
* Rate limiting and caching headers (ETag, X-RateLimit-*)

### 4. Pagination, Sorting, and Filtering

Large datasets require pagination. QA should test:

* Page/size or limit/offset parameters
* Boundary cases (first, last, empty pages)
* Sorting order (ascending/descending)
* Filtering combinations and invalid filters

### 5. Idempotency and Safe Methods

* Safe methods (GET) must not change server state.
* Idempotent methods (PUT, DELETE) must produce the same result when repeated.
  QA should send duplicate requests and verify consistent behavior.

### 6. Asynchronous Endpoints

Some APIs process requests asynchronously:

* Return 202 Accepted
* Provide status endpoints for polling
* Use webhooks for completion notifications
  QA should validate polling logic, retries, and error handling.

### 7. Security and Authentication

API security testing includes:

* Authentication (Basic Auth, Bearer tokens, OAuth2)
* Authorization and role-based access control
* HTTPS enforcement
* Input validation to prevent injection attacks
* Rate limiting and protection against abuse

### 8. Contract and Schema Testing

APIs must conform to their contracts:

* Validate responses against OpenAPI / Swagger definitions
* Use JSON Schema to assert required fields, data types, and formats
* Detect breaking changes early using contract tests

### 9. Performance Testing

Performance testing evaluates:

* Response time (p95, p99)
* Throughput
* Error rates under load
  Tools like JMeter, k6, and Gatling simulate realistic traffic patterns.

### 10. Test Data and Environment Management

Stable API testing requires:

* Dedicated test or staging environments
* Deterministic and isolated test data
* Unique data for parallel execution
* Cleanup after tests to avoid data pollution

### 11. Flaky Tests

Flaky API tests pass or fail inconsistently. Common causes include timing issues, shared data, and unstable dependencies. QA should isolate tests, mock external services, and track flaky tests in CI reports.

## Tools and Practical Examples

### Postman

Postman enables:

* Request collections and environments
* Pre-request scripts for dynamic data
* Assertions in the Tests tab
* Newman CLI execution in CI/CD

### curl

curl is used for quick manual testing and debugging of HTTP requests from the command line.

### Automation Frameworks

* Java: RestAssured
* Python: pytest + requests
* JavaScript: SuperTest
  These frameworks integrate API tests into CI/CD pipelines.

## CI/CD Integration

API tests should run automatically on each commit or pull request. Critical failures must fail the build. Test reports should be archived and monitored as quality gates.

## Practical QA Tips

* Always assert both status codes and response bodies
* Validate schemas, not just values
* Avoid hardcoded credentials
* Clean up test data
* Prefer API tests over UI tests for core logic

## Summary

REST API testing is a core QA skill that ensures reliable communication between system components. By validating functionality, security, performance, and contracts at the API level, QA engineers can detect defects early, stabilize CI pipelines, and support confident release decisions.