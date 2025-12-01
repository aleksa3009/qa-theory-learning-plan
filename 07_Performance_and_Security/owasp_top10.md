# OWASP Top 10 (2021) 

This is a detailed learning script for the **OWASP Top 10 vulnerabilities**. Each item includes:

- Explanation of the theory
- Simple example of the attack
- How a tester checks for it

## What is OWASP

**OWASP (Open Web Application Security Project)** is a global community focused on improving software security. The organization publishes guides, tools, and Top 10 lists of the most critical vulnerabilities to help developers and testers identify and fix security risks.  

The goal of OWASP is to make software more secure and protect users’ data from attackers. The **OWASP Top 10** is the most well-known list and serves as a reference for QA testers, developers, and security professionals.

---

## 1. Broken Access Control (BAC)

**Definition:**  
Access control restricts what users can do within an application. Broken access control occurs when these restrictions fail, allowing attackers to perform actions as if they had higher privileges.

**Example:**  
A web application allows a user to switch accounts simply by changing a `user_id` in the URL, without any additional verification.

**Prevention:**  
- Implement strict server-side checks  
- Use authorization tokens for every privileged request  
- Verify each action against the user’s permissions  

**How to Test:**  
- Change URLs, request parameters, cookies, or tokens to access unauthorized resources  
- Check if the server blocks unauthorized actions

---

## 2. Cryptographic Failures

**Definition:**  
Cryptography protects sensitive data by encrypting it so unauthorized parties cannot read it. Failures occur when data is transmitted or stored insecurely, weak algorithms are used, or secrets are poorly managed.

**Example:**  
A login form sending passwords over HTTP instead of HTTPS exposes users to credential theft.

**Prevention:**  
- Use strong, modern algorithms  
- Enforce HTTPS  
- Never store sensitive data in plain text  

**How to Test:**  
- Check that sensitive data is encrypted in transit and at rest  
- Ensure strong algorithms are used  
- Inspect that secrets are not exposed in logs or error messages

---

## 3. Injection

**Definition:**  
Injection vulnerabilities occur when untrusted data is sent to an interpreter as part of a command or query, allowing attackers to alter execution logic.

**Example:**  
Entering `' OR '1'='1` in a login field could bypass authentication if the input is directly used in a SQL query without sanitization.

**Prevention:**  
- Validate and sanitize inputs  
- Use parameterized queries  
- Avoid unsafe dynamic commands  

**How to Test:**  
- Input special characters, SQL fragments, or script tags  
- Observe if the system properly handles or rejects them

---

## 4. Insecure Design

**Definition:**  
Insecure design refers to flaws in application architecture or design that allow vulnerabilities to exist even before code is written.

**Example:**  
An application without rate limiting allows attackers to perform brute-force attacks indefinitely.

**Prevention:**  
- Threat modeling  
- Enforce least privilege  
- Input validation  
- Plan for security in all development stages  

**How to Test:**  
- Review workflow logic  
- Attempt edge-case operations  
- Check if security protections are implemented

---

## 5. Security Misconfiguration

**Definition:**  
Security misconfiguration happens when security settings are missing, incorrect, or left at insecure defaults.

**Example:**  
A server exposing stack traces or default admin pages leaks sensitive information.

**Prevention:**  
- Configure servers, databases, and APIs securely  
- Disable unnecessary features  
- Regularly review configurations  

**How to Test:**  
- Inspect server responses, headers, and endpoints  
- Verify debug info is not publicly exposed

---

## 6. Vulnerable and Outdated Components

**Definition:**  
Using outdated or vulnerable software introduces known weaknesses.

**Example:**  
Old jQuery versions with known XSS vulnerabilities can be exploited.

**Prevention:**  
- Keep software up to date  
- Monitor security advisories  
- Remove unused components  

**How to Test:**  
- Identify library versions  
- Check for known vulnerabilities  
- Test endpoints with outdated components

---

## 7. Identification and Authentication Failures

**Definition:**  
Failures in verifying user identity allow attackers to impersonate users or hijack sessions.

**Example:**  
Not regenerating session IDs after login enables session fixation attacks.

**Prevention:**  
- Multi-factor authentication  
- Strong password policies  
- Secure session management  

**How to Test:**  
- Test login, password reset, and session handling  
- Attempt to bypass authentication or reuse session tokens

---

## 8. Software and Data Integrity Failures

**Definition:**  
These failures occur when software or data cannot be trusted to be accurate and unmodified.

**Example:**  
Downloading updates without verifying digital signatures allows attackers to inject malicious code.

**Prevention:**  
- Use code signing  
- Verify data integrity  
- Enforce secure CI/CD practices  

**How to Test:**  
- Validate updates  
- Verify digital signatures  
- Check critical data changes

---

## 9. Security Logging and Monitoring Failures

**Definition:**  
Insufficient logging and monitoring prevent detecting breaches and responding effectively.

**Example:**  
Repeated failed login attempts without logging may allow brute-force attacks to go unnoticed.

**Prevention:**  
- Properly log security events  
- Implement monitoring to alert on suspicious activity  

**How to Test:**  
- Generate errors or unauthorized access attempts  
- Verify correct logging

---

## 10. Server-Side Request Forgery (SSRF)

**Definition:**  
SSRF occurs when a server is tricked into making requests to internal or external resources without proper validation.

**Example:**  
An API fetching a URL from user input may access internal network services if not validated.

**Prevention:**  
- Validate and sanitize all user-supplied URLs  
- Restrict requests to allowed domains  
- Use network-level protections  

**How to Test:**  
- Submit internal IP addresses or sensitive URLs  
- Check if access is improperly granted
