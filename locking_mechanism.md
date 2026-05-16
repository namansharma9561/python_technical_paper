# Locking Mechanism in Databases

## Introduction

Locking mechanisms are used in database systems to control concurrent access to data. Locks prevent conflicts when multiple transactions attempt to access or modify the same resource simultaneously.

Without locking, concurrent operations may cause inconsistent or corrupted data.

---

# Purpose of Locking

Locks help:

- Maintain consistency
- Prevent data corruption
- Ensure isolation
- Control concurrent access

---

# Types of Locks

## Shared Lock

Allows multiple transactions to read data but prevents modification.

### Example

```sql
SELECT *
FROM employees
WHERE id = 1;
```

---

## Exclusive Lock

Allows one transaction to modify data while blocking others.

### Example

```sql
SELECT *
FROM employees
WHERE id = 1
FOR UPDATE;
```

---

# Row-Level Lock

Locks specific rows instead of the entire table.

Advantages:

- Better concurrency
- Reduced blocking

---

# Table-Level Lock

Locks the entire table.

```sql
LOCK TABLE employees IN EXCLUSIVE MODE;
```

---

# Deadlock

A deadlock occurs when two or more transactions wait indefinitely for each other’s locks.

### Example

- Transaction A locks Row 1
- Transaction B locks Row 2
- Both wait for each other

Database systems automatically detect deadlocks and terminate one transaction.

---

# Advantages of Locking

- Prevents conflicts
- Maintains integrity
- Supports multi-user systems
- Ensures transaction isolation

---

# Disadvantages of Locking

- Performance overhead
- Reduced concurrency
- Deadlock possibilities

---

# Real-World Applications

Locking is used in:

- Banking applications
- Ticket booking systems
- Inventory systems
- Online payment platforms

---
