# Playwright

## 1. Introduction

Playwright is a modern end-to-end testing tool developed by Microsoft. Its main purpose is to enable fast, reliable, and automated testing of web applications across multiple browsers:
• Chromium (Chrome, Edge)
• Firefox
• WebKit (Safari)

Playwright allows QA engineers to write stable, scalable tests that work consistently across browsers. It provides advanced capabilities for interacting with web elements, handling asynchronous operations, and performing cross-browser testing.

From a QA perspective, Playwright ensures high test reliability, reduces flakiness, and facilitates CI/CD integration.

## 2. Web Element Interaction

Playwright provides a clear API for interacting with elements on a page. It includes automatic waiting and multiple action types.

### 2.1 Locators

Common locator strategies:
• CSS selectors
• Text selectors
• XPath
• Role selectors (for accessibility)

Example:

```js
const usernameInput = page.locator('#username');
const loginButton = page.locator('text=Login');
```

### 2.2 Actions

Basic interactions:

```js
await usernameInput.fill('testuser');
await loginButton.click();
await page.hover('#profile-menu');
await page.check('#remember-me');
await page.selectOption('#country', 'US');
```

Auto-wait ensures actions are performed only when elements are ready.

### 2.3 Assertions

Playwright supports assertions for element state and content:

```js
await expect(page.locator('#dashboard')).toBeVisible();
await expect(page.locator('#username')).toHaveValue('testuser');
await expect(page.locator('text=Logout')).toBeEnabled();
```

Assertions are integrated with retries to reduce flakiness.

## 3. Core Features

### 3.1 Multi-Browser Support

• Tests can run in Chromium, Firefox, and WebKit without extra configuration.
• Enables cross-browser verification of UI behavior.

### 3.2 Automatic Waiting

• Playwright automatically waits for elements to be visible, enabled, or attached to the DOM.
• Eliminates most manual sleep() calls.

Example:

```js
await page.click('#login-button'); // Waits until interactable
```

### 3.3 Parallel Testing

• Playwright supports parallel execution using multiple browser contexts or workers.
• Each test runs in isolation.

Example configuration (Node.js + Jest):

```js
module.exports = {
  browsers: ["chromium", "firefox", "webkit"],
  exitOnPageError: false,
  launchOptions: { headless: true },
};
```

Parallel execution is ideal for CI/CD pipelines.

### 3.4 Network Interception

• Allows intercepting and mocking API requests.
• Useful for deterministic testing.

Example:

```js
await page.route('**/api/users', route => {
  route.fulfill({ json: [{ id: 1, name: 'Alice' }] });
});
```

### 3.5 Multiple Browser Contexts

• Isolate sessions in the same test.
• Supports multi-user scenarios.

### 3.6 File Upload and Download

• Supports testing file interactions.
• Ensures QA can validate upload/download flows.

### 3.7 Advanced Simulations

• Geolocation and permissions testing
• Device emulation
• Offline mode simulation

## 4. Advantages

• Reliable and stable test execution
• Cross-browser support including Safari
• Parallel execution for faster test runs
• Automatic waiting reduces flakiness
• Supports multiple languages: JavaScript, TypeScript, Python, Java, .NET
• Integrated debugging tools and screenshots for failures

## 5. Limitations

• Smaller ecosystem compared to Selenium
• Some advanced features require configuration
• Learning curve for complex scenarios
• Limited support for legacy browsers

## 6. Test Structure and Organization

Recommended folder structure:
• tests/ - end-to-end test files
• fixtures/ - static test data in JSON
• helpers/ - reusable functions
• playwright.config.js - configuration file

Structured tests improve maintainability, readability, and collaboration within QA teams.

## 7. Practical QA Tips

• Keep tests independent and isolated
• Use stable selectors like `data-testid` attributes
• Avoid relying on previous test state
• Prefer `page.route()` for deterministic network tests
• Clean up test data after execution
• Utilize multiple browser contexts for isolated scenarios
• Capture screenshots and videos on failures for debugging

## 8. Summary

Playwright is a versatile, modern end-to-end testing framework suitable for QA engineers who require stable, cross-browser testing with minimal flakiness. It provides parallel execution, automatic waiting, network mocking, and advanced simulations. Proper use of structured tests, best practices, and Playwright's features ensures reliable QA workflows and smooth CI/CD integration.