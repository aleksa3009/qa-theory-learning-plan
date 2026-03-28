# Test Design Techniques

## Introduction

Test Design Techniques are structured methods used to derive test cases from requirements, user stories, or system behavior. Their goal is to improve test coverage, reduce redundancy, and ensure systematic validation of functionality.

These techniques are part of the Test Design phase in STLC and are essential for creating efficient, repeatable, and risk-based test suites.

---

## Web Element Interaction

Test design techniques are applied to real UI components such as:

* Forms (login, registration)
* Input fields (text, numeric, date)
* Dropdowns and filters
* Multi-step workflows (checkout, onboarding)

They define what data combinations, boundary conditions, and business rules must be tested.

---

## Locators

Test design influences which elements must be covered during execution.

Common locators:

* ID
* Name
* CSS selectors
* XPath
* data-testid attributes

Example:

* input email → id="email"
* password field → id="password"
* submit button → data-testid="submit"

---

## Actions

Derived actions include:

* Input valid/invalid data
* Submit forms
* Select multiple combinations
* Navigate states and workflows
* Trigger validations

---

## Assertions

Assertions validate expected outcomes:

* Error messages for invalid input
* Successful submission for valid data
* Correct system state transitions
* UI updates after actions

---

## Key Features / Core Concepts

### 1. Equivalence Partitioning (EP)

Equivalence Partitioning is a black-box test design technique where input data is divided into groups (partitions) that are expected to behave the same way. Instead of testing every possible value, QA selects one representative value from each valid and invalid group. This reduces the number of test cases while maintaining good coverage.

Example (Age 18–60):

* Valid class: 18–60 → representative value: 30
* Invalid class: below 18 → 10
* Invalid class: above 60 → 70

Purpose: reduce redundant testing while ensuring all input categories are covered.

---

### 2. Boundary Value Analysis (BVA)

Boundary Value Analysis focuses on testing values at the edges of input ranges because defects often occur at boundaries rather than in the middle of ranges. It complements equivalence partitioning.

Example (Age 18–60):

* 17 (just below minimum)
* 18 (minimum valid)
* 19 (just above minimum)
* 59 (just below maximum)
* 60 (maximum valid)
* 61 (just above maximum)

Purpose: detect off-by-one errors and validation issues at limits.

---

### 3. Decision Table Testing

Decision Table Testing is used when system behavior depends on multiple input conditions. It represents conditions and corresponding actions in a table format, ensuring all logical combinations are tested.

Example:

* Premium user (Yes/No)
* Order value > 100 (Yes/No)
* Coupon applied (Yes/No)

Each combination results in a different system behavior (discount applied, partial discount, no discount).

Purpose: ensure complete coverage of business rules and condition combinations.

---

### 4. State Transition Testing

State Transition Testing verifies how a system behaves when it moves between different states based on events or user actions. It is useful for systems with workflows or lifecycle states.

Example:

* Logged out → Logged in (successful login)
* Logged in → Logged out (logout action)
* Failed login attempts → Account locked
* Session active → Session expired

Purpose: ensure correct system behavior across different states and transitions.

---

### 5. Pairwise Testing

Pairwise Testing is a combinatorial technique that reduces the number of test cases by ensuring that every possible pair of input parameters is covered at least once. It is effective when testing multiple configurations.

Example:

* Browser: Chrome, Firefox, Safari
* OS: Windows, Mac
* User type: Guest, Registered

Instead of testing all combinations, pairwise ensures that every pair (e.g., Chrome + Windows, Firefox + Mac) is tested.

Purpose: optimize coverage while reducing test execution effort.

---

### 6. Cause-Effect Graphing

Cause-Effect Graphing is a technique that maps input conditions (causes) to output results (effects) using logical relationships. It helps derive structured test cases from complex business rules.

Example:

* Cause: valid username + valid password → Effect: login success
* Cause: invalid password → Effect: error message

Purpose: translate complex logic into structured test cases and decision tables.

---

### 7. Error Guessing

Error Guessing is an experience-based technique where QA engineers design test cases based on intuition, experience, and knowledge of common defect patterns. It is not structured but highly effective when combined with formal techniques.

Examples:

* Empty input fields
* Very long strings
* Special characters (e.g., !@#$)
* SQL injection attempts
* Invalid formats (email without @)

Purpose: detect defects that structured techniques might miss.

---

### 8. Use Case Testing

Use Case Testing is based on real user scenarios and workflows. Test cases are derived from how an actual user interacts with the system from start to finish.

Example:

* User logs in → searches product → adds item to cart → completes checkout

Purpose: validate end-to-end business flows and real-world usage behavior.

---

### 9. Exploratory Testing (Structured)

Exploratory Testing combines test design and execution simultaneously. QA explores the application while designing tests dynamically based on system behavior and findings.

Purpose: discover unexpected issues, usability problems, and edge cases not covered in formal test cases.

---

### 10. Combinatorial Testing

Combinatorial Testing involves testing combinations of multiple input parameters beyond pairwise when higher interaction coverage is needed.

Purpose: ensure that complex systems with multiple dependencies behave correctly under different configurations.

---

### 11. Risk-Based Testing

Risk-Based Testing prioritizes test cases based on the probability of failure and the business impact of defects. High-risk areas are tested first and more thoroughly.

Purpose: maximize defect detection efficiency when time and resources are limited.

---

## Advantages

* Systematic test coverage
* Reduced redundant test cases
* Better defect detection
* Improved efficiency in regression testing
* Supports structured QA planning

---

## Limitations

* Requires strong requirement understanding
* Complex systems may increase design effort
* Some techniques require experience to apply effectively
* Risk of missing edge cases if misapplied

---

## Practical QA Tips

* Combine techniques (EP + BVA is standard)
* Use decision tables for business logic
* Use state transitions for workflows
* Apply error guessing after structured testing
* Use pairwise for multi-configuration testing
* Prioritize risk-based testing in limited time scenarios

---

## Summary

Test Design Techniques are essential QA methods for creating efficient, structured, and high-quality test cases. They ensure maximum coverage with minimal redundancy and are critical for junior QA engineers preparing for real-world testing environments.