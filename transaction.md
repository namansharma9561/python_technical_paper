# Transactions in Databases

## Introduction

A transaction is a sequence of one or more database operations treated as a single logical unit of work. Transactions ensure that database operations are completed reliably and maintain consistency even during failures.

Transactions are fundamental in relational database systems and support ACID properties.

---

# ACID Properties

Transactions follow ACID principles:

- Atomicity
- Consistency
- Isolation
- Durability

These properties guarantee reliable transaction processing.

---

# Transaction Commands

## BEGIN

Starts a transaction.

```sql
BEGIN;
```

---

## COMMIT

Saves all changes permanently.

```sql
COMMIT;
```

---

## ROLLBACK

Undoes changes if an error occurs.

```sql
ROLLBACK;
```

---

# Example of Transaction

```sql
BEGIN;

UPDATE accounts
SET balance = balance - 500
WHERE id = 1;

UPDATE accounts
SET balance = balance + 500
WHERE id = 2;

COMMIT;
```

This transaction transfers money between accounts.

---

# Importance of Transactions

- Prevents partial updates
- Maintains consistency
- Supports concurrent access
- Provides recovery during failures

---

# Real-World Applications

Transactions are essential in:

- Banking systems
- Airline reservation systems
- Online shopping
- Payroll systems
- Inventory management

---

# Advantages of Transactions

- Reliable operations
- Error recovery
- Data integrity
- Concurrency control

---
