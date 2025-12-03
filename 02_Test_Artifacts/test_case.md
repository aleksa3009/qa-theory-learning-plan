# Test Case Design & Writing — Expanded Theory (Bullet-Point Structure)

## 1. What is a Test Case?
- A test case is a structured document describing a specific condition, input, action, or scenario to verify that a software feature works correctly.
- Serves as the foundation for manual and automated testing.
- Main purpose:
  - Ensure the application meets functional requirements.
  - Verify expected operations.
  - Validate behavior under various conditions.
  - Provide repeatable, reliable, and verifiable validation.
- Benefits:
  - Makes defect reproduction easier.
  - Validates fixes.
  - Provides clear evidence during testing.

## 2. Principles of a Good Test Case
- Clear and Understandable:
  - Anyone in QA should execute it without extra explanations.
- Concise but Complete:
  - Include all necessary details, avoid verbosity.
- Reproducible:
  - Executing multiple times yields the same results.
- Independent:
  - Can run without relying on other test cases.
- Traceable:
  - Linked to requirements, user stories, or specifications.
- Maintainable:
  - Easy to update as features evolve.

## 3. Standard Test Case Structure
1. **Test Case ID**: Unique identifier (e.g., TC-LOGIN-001).
2. **Title / Summary**: Descriptive title.
   - Example: Verify login with valid credentials.
3. **Related Requirement / Story ID**: Links test to requirement or story.
4. **Preconditions**: Setup or state required.
   - Example: User account exists, Chrome 116 on Windows 10.
5. **Test Data**: Input values or parameters.
   - Example: username, password, product SKU.
6. **Test Steps**: Numbered step-by-step instructions.
   - Example:
     1. Open login page
     2. Enter username
     3. Enter password
     4. Click “Login”
7. **Expected Result**: What should happen.
   - Example: User redirected to dashboard, welcome message displayed.
8. **Actual Result**: What actually happened (filled after execution).
9. **Status / Execution Result**: Pass / Fail / Blocked / Not Executed.
10. **Postconditions**: Cleanup actions after test execution.
11. **Attachments / Evidence**: Screenshots, logs, videos.
12. **Notes / Comments**: Observations, dependencies, special instructions.

## 4. Types of Test Cases
- **Positive Test Cases**: Verify correct behavior with valid input.
- **Negative Test Cases**: Handle invalid input gracefully.
- **Boundary / Edge Test Cases**: Test system limits.
- **Exploratory / Ad-hoc Test Cases**: Discover unexpected defects.
- **Regression Test Cases**: Verify existing functionality after changes.
- **Performance / Load Test Cases**: Validate behavior under stress.

## 5. Best Practices for Writing Test Cases
- Use consistent naming/ID conventions.
- Write numbered, clear steps.
- Include preconditions and test data.
- Keep tests independent.
- Link to requirements or user stories.
- Include expected results for each step.
- Attach evidence when needed.
- Regularly review and update test cases.
- Avoid hardcoding; use reusable data.
- Prioritize based on critical features and risk.

## 6. Test Case Execution Flow
1. Prepare the environment and set up preconditions.
2. Execute the test step by step, following instructions precisely.
3. Compare actual results with expected results.
4. Record the status (Pass/Fail/Blocked).
5. Capture evidence for any failures.
6. Log defects if discrepancies are found, linking to the test case.
7. Perform any postconditions or cleanup actions.

## 7. Example Test Case
**Test Case ID:** TC-LOGIN-001  
**Title:** Verify login with valid credentials  
**Requirement ID:** REQ-LOGIN-01  
**Preconditions:**
- User account exists: xyz@test.com / Test123!
- Browser: Chrome 116  
**Test Data:**
- Username: xyz@test.com
- Password: Test123!  
**Steps:**
1. Open login page
2. Enter username
3. Enter password
4. Click "Login"  
**Expected Result:**
- User is redirected to dashboard
- Welcome message displayed  
**Postconditions:**
- Logout user  
**Attachments:**
- Screenshot of successful login  
**Status:** Not executed  
**Notes:**
- Ensure no cached session is present

## 8. QA Value and Metrics
- **Test Coverage:** Percentage of requirements/features covered.
- **Pass/Fail Ratio:** Evaluates release quality.
- **Defect Density per Test Case:** Highlights risky or unstable modules.
- **Execution Efficiency:** Estimates time for regression cycles.

## 9. Summary
- Test cases provide structured, repeatable instructions for validating application functionality.
- Well-written test cases:
  - Ensure requirements are validated
  - Make defects reproducible
  - Support regression and automated testing
  - Improve overall QA workflow
