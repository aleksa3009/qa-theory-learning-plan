# OpenAPI / Swagger

## 1. Definition & Purpose
OpenAPI (formerly Swagger) is a standard specification for describing REST APIs. It defines how an API works in a structured and machine-readable way, enabling consistent understanding, testing, and integration across teams.

For QA engineers, OpenAPI acts as a single source of truth for API behavior.

## 2. What OpenAPI Describes
OpenAPI specifications typically define:
- API endpoints (URLs)
- HTTP methods (GET, POST, PUT, DELETE)
- Request parameters (path, query, headers, body)
- Response definitions (status codes, headers, body schema)
- Authentication and authorization mechanisms

This removes ambiguity and reduces reliance on informal documentation.

## 3. Benefits for QA
OpenAPI provides several direct benefits for QA work:
1. Clear documentation of expected API behavior
2. Faster understanding of endpoints and data contracts
3. Ability to validate requests and responses against schemas
4. Improved collaboration with developers and other teams
5. Reduced risk of misaligned expectations between frontend, backend, and QA

## 4. Key Components
1. Paths (Endpoints)  
   Define available API routes.

2. Operations (Methods)  
   Specify allowed HTTP methods per endpoint.

3. Parameters  
   Inputs such as path variables, query parameters, headers, and request bodies.

4. Responses  
   Expected outputs, including status codes and response structures.

5. Schemas (Models)  
   Define the structure and data types of requests and responses.

6. Security  
   Describes authentication methods such as API keys, OAuth, or Basic Auth.

## 5. QA Use Cases
QA engineers commonly use OpenAPI for:
1. API exploration and understanding
2. Automated API test creation
3. Schema validation of responses
4. Mock server usage when backend is unavailable
5. Contract testing to ensure implementation matches specification

## 6. Tools Supporting OpenAPI
Common tools used with OpenAPI include:
- Swagger UI for interactive API exploration
- Swagger Editor for writing and editing specifications
- Swagger Codegen for generating clients or server stubs
- Postman or Insomnia for importing specs and creating tests

## 7. Best Practices for QA
- Review the OpenAPI specification before starting API testing
- Ensure all endpoints and responses are documented
- Validate responses against defined schemas
- Report mismatches between implementation and specification
- Keep specifications updated as the API evolves

## 8. Summary
OpenAPI simplifies API testing by providing clear, structured documentation and enforceable contracts. For QA, it improves test accuracy, speeds up onboarding, and reduces misunderstandings between teams.