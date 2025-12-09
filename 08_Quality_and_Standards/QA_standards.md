# QA Standards and Guidelines

## Definition & Purpose
QA standards are formal procedures, guidelines, and recommendations that define how software testing is planned, executed, documented, and controlled. Their main purpose is to ensure:
- Consistency of QA processes
- Traceability and coverage of requirements
- Repeatability of results
- Clear quality criteria
- Risk minimization
- Measurement of software quality

Standards are used in companies and education and provide a framework that a junior QA should understand even if not applied formally.

## Sections

### 1. Key QA Standards and Guidelines

#### 1.1 ISO/IEC 29119 – Software Testing
**Overview:** The most important global standard for software testing, consisting of 5 parts; for practical QA, the first four are essential.

**Key Parts:**
- **29119-1 – Concepts & Definitions**
  - Terminology: test case, test suite, test plan, incident, risk-based testing, coverage
  - Basis for ISTQB and most QA methodologies
- **29119-2 – Test Processes**
  - Defines the complete testing process: planning, analysis & design, implementation, execution, evaluation, closure
  - Specifies inputs, outputs, activities, and responsibilities for each phase
- **29119-3 – Test Documentation**
  - Key documents: Test Plan, Test Design Specification, Test Case Specification, Test Procedure Specification, Test Log, Test Summary Report, Test Incident Report
- **29119-4 – Test Techniques**
  - Functional and non-functional techniques: Equivalence Partitioning (EP), Boundary Value Analysis (BVA), Decision Tables, State Transition Testing, Exploratory Testing, Performance and Security test techniques

#### 1.2 ISO/IEC 25010 – Software Quality Model
Defines software quality through eight attributes:
1. Functional suitability
2. Performance efficiency
3. Compatibility
4. Usability
5. Reliability
6. Security
7. Maintainability
8. Portability

Used by QA to define quality criteria and ensure test coverage across all quality dimensions.

#### 1.3 ISO/IEC 12207 – Software Life Cycle
Describes the complete SDLC: development, verification, validation, delivery, and maintenance. QA uses it to:
- Understand how testing fits into each SDLC phase
- Define QA roles in Waterfall and Agile
- Follow change control processes

#### 1.4 IEEE 829 – Standard Test Documentation
Even though it succeeds ISO 29119-3, IEEE 829 is still widely used. Key elements:
- Test Plan
- Test Design Specification
- Test Case Specification
- Test Incident Report
- Test Summary Report

Practical use: QA must know the structure of each document.

#### 1.5 IEEE 1028 – Standard for Formal Reviews
Defines types of document reviews:
- Walkthrough
- Technical review
- Inspection
- Audit

Used to control the quality of technical documentation.

#### 1.6 IEEE 730 – Software Quality Assurance Standard
Describes:
- How to establish QA processes in an organization
- SQA activities
- Procedures for quality audits
- Mandatory QA documents

Difference: covers the QA process as a whole, whereas ISO 29119 focuses on testing.

#### 1.7 ISO/IEC 9126 – Predecessor of ISO 25010
Older version of the software quality model; used as reference where 25010 is not adopted.

#### 1.8 ISO/IEC 27001 – Information Security Standard
Important for QA in the context of security testing. Shows:
- How to identify security requirements
- Importance of encryption, access policies, and data protection

QA should understand basic CIA principles (Confidentiality, Integrity, Availability).

#### 1.9 CWE, CVE, and CVSS – Security Weakness Guidelines
- **CWE:** Catalog of common software errors
- **CVE:** List of known vulnerabilities
- **CVSS:** Vulnerability criticality scoring system

Used for security testing.

#### 1.10 ISTQB Guidelines
Not formal standards, but widely recognized in the industry. Define:
- Global terminology
- Test processes
- Test techniques
- Types of testing
- QA roles in teams

ISTQB is the most sought-after certification; guidelines are mandatory for learning.

### 2. Most Important Standards for Junior QA
For beginners, the following are essential:
1. ISO/IEC 29119 (mandatory)
2. ISO/IEC 25010
3. IEEE 829
4. ISTQB guidelines
5. ISO/IEC 27001 (basics)
6. IEEE 1028
7. ISO/IEC 12207 (SDLC overview)

Everything else is additional knowledge.

### 3. Practical Learning Approach
- Understand concepts, do not memorize
- Draw your own test process according to ISO 29119
- Write three documents per standard: Test Plan, Test Case, Incident Report
- Create a quality checklist based on ISO 25010
- Practice traceability matrices
- Learn basic 27001 security principles
- Solve ISTQB Foundation level questions

### 4. Reference Table
| Standard | Focus | Purpose |
| --- | --- | --- |
| ISO/IEC 29119 | Test processes, documents, techniques | Core QA practice |
| ISO/IEC 25010 | Software quality model | Define quality criteria |
| IEEE 829 | Test documentation | Document templates |
| ISO/IEC 12207 | SDLC processes | Understand QA in development |
| IEEE 1028 | Reviews/Audits | Documentation quality control |
| IEEE 730 | QA process | Organizational QA and SQA |
| ISO/IEC 27001 | Information security | Security requirement basics |
| CWE/CVE/CVSS | Security weaknesses | Basis for security testing |
| ISTQB Guidelines | Terminology and practices | Industry-standard certification |
