# Regression Testing

## 1. Introduction

Regression Testing is a type of software testing aimed at verifying that new changes have not broken existing functionality. Any software change – bug fix, new feature, or enhancement – may affect other parts of the system.

**Example:**

* An online store has a product purchase function.
* Developer adds a new payment option.
* Regression testing ensures that previous payment methods still work and the new feature integrates correctly.

## 2. When to Perform Regression Testing

Regression testing is conducted after:

1. Bug fixes
2. Adding new features
3. Enhancing existing functionality
4. Module integrations

**Execution Methods:**

* Manual: QA tester executes tests manually.
* Automated: Scripts execute tests automatically, saving time and reducing human error.

## 3. Objectives

* Ensure old functionality continues to work.
* Detect unexpected errors caused by new changes.
* Reduce risk of software failure.
* Maintain product stability and quality.

## 4. Regression Test Package Planning

A regression test package is a set of tests used for regression testing.

**Steps:**

1. Identify critical functionality

   * Focus on commonly used features.
   * **Example:** login, product search, adding to cart, payment.
2. Select test cases

   * Include tests most likely affected by changes.
   * Mix of manual and automated tests.
3. Prioritize tests

   * High priority: critical functionality
   * Medium/Low: less critical
4. Automate tests

   * Frequently repeated tests are ideal for automation.
5. Update package regularly

   * Keep package current as the system evolves.

## 5. Regression Testing Techniques

* **Retest all:** run all tests (time-consuming)
* **Selective regression:** run only tests likely affected
* **Prioritized regression:** run tests based on criticality
* **Automated regression:** automated, can run often

## 6. Tactics and Strategies

* Focus on critical and frequently used functionality
* Combine manual and automated testing
* Log all regressions and analyze causes
* Maintain test package to reflect system changes

## 7. Sample Regression Testing Flow

1. Developer implements new functionality.
2. QA team prepares regression test package.
3. Tests are executed manually or automatically.
4. Test results are recorded; failures are analyzed.
5. Detected regressions are reported and fixed.
6. Tests are re-executed until all functions work correctly.

**Example:**

* Developer adds new payment method.
* QA runs regression test for product purchase.
* Old payment methods are verified; new method tested.
* Issue found in one old method is reported and fixed.

## 8. Common Mistakes and Challenges

* Running all tests without prioritization
* Ignoring old but critical test cases
* Insufficient test automation
* Not maintaining or updating regression package