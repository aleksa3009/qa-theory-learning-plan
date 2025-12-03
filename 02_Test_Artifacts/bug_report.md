# Bug Report — Theory, Structure & Best Practices (Complete Guide)

## 1. Purpose of a Bug Report
- Communicate a reproducible problem so developers can understand, reproduce, fix, and verify it.
- Reduces time-to-fix, prevents misunderstandings, and increases product quality.

## 2. Principles of a Good Bug Report
- Clear — easy to read, informative title.
- Concise — enough detail, no unnecessary noise.
- Reproducible — precise steps for others to reproduce the issue.
- Objective — describe facts, not opinions.
- Actionable — provide evidence and context enabling fixing.
- Traceable — link to related tests, requirements, or commits.

## 3. Standard Bug Report Structure (fields to include)
1. **Title / Summary**
   - One-line clear summary: what is wrong and where.
   - Good: Login button unresponsive on Chrome 116 (production)
   - Bad: Login broken (too vague)
2. **ID / Reference**
   - Assigned by tracker (Jira/Bugzilla) for traceability.
3. **Environment / Context**
   - OS / version (Windows 10, macOS 13.4)
   - Browser / version or app version / build number
   - Server/stage, DB version, device
   - Feature flags or relevant config
4. **Priority & Severity**
   - Severity: technical impact (Critical, Major, Minor, Trivial)
   - Priority: business urgency (P0/P1/P2)
5. **Component / Module / Labels**
   - Location (e.g., Checkout, Auth, Mobile-Android)
   - Tags: regression, performance, security, ui
6. **Steps to Reproduce (STR)**
   - Numbered steps, include test data or fixtures
   - Indicate if always reproducible or intermittent
7. **Expected Result**
   - What should happen if no bug existed
8. **Actual Result**
   - What happened; include error text, UI state, wrong data
9. **Attachments / Evidence**
   - Screenshots, screencasts, logs, HAR/network traces, DB queries, stack traces
   - Automated test logs if relevant
10. **Reproducibility / Frequency**
    - Always / Sometimes x/y / Intermittent / Hard to reproduce
11. **Workaround**
    - Temporary way to avoid the issue, if any
12. **Related Artifacts / Links**
    - Failed test case, PR, API, logs, user story, spec
13. **Reporter & Date**
    - Who reported it and when
14. **Regression Info**
    - Worked in release X.Y, broken in X.Z
15. **Suggested Fix / Hypothesis (optional)**
    - Probable cause hints
16. **Status / Workflow**
    - New → Assigned → In Progress → Fixed → Retest → Closed / Reopened / Deferred / Duplicate

## 4. Writing Tips — How to be precise
- Use exact timestamps and locale
- Provide exact input values
- Include reproduction URLs and build numbers
- Trim logs to relevant sections
- Prefer numbered steps over paragraphs
- Record variables for intermittent issues
- Avoid judgmental language

## 5. Examples

### Good Bug Report (short)
**Title:** Checkout payment fails with 500 using PayPal on staging (browser: Firefox 127)  
**Environment:** Staging, build v2.3.1, Firefox 127.0.0, Ubuntu 22.04  
**Steps to Reproduce:**
1. Login as test+paypal@qa.com (password Test123!) on staging.
2. Add item SKU SKU-123 to cart.
3. Proceed to Checkout → Payment → choose PayPal → Click “Pay Now”.
4. Observe the error.  
**Expected:** Redirect to PayPal payment page and complete payment.  
**Actual:** Page returns HTTP 500, shows “Internal Server Error”. Console shows TypeError: cannot read property 'id' of undefined.  
**Reproducibility:** 3/3 attempts  
**Attachments:** screenshot, server log, network HAR  
**Priority/Severity:** P1 / Major

### Bad Bug Report (short)
**Title:** PayPal broken  
**Description:** It doesn't work. Fix it.  
→ Not actionable: missing environment, steps, logs.

## 6. Common Mistakes to Avoid
- Vague titles and steps
- Missing environment details
- No proof (screenshots/logs)
- Not marking duplicates
- Over-prescribing fixes
- Mixing unrelated issues in one ticket

## 7. Handling Intermittent & Non-deterministic Bugs
- Document every attempt: timestamps, steps, outcomes
- Capture system state at failure
- Isolate variables: browser, account, time, concurrent tests
- Create small reproducible cases if possible
- Use monitoring/observability data

## 8. Prioritization: Severity vs Priority
- Severity: technical impact (critical vs cosmetic)
- Priority: business need (how soon fix is needed)
- Example: cosmetic bug on marketing page → Low Severity, High Priority

## 9. Lifecycle & Communication Best Practices
- Triage quickly: validate, assign severity/priority, prevent duplicates
- Keep comments factual
- Retest promptly when fix is deployed
- Use consistent workflow and naming
- Escalate blocking issues immediately

## 10. Metrics & QA Health Indicators
- Open vs Closed bugs trend
- Average time to resolve (MTTR)
- Bug reopen rate
- Defects by severity/component
- Defects found in production vs pre-release

## 11. Templates (Quick copyable)
**Title:** [Component] Short description — browser/platform (optional)  
**Environment:** OS / browser / device / app version / backend build  
**Steps to Reproduce:**  
1.  
2.  
3.  
**Expected Result:**  
**Actual Result:**  
**Frequency:** Always / Intermittent: x/y  
**Severity / Priority:**  
**Attachments:** (screenshots, logs, HAR, test id)  
**Related:** (test case id, story id, PR)

## 12. When to Close a Bug
- QA verifies the fix and passes regression checks
- No new side-effects introduced
- Update bug with verification steps/results, then mark Closed
- If failure recurs, reopen with new evidence

## 13. Final Checklist Before Filing
- Steps reproduce the issue on clean state
- Environment