# Advanced SQL Concepts

## 1. Introduction to Advanced SQL

Advanced SQL goes beyond basic CRUD operations and focuses on query optimization, multi-table operations, data integrity, and database design.
As a QA engineer, advanced SQL knowledge is essential to validate complex data flows, business rules, and performance-critical queries.

## 2. Working with Multiple Tables (JOINs)

### 2.1 What is a JOIN?

A JOIN combines data from two or more tables based on a related column. JOINs are critical when testing scenarios where multiple entities interact, such as users and their orders.

### 2.2 Types of JOINs

1. INNER JOIN
   Returns rows with matching values in both tables.

```sql
SELECT users.name, orders.id, orders.amount
FROM users
INNER JOIN orders ON users.id = orders.user_id;
```

2. LEFT JOIN (LEFT OUTER JOIN)
   Returns all rows from the left table, even if there is no matching row in the right table.

```sql
SELECT users.name, orders.id
FROM users
LEFT JOIN orders ON users.id = orders.user_id;
```

3. RIGHT JOIN (RIGHT OUTER JOIN)
   Returns all rows from the right table.

```sql
SELECT users.name, orders.id
FROM users
RIGHT JOIN orders ON users.id = orders.user_id;
```

4. FULL OUTER JOIN
   Returns all rows from both tables, with NULL values where no match exists.

```sql
SELECT users.name, orders.id
FROM users
FULL OUTER JOIN orders ON users.id = orders.user_id;
```

5. CROSS JOIN
   Returns the Cartesian product of both tables.

```sql
SELECT users.name, products.name
FROM users
CROSS JOIN products;
```

QA Note: JOINs are commonly used to verify relationships, combined datasets, and report outputs during testing.

## 3. Indexing

### 3.1 What is an Index?

An index is a database structure that improves query performance by enabling faster data retrieval. It works similarly to an index in a book, reducing the need for full table scans.

### 3.2 Creating Indexes

```sql
CREATE INDEX idx_users_email ON users(email);
```

Indexes can be single-column or composite. QA engineers should be aware of indexes when validating performance-critical queries.

### 3.3 Considerations

* Indexes improve read performance.
* Indexes may slow down write operations (INSERT, UPDATE, DELETE).
* Knowing indexed columns helps simulate realistic test conditions.

## 4. Database Normalization

### 4.1 Purpose of Normalization

Normalization structures data to:

* Reduce redundancy
* Ensure data integrity
* Improve maintainability

### 4.2 Normal Forms

1. 1NF – Atomic values, no repeating groups
2. 2NF – All non-key attributes depend on the full primary key
3. 3NF – No transitive dependencies

Example (denormalized):

* order_id
* user_name
* product_name
* quantity

Normalized structure:

* users table: user_id, name
* products table: product_id, name
* orders table: order_id, user_id, product_id, quantity

QA Note: Normalized schemas require JOINs to validate complete datasets and relationships.

## 5. Advanced Querying Techniques

### 5.1 Aggregations Across Tables

```sql
SELECT users.name, SUM(orders.amount) AS total_spent
FROM users
INNER JOIN orders ON users.id = orders.user_id
GROUP BY users.name;
```

Used for validating totals, reports, and KPIs.

### 5.2 Subqueries and Nested Queries

```sql
SELECT name
FROM users
WHERE id IN (
    SELECT user_id
    FROM orders
    WHERE amount > 100
);
```

Useful for validating conditional relationships between entities.

### 5.3 Views

Views are virtual tables created from queries.

```sql
CREATE VIEW user_orders AS
SELECT users.name, orders.id, orders.amount
FROM users
INNER JOIN orders ON users.id = orders.user_id;
```

Views simplify reusable validations in tests.

## 6. How Database Design Impacts Testing

### 6.1 Test Data Preparation

* Normalized databases require inserting related records across multiple tables.
* Example: testing an order requires a user and product to exist first.

### 6.2 Test Verification

* JOINs are required for end-to-end data validation.
* Aggregations (SUM, COUNT, AVG) are essential for reporting tests.

### 6.3 Performance Testing

* Indexes, table size, and query complexity directly impact response times.
* QA may need to validate execution speed under realistic load.

## 7. QA Best Practices with Advanced SQL

1. Use transactions to keep test data consistent.
2. Verify foreign key constraints during testing.
3. Run SELECT queries before INSERT or UPDATE operations.
4. Combine JOINs and aggregations for complex validations.
5. Understand indexes to test realistic performance behavior.
6. Carefully validate normalized relationships to avoid subtle data bugs.

## 8. Summary

Advanced SQL enables QA engineers to:

* Validate multi-table relationships using JOINs
* Understand indexing and performance behavior
* Work effectively with normalized databases
* Prepare and verify complex test data
* Ensure data integrity and consistency

Strong SQL skills significantly improve backend validation, reporting accuracy, and performance testing.