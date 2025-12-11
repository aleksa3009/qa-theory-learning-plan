# Smoke and Sanity Testing

## 1. Definition & Purpose
**Smoke testing** is a quick, surface-level set of tests that verify whether the most essential functionalities of an application work and whether a build is stable enough for further testing.  
**Sanity testing** is focused testing that checks specific functionalities or modules after minor code changes or bug fixes.

**Purpose:** Introduce junior QA engineers to smoke and sanity testing concepts and best practices.

---

## 2. Smoke Testing
**Definition:** Verifies basic stability of the entire build. Named after hardware testing, where the first power-on “smoke test” would reveal catastrophic failure.

**Goals:**
* Detect critical issues early.
* Prevent QA from wasting time on unstable builds.
* Confirm core functionalities work.

**Characteristics:**
* Quick and surface-level.
* Covers all key system functionalities.
* Can be automated or manual.
* If a smoke test fails → build is returned to developers.

**Typical Examples:**
* Application launches without error.
* Login works with valid credentials.
* Navigation through main menu functions.
* Creation, saving, and deletion of a basic entity (user, product).
* Basic payment or checkout functionalities work.

---

## 3. Sanity Testing
**Definition:** Focused testing verifying a specific functionality or module after minor code changes.

**Goals:**
* Quickly confirm that a change does not break existing functionality.
* Validate that the build is worth further testing.

**Characteristics:**
* Focused on one module or feature.
* Usually smaller and faster than detailed testing.
* Often manual, can be automated.
* If sanity test fails → build is returned to developers; further testing is halted.

**Typical Examples:**
* After a login bug fix:
  * Verify login with valid credentials.
  * Verify correct error messages for invalid password.
* After a payment system update:
  * Verify transactions complete successfully.
  * Verify coupon codes or discounts are applied correctly.

---

## 4. Smoke vs Sanity – Key Differences

| Aspect             | Smoke Test                  | Sanity Test                   |
|-------------------|----------------------------|-------------------------------|
| Focus              | Entire build, core features | Specific functionality/module |
| Goal               | Build stability             | Correctness after change      |
| Scope              | Broad                       | Narrow                        |
| Execution time     | Fast but comprehensive      | Very fast, minimal            |
| When performed     | After every new build       | After bug fix or minor change |
| Result             | Fail → build not tested further | Fail → build returned to dev |
| Formality          | Planned set of tests        | Usually ad-hoc, focused      |
| Automation         | Suitable for automation     | Manual or automated           |

---

## 5. Best Practices
1. Document tests – both smoke and sanity tests should have clear steps and success criteria.  
2. Automate smoke tests – saves time with frequent builds.  
3. Prioritize functionalities – focus on critical features: login, payment, create/delete data, basic navigation.  
4. Run sanity tests quickly and targeted – test only changed or potentially affected areas.  
5. Record results – track pass/fail to help the team decide next steps.  
6. Understand context – in Agile/Scrum, smoke and sanity tests are essential for sprints and continuous integration.  

---

## 6. Example Scenario
**Scenario:** New version of an e-commerce app is released.

**Smoke Tests:**
1. Launch application.
2. Login with test account.
3. Search for a product.
4. Add product to cart.
5. Checkout process works.

**Sanity Tests (after coupon code fix):**
1. Verify coupon code applies discount correctly.
2. Verify total price updates automatically.
3. Quick check that basic purchase and checkout still work.

---

## 7. Conclusion
* **Smoke test** → quick overview of the entire build, verifies basic stability.  
* **Sanity test** → focused verification after code changes or bug fixes.  
* Both tests enable efficient and safe QA, save time, and ensure software quality.

---