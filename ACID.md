# ACID Properties in Database Management Systems

## Abstract

ACID is a set of fundamental properties used in database systems to ensure reliable and consistent transaction processing. The acronym ACID stands for Atomicity, Consistency, Isolation, and Durability. These properties are critical in relational database management systems (RDBMS) such as :contentReference[oaicite:0]{index=0}, :contentReference[oaicite:1]{index=1}, and :contentReference[oaicite:2]{index=2}. ACID guarantees that database transactions are processed safely even in the presence of system failures, crashes, or concurrent access.

---

# Introduction

A transaction is a sequence of database operations treated as a single logical unit of work. Database systems must maintain data correctness and integrity while handling multiple users and potential failures. ACID properties provide the rules that guarantee dependable transaction execution.

Example of a transaction:

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

The above transaction transfers money from one account to another. ACID ensures the operation is completed correctly and safely.

---

# 1. Atomicity

## Definition

Atomicity guarantees that a transaction is treated as a single indivisible unit. Either all operations inside the transaction are executed successfully, or none of them are applied.

This property prevents partial updates from occurring.

---

## Example

Consider a banking transaction:

```sql
BEGIN;

UPDATE accounts
SET balance = balance - 1000
WHERE id = 1;

UPDATE accounts
SET balance = balance + 1000
WHERE id = 2;

COMMIT;
```

If the system crashes after deducting money from account 1 but before adding money to account 2, the database system automatically rolls back the transaction.

---

## Rollback Example

```sql
ROLLBACK;
```

Rollback restores the database to its previous consistent state.

---

## Importance of Atomicity

- Prevents incomplete transactions
- Ensures reliable financial operations
- Protects against system failures
- Maintains transaction integrity

---

# 2. Consistency

## Definition

Consistency ensures that a transaction moves the database from one valid state to another valid state while preserving all predefined rules, constraints, and relationships.

---

## Database Constraints

Examples of constraints:

```sql
CREATE TABLE employees (
    id INT PRIMARY KEY,
    salary INT CHECK (salary > 0)
);
```

The database prevents insertion of invalid values:

```sql
INSERT INTO employees VALUES (1, -5000);
```

This operation fails because it violates the constraint.

---

## Importance of Consistency

- Preserves data integrity
- Prevents invalid records
- Enforces business rules
- Maintains referential integrity

---

# 3. Isolation

## Definition

Isolation ensures that multiple transactions executing concurrently do not interfere with each other.

Each transaction behaves as if it is running independently.

---

## Concurrent Transaction Problem

Without isolation:

Transaction A:

```sql
UPDATE accounts
SET balance = balance - 100
WHERE id = 1;
```

Transaction B simultaneously reads the same account balance before Transaction A completes.

This may result in incorrect or inconsistent data.

---

## Isolation Levels

SQL databases provide multiple isolation levels:

| Isolation Level | Description |
|---|---|
| Read Uncommitted | Allows dirty reads |
| Read Committed | Prevents dirty reads |
| Repeatable Read | Prevents non-repeatable reads |
| Serializable | Highest isolation level |

---

## Setting Isolation Level

```sql
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE;
```

---

## Importance of Isolation

- Prevents data corruption
- Supports concurrent users safely
- Avoids race conditions
- Ensures predictable transaction behavior

---

# 4. Durability

## Definition

Durability guarantees that once a transaction is committed, the changes are permanently stored even if the system crashes immediately afterward.

---

## Commit Example

```sql
COMMIT;
```

After commit execution:

- Data is written to persistent storage
- Changes survive power failures
- Recovery systems can restore committed data

---

## Recovery Mechanisms

Database systems achieve durability using:

- Write-Ahead Logging (WAL)
- Transaction logs
- Checkpoints
- Backup systems

Example in PostgreSQL:

```sql
SHOW wal_level;
```

---

## Importance of Durability

- Prevents data loss
- Ensures permanent storage
- Supports crash recovery
- Provides transaction reliability

---

# ACID in PostgreSQL

:contentReference[oaicite:3]{index=3} fully supports ACID properties.

Example transaction:

```sql
BEGIN;

INSERT INTO orders VALUES (101, 'Laptop', 1);

UPDATE inventory
SET quantity = quantity - 1
WHERE product = 'Laptop';

COMMIT;
```

If any operation fails:

```sql
ROLLBACK;
```

PostgreSQL restores the database to the previous stable state.

---

# Advantages of ACID

| Property | Advantage |
|---|---|
| Atomicity | Prevents partial transactions |
| Consistency | Maintains valid data |
| Isolation | Supports safe concurrency |
| Durability | Prevents committed data loss |

---

# Limitations of ACID

- Increased system overhead
- Reduced performance in highly distributed systems
- Locking may reduce concurrency
- Serializable isolation can be expensive

---

# Real-World Applications

ACID properties are essential in:

- Banking systems
- Airline reservation systems
- E-commerce platforms
- Payroll systems
- Healthcare databases

---
