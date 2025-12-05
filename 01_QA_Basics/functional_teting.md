# Functional Testing

## 1. Overview and Purpose

Functional testing verifies system behavior against requirements, user stories, or specifications. It ensures features work as intended, detects defects, and prevents regressions.

**Primary goals:**

* Confirm features work as specified.
* Detect defects in logic, data handling, and integration.
* Provide repeatable checks that prevent regressions.

Functional testing spans multiple levels (unit → integration → system → acceptance), forming the testing pyramid.

---

## 2. Unit Testing

**What it is:** Validates smallest testable units (functions, methods, classes) in isolation.

**Who writes & runs:** Developers, run locally and in CI.

**Objectives:**

* Verify correctness of small logic pieces.
* Provide fast feedback.
* Serve as documentation.

**Characteristics:** Fast, deterministic, use mocks/stubs.

**Tools/Frameworks:** JUnit, pytest, Jest, Mockito.

**Design Techniques:** Positive/negative paths, boundary values, edge cases.

**Example:** Tax calculation function, input 100, region VAT20 → expected tax 20, total 120.

**Best Practices:** Small, focused tests; clear naming; run in CI; meaningful coverage.

---

## 3. Integration Testing

**What it is:** Ensures multiple components work together correctly.

**Who writes & runs:** Mix of developers and QA.

**Objectives:** Detect interface mismatches, validate data flows.

**Characteristics:** Slower than unit tests; focus on integration points.

**Tools/Frameworks:** Spring Test, Testcontainers, pytest with fixtures, Pact, supertest.

**Types:** Component integration, service integration, contract tests.

**Design Techniques:** Use real or ephemeral test DBs; mock external APIs; validate success/error flows.

**Example:** API POST /orders calls billing → 200 → DB row created.

**Best Practices:** Focused, idempotent; fixtures; ephemeral environments; isolate flaky network conditions.

---

## 4. System Testing (E2E)

**What it is:** Validates entire application workflows end-to-end.

**Who writes & runs:** QA engineers, sometimes with developers.

**Objectives:** Validate full workflows, UI/backend integrations, catch gaps.

**Characteristics:** Slow, fragile if poorly designed.

**Tools:** Selenium, Playwright, Cypress, Postman/Newman.

**Design Approach:** Focus on critical flows; combine UI + API verification; fewer high-value tests.

**Example:** User registers → logs in → adds items → checkout → verify DB/email.

**Best Practices:** Test accounts, isolated data, seed/reset state, resilient waits, capture artifacts.

---

## 5. Acceptance Testing & UAT

**What it is:** Confirms system meets business requirements; UAT involves real users.

**Who writes & runs:** Business analysts, product owners, QA supporting users.

**Objectives:** Validate acceptance criteria, support business use cases, provide release sign-off.

**Characteristics:** Focus on business outcomes; mostly manual; staging/pre-prod with production-like data.

**Tools:** BDD (Cucumber/Gherkin), TestRail/Zephyr.

**Example (Gherkin):**

```
Feature: Checkout
Scenario: Successful purchase with coupon
Given a user with an active cart
When the user applies coupon "SAVE10" and completes checkout
Then the order should have a discount of 10% and status "confirmed"
```

**Best Practices:** Prepare clear criteria, provide test data, involve business early, log gaps as defects.

---

## 6. Regression Testing

**What it is:** Verifies code changes do not break existing functionality.

**Who writes & runs:** QA; automated in CI; developers may run locally.

**Objectives:** Prevent old defects, preserve behavior.

**Characteristics:** Combination of unit, integration, and E2E; mostly automated.

**Types:** Smoke tests, full regression.

**Design Strategy:** Automate stable tests; manual for exploratory/brittle cases.

**Best Practices:** Fast, reliable regression suites; maintain test data/environment parity; review for redundancy/flakiness.

---

## 7. Test Design & Selection

**Test Pyramid & Investment:** Most in unit tests → medium integration → fewer E2E.

**Risk-Based Selection:** Prioritize high-impact areas.

**Test Cases vs Levels:** Same requirement covered at multiple levels.

---

## 8. Test Data & Environment Considerations

**Environments:** Local dev, CI, staging/pre-prod, restricted production.

**Test Data:** Deterministic fixtures or seeded DBs; anonymized/synthetic if sensitive.

**Isolation & Cleanup:** Idempotent tests; parallel runs use separate namespaces/datasets.

---

## 9. Automation Considerations

**What to automate:**

* Unit: all.
* Integration: key APIs, critical interactions.
* System/E2E: high-value stable journeys.
* Acceptance: deterministic BDD tests.

**CI Integration:** Run unit per commit; integration in PR/nightly; E2E smoke per PR, full nightly; fail fast critical issues.

**Artifacts/Debugging:** Capture screenshots, logs, HAR, tag failures with test IDs.

---

## 10. Metrics & Reporting

**Key Metrics:** Test pass rate, execution time, defect density, regression failure rate, flaky test rate, defect escape rate.

Use metrics to adjust coverage, prioritize fixes, identify unstable modules.

---

## 11. Common Pitfalls

* Over-reliance on E2E → compress scope, automate lower levels.
* Flaky tests → isolate, explicit waits, move to integration.
* Poor test data management → script and isolate.
* Ignore performance/security → combine with non-functional tests.
* Not involving business in acceptance → UAT early.

---

## 12. Practical Checklists

**Before Writing Tests:** Understand requirements, boundary conditions, dependencies, test data.

**Before Executing:** Environment parity, seed data, clear caches, confirm connectivity.

**After Failing Test:** Capture artifacts, re-run, file bug if reproducible.

---

## 13. Sample Test Cases

**Unit Test:** TC-UNIT-001 — calculateTax() Input: amount=100, rate=0.2 → Expected: 20

**Integration:** TC-INTEG-001 — POST /orders persists order
Pre: product/user exists → Action: POST /orders → Expected: 201, DB row correct

**System/E2E:** TC-E2E-001 — Checkout end-to-end
Steps: login → add product → checkout → verify confirmation → Expected: Order confirmed, email queued

**Acceptance (UAT):** TC-UAT-001 — Manager approval flow
Given manager logged in → When approve expense → Then status approved, notification sent

**Regression/Smoke:** TC-SMOKE-001 — Login basic smoke
Open app → login → Expected: Dashboard opens, welcome visible

---