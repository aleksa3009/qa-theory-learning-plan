# Software Testing Life Cycle (STLC)

## Introduction

### Definition and Purpose

Software Testing Life Cycle (STLC) is a structured process that defines the phases of software testing. It helps QA teams plan, design, execute, and close testing activities in an organized way.

STLC gives testing a clear flow. It connects requirements, test design, execution, defect reporting, and reporting.

### Why it matters in QA

STLC is important because it helps QA engineers work in a disciplined and predictable way. It improves communication with developers, business analysts, and product owners.

For junior QA engineers, STLC is one of the most important topics because it shows that testing is not only about running test cases. It is also about planning, analysis, documentation, execution, and closure.

## Web Element Interaction

STLC does not describe web element interaction directly. It explains when testing activities happen and how UI test scenarios fit into the process.

Example:

* During Requirement Analysis, the QA engineer identifies what should be tested.
* During Test Design, the QA engineer prepares scenarios for fields, buttons, links, and forms.
* During Test Execution, the QA engineer interacts with the application manually or through automation.

Practical example:
A login feature may include interactions with the email field, password field, login button, and error message area.

## Locators

Locators are not part of STLC itself, but they become important during test design and execution, especially in UI automation.

QA engineers should prefer stable locators such as:

* `data-testid`
* label-based locators
* role-based locators
* accessible text when it is stable

Example:

```javascript
await page.getByLabel('Email').fill('qa@example.com');
await page.getByRole('button', { name: 'Login' }).click();
```

QA note:
Poor locators can make tests flaky and harder to maintain. Good locators improve reliability in local runs and CI.

## Actions

STLC usually includes these phases:

### 1. Requirement Analysis

The QA engineer reviews requirements and identifies what is testable.

Typical QA tasks:

* understand business requirements
* identify test scope
* find ambiguities or missing details
* raise questions early

### 2. Test Planning

The QA engineer defines the testing approach.

Typical QA tasks:

* estimate effort
* choose tools
* define test strategy
* identify risks

### 3. Test Case Design

The QA engineer writes test cases and prepares test data.

Typical QA tasks:

* create positive and negative scenarios
* define preconditions
* prepare test data
* review coverage

### 4. Test Environment Setup

The team prepares the environment for testing.

Typical QA tasks:

* check application access
* confirm test accounts
* verify builds and configurations
* validate dependencies

### 5. Test Execution

The QA engineer runs test cases and reports defects.

Typical QA tasks:

* execute manual or automated tests
* compare expected and actual results
* report bugs
* retest fixes
* perform regression checks

### 6. Test Closure

The QA engineer summarizes testing results.

Typical QA tasks:

* review coverage
* analyze defect trends
* document final status
* share test summary

Example for interview:
For a login feature, the QA process starts with requirement review, continues with test case creation, then execution of valid and invalid login attempts, and ends with a report of the results.

## Assertions if relevant

Assertions are the checks used during test execution to confirm expected behavior.

Examples:

* the dashboard is visible after login
* the error message is shown for invalid credentials
* the URL changes after successful navigation
* the submitted form data is saved

Example:

```javascript
await expect(page).toHaveURL('/dashboard');
```

QA note:
A good assertion checks business behavior, not only visual appearance.

## Key Features / Core Concepts

* structured testing process
* clear testing phases
* early defect detection
* better communication between QA and other roles
* traceability from requirements to execution

Core concept:
STLC describes how testing work flows from analysis to closure.

## Advantages

* improves test organization
* helps detect defects early
* supports better planning
* improves team alignment
* makes QA work easier to track and review

## Limitations

* can feel heavy in very fast projects
* requires discipline and documentation
* may be skipped or shortened in small teams
* does not solve poor communication by itself

## Practical QA Tips

1. Start with requirement understanding before writing tests.
2. Keep test cases clear and focused.
3. Use both positive and negative scenarios.
4. Do not skip planning, even in small projects.
5. Track defects with clear steps and expected vs actual results.
6. Review coverage before closure.

Practical example:
For a registration page, the QA engineer should check valid input, invalid email format, password rules, empty fields, and success confirmation.

## Summary

STLC is the foundation of organized software testing. It shows how QA work is planned, designed, executed, and closed.