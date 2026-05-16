# Normalization in Databases

## Introduction

Normalization is a database design technique used to organize data efficiently in relational database systems. The primary goal of normalization is to reduce data redundancy and improve data integrity by dividing large tables into smaller related tables.

In poorly designed databases, the same information may be repeated multiple times, leading to storage inefficiency and update anomalies. Normalization solves these issues by structuring data according to specific rules known as normal forms.

Relational database management systems such as :contentReference[oaicite:0]{index=0}, :contentReference[oaicite:1]{index=1}, and :contentReference[oaicite:2]{index=2} use normalization extensively.

---

# Objectives of Normalization

The major objectives are:

- Reduce duplicate data
- Improve data consistency
- Eliminate insertion, deletion, and update anomalies
- Improve database organization
- Simplify maintenance

---

# Data Redundancy

Data redundancy occurs when the same information is stored repeatedly.

### Example

| Student_ID | Student_Name | Course | Instructor |
|---|---|---|---|
| 1 | Rahul | DBMS | Sharma |
| 1 | Rahul | SQL | Sharma |

Here, student and instructor names are repeated unnecessarily.

---

# First Normal Form (1NF)

A table is in 1NF if:

- Each column contains atomic values
- No repeating groups exist
- Each row is unique

### Non-Normalized Table

| Student_ID | Subjects |
|---|---|
| 1 | DBMS, SQL |

### 1NF Table

| Student_ID | Subject |
|---|---|
| 1 | DBMS |
| 1 | SQL |

---

# Second Normal Form (2NF)

A table is in 2NF if:

- It satisfies 1NF
- No partial dependency exists

Partial dependency occurs when a non-key attribute depends only on part of a composite primary key.

---

# Third Normal Form (3NF)

A table is in 3NF if:

- It satisfies 2NF
- No transitive dependency exists

Transitive dependency occurs when a non-key attribute depends on another non-key attribute.

---

# Boyce-Codd Normal Form (BCNF)

BCNF is a stricter version of 3NF.

A table is in BCNF if every determinant is a candidate key.

---

# Advantages of Normalization

- Reduces redundancy
- Improves consistency
- Prevents anomalies
- Saves storage space
- Simplifies updates

---

# Disadvantages of Normalization

- More tables are created
- Complex joins may reduce performance
- Query writing becomes more complicated

---

# Real-World Applications

Normalization is used in:

- Banking systems
- University databases
- Hospital management systems
- E-commerce applications
- Payroll systems

---
