# Non-Functional Testing

Non-functional testing focuses on how the system operates rather than what it does. While functional testing validates feature correctness, non-functional testing evaluates system quality attributes such as performance, security, usability, reliability, scalability, and maintainability. This ensures that the product is fast, stable, secure, and user-friendly under different conditions. It is usually performed after functional testing, but some categories (e.g., security and performance testing) may run in parallel.

## 1. Performance Testing

Performance testing assesses system behavior under different workloads and stress conditions. The goal is to detect bottlenecks, latency issues, and stability concerns.

### 1.1 Load Testing

• Evaluates system behavior under expected, typical loads.
• Example: 500 concurrent users accessing the website.
• Measures response times, throughput, and server utilization.

### 1.2 Stress Testing

• Determines system behavior under extreme load beyond expectations.
• Identifies breaking points and tests recovery mechanisms.

### 1.3 Spike Testing

• Assesses system response to sudden, extreme increases or decreases in user activity.
• Example: sudden surge during a flash sale.

### 1.4 Endurance / Soak Testing

• Runs the system under normal load for extended periods.
• Detects memory leaks, CPU exhaustion, and performance degradation over time.

### 1.5 Scalability Testing

• Evaluates performance when resources or load increase.
• Checks if response times and throughput remain acceptable with scaling.

## 2. Security Testing

Security testing ensures protection against threats, unauthorized access, and vulnerabilities, preserving confidentiality, integrity, and availability.

### 2.1 Authentication & Authorization Testing

• Verifies users log in correctly and access only allowed resources.

### 2.2 Vulnerability Scanning

• Automated detection of known security weaknesses.

### 2.3 Penetration Testing

• Ethical hacking to identify exploitable vulnerabilities.

### 2.4 Data Security Testing

• Ensures encryption, secure transmission, and storage of sensitive data.

### 2.5 Session Management Testing

• Validates session expiration, token security, and multi-factor authentication.

### 2.6 Input Validation Testing

• Prevents attacks such as XSS, SQL injection, CSRF, etc.

## 3. Usability Testing

Usability testing evaluates the user experience and ease of interaction with the product.

Checks include:
• UI clarity and consistency
• Navigation simplicity
• Accessibility (contrast, screen reader compatibility, keyboard navigation)
• Error message clarity and helpfulness
• Learning curve and intuitiveness

## 4. Compatibility Testing

Compatibility testing ensures the system works consistently across different environments.

Types include:
• Browser compatibility: Chrome, Firefox, Safari, Edge
• Device compatibility: Mobile, tablet, desktop
• OS compatibility: Windows, macOS, Linux, Android, iOS
• Network compatibility: 3G, 4G, unstable networks
• Version compatibility: backward/forward support

## 5. Reliability & Stability Testing

Reliability testing verifies consistent performance; stability testing ensures continuous operation over time.

Includes:
• Recovery after crashes or failures
• Stability under load
• Monitoring error rates and failure points
• Ensuring no data loss or corruption

## 6. Localization & Internationalization Testing

Ensures the system works correctly across languages, regions, and cultures.

Internationalization (I18N):
• System supports multiple languages without code changes

Localization (L10N):
• Accurate translations, date/time formats, currency, and UI cultural adjustments

## 7. Accessibility Testing

Accessibility testing ensures usability for people with disabilities.

Checks include:
• Screen reader support
• Proper ARIA labels
• Keyboard-only navigation
• Compliance with WCAG color contrast and other standards

## 8. Maintainability & Portability Testing

### Maintainability

• Evaluates how easily the system can be updated or fixed
• Checks code modularity, documentation, and ease of modification

### Portability

• Ensures smooth deployment across platforms, cloud environments, or database systems

## 9. Summary

Non-functional testing focuses on system performance, reliability, security, usability, and overall user experience. It answers questions such as:
• Is the system fast and responsive?
• Is it secure?
• Can it handle growth?
• Is it accessible and user-friendly?
• Will it remain stable over long-term usage?

Combined with functional testing, non-functional testing ensures the product is robust, efficient, and production-ready.