# SQL Fundamentals for QA (CS50-Based)

## 1. Definition & Purpose

SQL (Structured Query Language) is used to create, read, update, and delete data in relational databases.

Purpose for QA:

* Verify data correctness
* Validate business rules
* Analyze defects
* Support backend testing

## 2. Databases and DBMS

A database is an organized collection of data that supports CRUD operations.
A Database Management System (DBMS) is software used to interact with databases.

Common DBMS examples:

* MySQL
* PostgreSQL
* SQLite
* Oracle
* MongoDB

## 3. SQL Basics

SQL allows querying and manipulating structured data stored in tables.
A table consists of rows (records) and columns (fields).

Example:

```sql
SELECT title, author FROM books;
```

## 4. Querying Data

* SELECT retrieves data from tables
* WHERE filters rows based on conditions
* LIMIT restricts the number of returned rows
* ORDER BY sorts results

Examples:

```sql
SELECT * FROM books LIMIT 10;
SELECT title FROM books WHERE year = 2023;
SELECT title, rating FROM books ORDER BY rating DESC;
```

## 5. Filtering and Conditions

Operators include =, !=, <, >, BETWEEN, AND, OR.
NULL represents missing data and must be checked using IS NULL.

Examples:

```sql
SELECT title FROM books WHERE rating > 4.0;
SELECT title FROM books WHERE translator IS NULL;
```

## 6. Pattern Matching

LIKE is used for partial string matching.

Example:

```sql
SELECT title FROM books WHERE title LIKE '%love%';
```

## 7. Aggregate Functions

Used to calculate values across multiple rows.

Common functions:

* COUNT
* AVG
* MIN
* MAX
* SUM

Examples:

```sql
SELECT COUNT(*) FROM books;
SELECT ROUND(AVG(rating), 2) FROM ratings;
```

## 8. Relational Databases

Tables are connected using keys.

* Primary Key: uniquely identifies a row
* Foreign Key: references another table

QA focus: ensure data relationships are valid and consistent.

## 9. Joins

Joins combine rows from multiple tables based on relationships.

Example:

```sql
SELECT authors.name, books.title
FROM authors
JOIN authored ON authors.id = authored.author_id
JOIN books ON books.id = authored.book_id;
```

## 10. Subqueries

A query inside another query, often used for complex lookups.

Example:

```sql
SELECT title FROM books
WHERE publisher_id = (
  SELECT id FROM publishers WHERE publisher = 'Fitzcarraldo Editions'
);
```

## 11. Transactions

A transaction is a unit of work that must fully succeed or fail.

ACID principles:

* Atomicity
* Consistency
* Isolation
* Durability

Example:

```sql
BEGIN TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```

QA focus: verify rollback on failure and data consistency.

## 12. Indexes and Performance

Indexes speed up data retrieval.
Without indexes, databases perform linear searches.

Example:

```sql
CREATE INDEX idx_users_email ON users(email);
```

QA role: detect slow queries and missing indexes.

## 13. Views

A view is a virtual table defined by a query.
Used to simplify queries and restrict data access.

Example:

```sql
CREATE VIEW active_users AS
SELECT * FROM users WHERE deleted = 0;
```

## 14. Edge Cases for QA

Test:

* NULL values
* Duplicates
* Invalid formats
* Boundary values

Verify constraints such as NOT NULL, UNIQUE, and CHECK.

## 15. Security Awareness

SQL Injection occurs when user input is executed as SQL.

QA responsibility:

* Verify inputs are parameterized
* Ensure injection attempts fail safely

## 16. Scaling Concepts

Scaling means handling more data or users without failure.

QA focus:

* Detect slow queries as data grows
* Test behavior under larger datasets
* Report performance degradation