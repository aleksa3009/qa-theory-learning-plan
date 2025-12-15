# SQL and Relational Databases

## 1. Introduction to Databases

A database is a structured repository of data that allows storage, retrieval, modification, and deletion of information. Databases are critical in almost every software application because they hold the underlying data that powers the application logic.

### Types of Databases

#### 1. Relational Databases (RDBMS)

* Store data in tables (rows = records, columns = fields).
* Use SQL (Structured Query Language) to manipulate and query data.
* Relationships are defined between tables using primary keys and foreign keys.
* Examples: MySQL, PostgreSQL, Oracle, SQL Server.

#### 2. Non-Relational Databases (NoSQL)

* Schema-less or flexible schema.
* Data can be key-value pairs, documents, graphs, or wide-column stores.
* Useful for highly scalable applications with unstructured data.
* Examples: MongoDB, Redis, Cassandra, DynamoDB.

QA perspective: Relational databases are more common in enterprise applications, and most automation and API tests interact with them.

## 2. Key Database Concepts

### 2.1 Tables

* A table consists of rows and columns.
* Example table `users`:

```
id | name    | email              | role
1  | Alice   | alice@test.com     | admin
2  | Bob     | bob@test.com       | user
3  | Charlie | charlie@test.com   | user
```

* Each row is a unique record.
* Each column defines the type of data (text, number, date).

### 2.2 Keys

#### 1. Primary Key (PK)

Uniquely identifies each row in a table.
Example: `id` in the `users` table.

#### 2. Foreign Key (FK)

Establishes a link between two tables.
Example: `orders.user_id` referencing `users.id`.

### 2.3 Relationships

* One-to-One: a row in Table A matches exactly one row in Table B.
* One-to-Many: a row in Table A can have multiple corresponding rows in Table B.
* Many-to-Many: multiple rows in Table A relate to multiple rows in Table B using a junction table.

## 3. SQL Basics

### 3.1 SELECT – Retrieve Data

```
SELECT * FROM users;
SELECT name, email FROM users WHERE role = 'admin';
SELECT id, name FROM users ORDER BY name ASC LIMIT 5;
```

* WHERE – filter rows.
* ORDER BY – sort results.
* LIMIT / OFFSET – control result size for pagination.

### 3.2 INSERT – Add New Data

```
INSERT INTO users (name, email, role)
VALUES ('David', 'david@test.com', 'user');
```

QA can use this to prepare test data.

### 3.3 UPDATE – Modify Existing Data

```
UPDATE users
SET role = 'moderator'
WHERE name = 'Bob';
```

Always use WHERE to avoid updating all rows accidentally.

### 3.4 DELETE – Remove Data

```
DELETE FROM users
WHERE name = 'David';
```

Use transactions to ensure safety when deleting in tests.

## 4. Joins – Combining Tables

Joins allow retrieving data from multiple tables simultaneously.

### Examples

```
-- INNER JOIN: only matching rows
SELECT orders.id, users.name, orders.amount
FROM orders
INNER JOIN users ON orders.user_id = users.id;

-- LEFT JOIN: all users, even if they have no orders
SELECT users.name, orders.id
FROM users
LEFT JOIN orders ON users.id = orders.user_id;
```

Other types include RIGHT JOIN, FULL OUTER JOIN, and CROSS JOIN.

## 5. Aggregations and Grouping

```
SELECT COUNT(*) FROM users;
SELECT AVG(amount) FROM orders;
SELECT role, COUNT(*) FROM users GROUP BY role;
```

Used to verify totals, metrics, and reports in QA tests.

## 6. Subqueries and Nested Queries

```
SELECT name FROM users
WHERE id IN (
    SELECT user_id FROM orders WHERE amount > 100
);
```

Useful for complex validations such as identifying users with high-value orders.

## 7. Transactions and Data Integrity

Transactions ensure multiple SQL statements execute as a single unit.

```
BEGIN;
INSERT INTO orders (user_id, amount) VALUES (1, 200);
UPDATE users SET balance = balance - 200 WHERE id = 1;
COMMIT;
-- ROLLBACK; to undo changes if an error occurs
```

QA can use transactions to safely roll back test data.

## 8. Indexes

Indexes improve query performance for large tables.

```
CREATE INDEX idx_user_email ON users(email);
```

QA may need to verify that performance-critical queries use indexes correctly.

## 9. Normalization

Normalization organizes data to reduce redundancy and maintain integrity.

* 1NF: no repeating groups
* 2NF: all columns depend on the primary key
* 3NF: no transitive dependencies

Example: separating `users` and `orders` instead of combining all data in one table.

## 10. Common QA Tasks Using SQL

1. Verify data after a UI operation.
2. Validate CRUD operations.
3. Check data relationships between tables.
4. Prepare test data for automation.
5. Clean up test data after tests.
6. Inspect database state during debugging.

## 11. Useful SQL Commands for QA

```
-- View all tables
SHOW TABLES;          -- MySQL
\dt                  -- PostgreSQL

-- View table structure
DESCRIBE users;      -- MySQL
\d users             -- PostgreSQL

-- Limit query results
SELECT * FROM users LIMIT 10;

-- Count rows
SELECT COUNT(*) FROM orders;

-- Check duplicates
SELECT email, COUNT(*)
FROM users
GROUP BY email
HAVING COUNT(*) > 1;

-- Delete all rows (use with caution)
DELETE FROM table_name;
```

## 12. QA Best Practices with SQL

* Always work in test or staging environments.
* Use transactions for safe setup and teardown.
* Combine SQL queries with assertions in automated tests.
* Validate both positive and negative scenarios.
* Use joins and aggregations for complex data verification.

## 13. Summary

SQL is the standard language for working with relational databases. QA engineers must understand core SQL operations, relationships, normalization, indexing, and transactions to effectively validate data integrity, prepare test data, debug issues, and support automated testing.