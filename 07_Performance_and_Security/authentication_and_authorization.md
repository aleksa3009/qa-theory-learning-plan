# Authentication & Authorization

## 1. Authentication vs Authorization

Authentication is the process of verifying a user's identity. It answers the question "Who are you?" and ensures that the person or system accessing the application is legitimate. This is usually done by validating credentials such as a username and password, an API token, or biometric data. From a QA perspective, authentication must reliably block unauthorized users while allowing valid users to log in without friction.

Authorization defines what an authenticated user is allowed to do within the system. It answers the question "What can you access and what actions can you perform?" Even after successful authentication, users must be restricted based on their role, permissions, or attributes. QA engineers must verify that authorization rules are enforced consistently across UI and API layers.

In practice, authentication always happens first, followed by authorization. Both must be tested together to ensure users can access only the resources that are explicitly allowed.

## 2. Common Authentication Mechanisms

### 2.1 Basic Authentication

Basic Authentication uses a username and password encoded with Base64 and sent in the HTTP Authorization header. While it is easy to implement, it is not secure unless combined with HTTPS, because credentials can be intercepted if transmitted over plain HTTP.

From a QA perspective, tests should verify that invalid credentials are rejected, valid credentials succeed, and that the application enforces HTTPS. QA should also ensure that credentials are never logged or exposed in error messages.

### 2.2 API Tokens / API Keys

API tokens or API keys are unique identifiers used to authenticate requests made to an API. They are typically passed in request headers and sometimes scoped to specific permissions or services.

QA should test scenarios where tokens are missing, expired, revoked, or invalid. It is also important to verify that token permissions are enforced correctly and that a token cannot access endpoints outside its allowed scope.

### 2.3 OAuth 2.0

OAuth 2.0 is an industry-standard protocol used for authentication and authorization, especially when integrating with third-party providers. Users authenticate through an authorization server, which issues access tokens that are used to access protected resources.

QA testing should focus on validating access token expiration, refresh token behavior, scope enforcement, and correct handling of unauthorized access. It is also important to test error responses and ensure sensitive token data is not exposed.

## 3. Authorization Mechanisms

Role-Based Access Control (RBAC) assigns permissions based on predefined roles such as admin, user, or guest. Each role has clearly defined capabilities. QA should verify that each role can perform only its allowed actions.

Attribute-Based Access Control (ABAC) determines access based on attributes such as user properties, resource type, or environmental conditions. This allows more flexible and granular authorization. QA must validate different attribute combinations and confirm access decisions are correct.

Authorization testing should include checks for privilege escalation, access to restricted endpoints, and behavior after role changes or session expiration.

## 4. QA Testing Strategies

Positive testing ensures that valid users with correct permissions can access allowed resources and perform expected actions without errors.

Negative testing focuses on invalid credentials, expired tokens, insufficient permissions, and attempts to access restricted resources. These tests verify that the system correctly blocks unauthorized actions.

Session testing validates logout behavior, session expiration, token refresh logic, and protection against session reuse.

Boundary testing includes extreme values such as long passwords, special characters, and multiple concurrent sessions to ensure stability and security.

Security testing ensures sensitive data such as passwords and tokens are encrypted, error messages do not leak information, and unauthorized access is consistently blocked.

## 5. Best Practices for QA

QA engineers should document all authentication flows and authorization rules to ensure consistent coverage. Automated tests should be used to validate access control, especially for APIs and CI/CD pipelines.

Monitoring failed login attempts and access logs helps detect unusual behavior. QA should collaborate with security teams for penetration testing and vulnerability assessments. Integration with third-party authentication providers such as OAuth or SSO must be tested thoroughly to ensure both security and usability.

## 6. Summary

Authentication verifies identity, while authorization controls access. Both are critical for application security. QA engineers must understand different authentication mechanisms and authorization models, and apply systematic testing strategies to prevent unauthorized access, protect sensitive data, and ensure reliable system behavior.