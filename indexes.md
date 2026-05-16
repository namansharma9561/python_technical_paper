# Indexes in Databases

## Introduction

Indexes are special database objects used to improve the speed of data retrieval operations. An index works similarly to an index in a book, allowing the database system to locate rows quickly without scanning the entire table.

Indexes are extremely important in large databases where tables may contain millions of rows.

---

# Why Indexes are Needed

Without indexes, databases perform a full table scan to find matching records.

### Example

```sql
SELECT *
FROM employees
WHERE email = 'abc@gmail.com';
```

If the table contains millions of rows, searching becomes slow.

Indexes reduce search time significantly.

---

# How Indexes Work

Indexes store references to table rows in sorted order.

Common data structures used:

- B-Tree
- Hash indexes
- Bitmap indexes

---

# Types of Indexes

## Single Column Index

Created on one column.

```sql
CREATE INDEX idx_name
ON employees(name);
```

---

## Composite Index

Created on multiple columns.

```sql
CREATE INDEX idx_employee
ON employees(department_id, salary);
```

---

## Unique Index

Ensures all values are unique.

```sql
CREATE UNIQUE INDEX idx_email
ON employees(email);
```

---

## Primary Key Index

Automatically created when a primary key is defined.

```sql
CREATE TABLE employees (
    id INT PRIMARY KEY
);
```

---

# Advantages of Indexes

- Faster searching
- Improved query performance
- Efficient sorting
- Better filtering
- Faster joins

---

# Disadvantages of Indexes

- Increased storage usage
- Slower INSERT and UPDATE operations
- Additional maintenance overhead

---

# Real-World Applications

Indexes are used in:

- Search engines
- Banking systems
- E-commerce platforms
- Social media applications
- Analytics systems

---
