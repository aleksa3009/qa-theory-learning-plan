# QA Accessibility

## 1. Introduction to Accessibility QA

### 1.1 What is QA Accessibility Testing?
QA accessibility testing checks whether digital products (websites, mobile apps, software) can be used by all users, including those with disabilities (visual, auditory, motor, cognitive).  
Goal: Enable access, navigation, and interaction for everyone.  

**Difference from standard QA:** Focus on usability with assistive technologies (screen reader, keyboard, braille, voice control), not just functionality, performance, or security.

### 1.2 Why Accessibility Matters
- **Legal compliance:** Non-compliance can lead to fines and lawsuits (ADA, Section 508, European Accessibility Act).  
- **Equal access:** All users, including elderly and temporarily disabled, can use the application.  
- **Improved UX & SEO:** Clear content and navigation help everyone.  
- **Integration in development:** Shift-left testing detects issues early, reducing cost and time to fix.

---

## 2. Standards and Regulations

### 2.1 WCAG (Web Content Accessibility Guidelines)
WCAG defines web accessibility standards.  

**POUR Principles:**
1. **Perceivable:** Content must be visible or audible.  
   - Example: Text contrast sufficient, images have alt text, videos have captions.  
2. **Operable:** Users must interact with UI via keyboard or voice.  
   - Example: Tab focus logical, dropdowns accessible via keyboard.  
3. **Understandable:** Information and interactions must be clear and predictable.  
   - Example: Clear instructions, consistent navigation, proper alerts/validation.  
4. **Robust:** Content compatible with all technologies, including assistive tools.  
   - Example: Semantic HTML, correct ARIA attributes.

### 2.2 Laws and Regulations
- **ADA (USA):** Websites and applications must be accessible.  
- **Section 508 & 504:** Digital technology in education/government must be accessible.  
- **European Accessibility Act (2025):** Digital products in EU must meet accessibility standards.

---

## 3. Accessibility Testing Goals
- Verify compliance with WCAG, ADA, Section 508.  
- Inclusive design: equal experience for all users.  
- Detect barriers:  
  - Poor contrast  
  - Missing alt text  
  - Improper form fields  
  - Keyboard/focus navigation issues  
- Prevent legal issues and lawsuits.  
- Ensure compatibility with assistive technologies.

---

## 4. User Groups and Challenges

| Group             | Problems                         | Example Situation                              |
|------------------|---------------------------------|-----------------------------------------------|
| Visually impaired | Blind, low vision, colorblind    | Image without alt text, poor contrast        |
| Hearing impaired | Deaf or hard of hearing          | Video without captions                        |
| Motor impaired   | Mouse/keyboard difficulties      | Input field not accessible by keyboard       |
| Cognitive impaired| Attention/understanding issues  | Complex form without clear instructions      |

---

## 5. Types of Accessibility Testing

### 5.1 By Method
- **Manual Testing:** human evaluation, keyboard navigation, UI structure, alt text.  
- **Automated Testing:** tools for quick issue detection (Wave, Axe, Tenon).

### 5.2 Specific Types
- Functional Testing with assistive technologies  
- Usability Testing with real users with disabilities  
- Compatibility / Cross-browser / Cross-platform  
- Mobile Accessibility Testing (iOS & Android)  
- Content Testing: text, images, video, multimedia  
- Regression Testing for accessibility after changes

---

## 6. ARIA and Semantics
- **ARIA (Accessible Rich Internet Applications):** attributes to enhance accessibility of dynamic content.  
- **Key ARIA attributes:**  
  - `role` – element type (button, navigation)  
  - `aria-label` – text description  
  - `aria-labelledby` – links element to a label  
  - `aria-hidden` – hides element from screen readers  
- **Semantic HTML:** `<header>`, `<main>`, `<nav>`, `<section>` improves navigation and accessibility.

---

## 7. Common Accessibility Issues
- Missing alt text  
- Poor color contrast  
- Incorrect heading structure  
- Missing or wrong ARIA attributes  
- Keyboard navigation issues  
- Improper forms & interactive elements  
- Multimedia without captions or transcript

---

## 8. Theoretical Tools
- Wave – visual accessibility issue map  
- Tenon – automatic code/UI analysis  
- Axe – browser extension for detecting issues  
- JAWS – screen reader  
- Accessibility Valet – comprehensive testing/reporting tool

---

## 9. Real-life Examples

| Problem                     | User Type           | Explanation                          |
|------------------------------|------------------|--------------------------------------|
| Image without alt text       | Visually impaired | Screen reader cannot read image      |
| Poor contrast                | Visually impaired | Text hard to read                    |
| Field without label          | All               | Keyboard/screen reader unsure input  |
| Navigation not tab-order     | Motor impaired    | Focus skips logical elements         |
| Video without captions       | Hearing impaired  | Users cannot follow audio            |

---

## 10. Trends and Future of Accessibility QA (2025)
- AI tools detect most issues and suggest fixes  
- Shift-left testing: check accessibility in design phase  
- Personalization: font, contrast, navigation adapt automatically  
- Global regulations tightening  
- Accessibility as a business strategy: reputation & user trust  

---