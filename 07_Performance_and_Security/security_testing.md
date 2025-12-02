# Security Testing

## 1. Introduction
**Security Testing** is a type of software testing focused on identifying and eliminating security vulnerabilities in an application. Its goal is to ensure that the application and the data it processes are protected from unauthorized access, data theft, and misuse.

**Goals:**
- Identify potential security flaws  
- Ensure integrity, confidentiality, and availability of data  
- Test the application’s resistance to various types of attacks  
- Verify that security controls work as intended  

**Example:**  
A web application handling user accounts and financial data must protect information from unauthorized access.

---

## 2. Security Testing Techniques

### 2.1 Penetration Testing (Pen Test)
**Definition:**  
A simulated attack on an application to identify vulnerabilities that real attackers could exploit.

**Goals:**
- Discover vulnerabilities in software, networks, or systems  
- Test application response to attacks  
- Provide recommendations for security fixes  

**Process:**
1. **Planning:** Define scope, objectives, rules, and permissions  
2. **Information Gathering:** Identify open ports, services, components, and access points  
3. **Vulnerability Analysis:** Use tools and manual techniques to detect security flaws  
4. **Exploitation:** Test vulnerabilities with simulated attacks without damaging the system  
5. **Post-Exploitation:** Assess the consequences and potential access to sensitive data  
6. **Reporting:** Document findings and suggest solutions  

**Example:**  
Simulating an attack on a login form to check if an unauthorized user can access the admin panel.

---

### 2.2 Input Validation Testing
**Definition:**  
Tests whether the application properly handles user input and prevents it from being exploited.

**Goals:**
- Prevent unauthorized code execution or data access  
- Test for vulnerabilities like XSS, SQL Injection, or other manipulations  

**Example:**  
Entering special characters, HTML tags, or SQL commands to check if unauthorized execution occurs.

---

### 2.3 Authentication & Authorization Testing
**Definition:**  
Verifies that login systems and access controls work as intended.

**Goals:**
- Prevent unauthorized access to user or admin functionalities  
- Ensure users can only access what they are permitted  
- Test password strength, multi-factor authentication, and account lockout policies  

**Example:**  
- Attempting to access admin pages with a regular user account  
- Testing password change scenarios to ensure old passwords cannot still be used  

---

### 2.4 Session & Cookie Testing
**Definition:**  
Checks whether sessions and cookies are securely implemented.

**Goals:**
- Prevent session hijacking  
- Ensure cookies properly encrypt data and have limited lifespan  
- Test logout mechanisms and automatic session expiration  

**Example:**  
- Using the same session from different devices or IP addresses  
- Verifying cookies are deleted after logout and session tokens are regenerated

---

### 2.5 Error Handling Testing
**Definition:**  
Tests how the application responds to unexpected inputs or errors.

**Goals:**
- Prevent disclosure of sensitive information through error messages  
- Ensure the application does not crash or become vulnerable  

**Example:**  
Sending invalid data intentionally and checking that the application returns generic, safe messages instead of revealing server or database details.

---

### 2.6 Network & Infrastructure Security Testing
**Definition:**  
Focuses on basic network and infrastructure security aspects relevant for QA understanding.

**Goals:**
- Detect open ports and unsecured services  
- Verify firewall rules and data encryption  
- Test resistance to DDoS and similar attacks  

**Example:**  
Port scanning to check if services are accessible only to authorized users.

---

## 3. Security Testing Process
1. Define testing objectives and scope  
2. Identify critical components and potential risks  
3. Select testing techniques  
4. Execute tests: penetration testing, input validation, authentication, session, and error handling tests  
5. Record vulnerabilities and analyze results  
6. Provide recommendations to fix vulnerabilities and track implementation  
7. Retest to confirm security

---

## 4. Common Challenges
- Limited access to test environments  
- Risk of data or system damage during testing  
- Requirement of knowledge about various attacks and techniques  
- Continuous software and infrastructure changes require repeated testing  
- Managing and categorizing numerous potential vulnerabilities

---

## 5. Conclusion
Security testing is a critical part of the QA process because it helps identify and eliminate vulnerabilities that could be exploited. A junior QA tester should understand basic techniques such as penetration testing, input validation, authentication and authorization testing, session and cookie testing, error handling testing, and basic network security testing. Practicing these techniques helps maintain application security and protect user data.