# Bug Triage

## Introduction

### Definition and Purpose

Bug Triage is the process of reviewing, analyzing, prioritizing, and assigning defects in a software project. It helps the team decide which bugs should be fixed first and which bugs can be delayed, rejected, or monitored.

Bug triage keeps defect handling organized. It helps the team focus on bugs that have the biggest business or technical impact.

### Why it matters in QA

Bug Triage is important because QA engineers do not only find bugs. They also help the team understand how serious a bug is, how reproducible it is, and how it affects the product.

For junior QA engineers, this topic is valuable because it shows that you can think beyond finding issues and understand how defects are managed in a real team.

## Web Element Interaction

Bug Triage does not involve direct interaction with web elements. However, bugs often come from UI behavior, so QA engineers need to describe the interaction clearly when reporting defects.

Example:

* the user enters valid credentials
* the user clicks the Login button
* the expected dashboard does not open

A clear description of the interaction helps the team reproduce the issue faster.

## Locators

Locators are not part of the triage process itself, but they help when a bug report references a specific UI element.

Useful details in a bug report may include:

* element name
* page or screen name
* selector or locator used in automation
* screenshot of the affected area

Example:

```javascript
await page.getByRole('button', { name: 'Login' }).click();
```

QA note:
Stable locators make reproduction easier in automated tests. Unclear element references make bug investigation slower.

## Actions

Typical Bug Triage flow:

### 1. Review the defect

The team checks whether the bug report is clear and complete.

### 2. Reproduce the issue

QA or the developer tries to reproduce the problem.

### 3. Assess severity

The team decides how much the bug affects the system.

### 4. Set priority

The team decides how urgently the bug should be fixed.

### 5. Assign ownership

The bug is assigned to the right developer or team.

### 6. Decide next action

The bug can be fixed, deferred, rejected, or reopened.

Typical participants:

* QA engineer
* developer
* product owner or product manager
* sometimes business analyst or team lead

Example for interview:
If the checkout page crashes for all users, the bug has high severity and usually high priority. If a button label is misspelled on a low-impact screen, the severity may be low, but the priority can still be high if the issue is visible to customers.

## Assertions if relevant

Assertions are used when QA verifies expected behavior during testing. They help identify whether a bug exists.

Example:

* Expected: the user is redirected to the dashboard
* Actual: an error message appears

This mismatch becomes the basis for the bug report.

Example in testing:

```javascript
await expect(page).toHaveURL('/dashboard');
```

QA note:
The assertion itself is not part of triage, but it often helps prove that the bug is real.

## Key Features / Core Concepts

### Severity

Severity describes how serious the bug is for the application.

### Priority

Priority describes how soon the bug should be fixed.

### Reproducibility

A reproducible bug is easier to confirm and assign.

### Impact

Impact describes how many users or business flows are affected.

### Bug Status

Common statuses include:

* Open
* In Progress
* Fixed
* Retest
* Closed
* Rejected
* Deferred

Example:
A typo on the homepage may have low severity but high priority because it is visible to many users.

## Advantages

* helps the team focus on the most important bugs
* improves communication between QA, dev, and product roles
* reduces confusion about defect ownership
* speeds up decisions on bug handling
* supports better product quality

## Limitations

* priority decisions can be subjective
* triage meetings need time and coordination
* incomplete bug reports slow down the process
* disagreements can happen between teams

## Practical QA Tips

1. Write bug reports clearly and simply.
2. Include steps to reproduce.
3. Add expected and actual results.
4. Attach screenshots, logs, or videos when possible.
5. Understand the business impact before judging priority.
6. Do not confuse severity with priority.
7. Keep the report focused on one issue.

Practical bug report example:

Title: Login fails with valid credentials

Steps:

1. Open the login page.
2. Enter a valid email and password.
3. Click the Login button.

Expected Result:
The user should be redirected to the dashboard.

Actual Result:
An error message is shown.

This is a strong bug report because it is clear, reproducible, and easy to discuss in triage.

## Summary

Bug Triage is the process of reviewing and prioritizing defects in a team.

For QA engineers, it is important because it connects testing with real defect management. It helps the team decide what to fix first and why.
