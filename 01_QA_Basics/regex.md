# Regex (Regular Expressions)

This script covers the fundamentals of Regex (Regular Expressions), their practical applications in QA, basic elements, examples, and best practices for junior QA engineers.

---

## 1. Introduction

Regular Expressions (Regex) are patterns used to search, validate, and extract text from strings. In QA, Regex is commonly used for:

* Data format validation (e.g., emails, phone numbers, dates)
* Searching through log files
* Parsing test or API outputs

**Definition:** A regex is a formal language describing a set of strings through patterns. Each regex defines the language, i.e., all strings it matches.

**Example:** `\d+` – matches one or more digits in a string.

---

## 2. Types of Regex Engines

* **DFA (Deterministic Finite Automaton):** Uses a deterministic machine for searching.
* **NFA (Nondeterministic Finite Automaton):** Uses a nondeterministic machine, more flexible but sometimes slower.

---

## 3. Basic Regex Elements

### a) Characters

| Symbol | Description                              |
| ------ | ---------------------------------------- |
| .      | Any character except newline             |
| \d     | Any digit [0-9]                          |
| \D     | Any non-digit character                  |
| \w     | Any alphanumeric character or underscore |
| \W     | Any non-alphanumeric character           |
| \s     | Any whitespace (space, tab, newline)     |
| \S     | Any non-whitespace character             |

**Example:** `\d{3}-\d{2}-\d{4}` → validates a Social Security Number (SSN) format, e.g., 123-45-6789.

### b) Quantifiers

| Symbol | Meaning                     |
| ------ | --------------------------- |
| *      | 0 or more repetitions       |
| +      | 1 or more repetitions       |
| ?      | 0 or 1 repetition           |
| {n}    | Exactly n repetitions       |
| {n,}   | n or more repetitions       |
| {n,m}  | Between n and m repetitions |

**Example:** `\d{2,4}` → matches 2 to 4 digits (12, 123, 1234).

### c) Groups and Character Classes

* Grouping: `()` → `(abc)+` matches "abc", "abcabc", etc.
* Alternation: `|` → `cat|dog` matches "cat" or "dog".
* Character class: `[]` → `[aeiou]` matches any vowel.
* Negation in class: `[^0-9]` → matches any character that is not a digit.

### d) Start and End Anchors

* `^` → start of string
* `$` → end of string

**Example:** `^\d{3}-\d{2}-\d{4}$` → ensures the string exactly matches SSN format.

### e) Escape Characters

Some characters have special meaning and must be escaped with `\` to match literally: `. ^ $ * + ? { } [ ] \ | ()`

**Example:** `\.` → matches a literal dot.

---

## 4. Practical QA Applications

### a) Email Validation

Regex: `^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$`

* `^` and `$` → full string
* `[a-zA-Z0-9._%+-]+` → username
* `@` → literal @ symbol
* `[a-zA-Z0-9.-]+` → domain
* `\.[a-zA-Z]{2,}` → top-level domain (.com, .org, .rs)

### b) Log File Search

Regex: `ERROR: .*`

* `.*` matches any text after "ERROR:"
* Useful for filtering logs in automated or manual testing.

### c) Parsing API Responses

Regex: `"id":\s*(\d+)`

* `\s*` → zero or more whitespace
* `(\d+)` → captures the numeric ID from JSON responses.

### d) URL Validation

Regex: `https?://\S+`

* `https?` → matches "http" or "https"
* `\S+` → one or more non-whitespace characters

### e) Form and Data Validation Examples

* Phone number: `^\+?\d{1,3}[- ]?\d{6,10}$`
* Date (YYYY-MM-DD): `^\d{4}-\d{2}-\d{2}$`
* Postal code (US): `^\d{5}(-\d{4})?$`

---

## 5. Best Practices in QA

* Keep regex simple and readable.
* Comment complex patterns.
* Test regex with multiple examples (valid/invalid cases).
* Use capturing groups only when needed.
* Avoid overly greedy patterns; prefer lazy quantifiers if appropriate.
* Integrate regex validation in automated test scripts for input fields, API responses, and log analysis.

---
