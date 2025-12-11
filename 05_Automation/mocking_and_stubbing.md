# Mocking and Stubbing

## 1. Definition & Purpose
Mocking and Stubbing are techniques for simulating dependencies in software testing. They allow testing your code without relying on real external services, such as APIs, databases, or third-party systems.

- **Mock:** An object that imitates the behavior of a real service and can verify interactions.
- **Stub:** An object that returns predefined responses, often used when a service is unavailable.

**Why they matter:**
- Enable isolated testing of functionality.
- Reduce dependency on external services.
- Help test edge cases and error scenarios.
- Lower testing costs and improve maintainability.

## 2. Mock vs Stub

| Feature | Mock | Stub |
|---------|------|------|
| Purpose | Verifies interaction with a dependency | Returns predefined results |
| Focus | Method calls and arguments | Output of the method |
| Usage | When checking communication with a service | When a service is unavailable or unstable |

## 3. Practical Examples

**Mock example:**
- Testing a function that fetches a user's name from an API.
- Mock simulates the API response.
- Verifies that the function calls the service with expected arguments.

**Stub example:**
- Testing a function that returns weather description from an API.
- Stub returns a predefined response.
- Useful when the service is unreliable or unavailable.

## 4. Best Practices

**Mocking**
- Keep mocks simple and understandable.
- Use realistic data.
- Test multiple scenarios, including error and edge cases.
- Avoid over-mocking to maintain test maintainability.

**Stubbing**
- Define expected outputs for each method.
- Keep stubs up-to-date when code changes.
- Avoid tight coupling between tests and stubs.

## 5. When to Use Mock vs Stub
- **Mock:** When you want to verify interaction with an external service.
- **Stub:** When a service is unavailable or hard to test, and you need controlled outputs.

## 6. Tips and Tricks
- Start with simple functions and API calls.
- Gradually include edge cases and error scenarios.
- Combine mocks and stubs in complex tests when needed.
- Always ensure mocks and stubs reflect realistic production scenarios.

## 7. Mini Practical Example
- `fetchMocker.mockResponseOnce(JSON.stringify(mockData))`
- Calling function returns expected mock object.
- `expect(...).toStrictEqual(...)` verifies the output matches the mock.

**Key points:**
- Mock verifies interaction.
- Stub provides controlled outputs.
- Both help isolate tests and ensure reliable QA coverage.
