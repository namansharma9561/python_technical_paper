# Database Isolation Levels

## Introduction

Isolation levels define how transactions interact with one another in concurrent database systems. They determine the visibility of changes made by one transaction to other transactions.

Isolation levels help balance consistency and performance.

---

# Problems in Concurrent Transactions

## Dirty Read

Reading uncommitted data from another transaction.

---

## Non-Repeatable Read

Reading different values for the same row during a transaction.

---

## Phantom Read

New rows appear during repeated query execution.

---

# Isolation Levels

## 1. Read Uncommitted

Lowest isolation level.

Allows dirty reads.

```sql
SET TRANSACTION ISOLATION LEVEL READ UNCOMMITTED;
```

---

## 2. Read Committed

Prevents dirty reads.

```sql
SET TRANSACTION ISOLATION LEVEL READ COMMITTED;
```

This is the default isolation level in many databases.

---

## 3. Repeatable Read

Prevents non-repeatable reads.

```sql
SET TRANSACTION ISOLATION LEVEL REPEATABLE READ;
```

---

## 4. Serializable

Highest isolation level.

```sql
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE;
```

Provides complete isolation.

---

# Comparison Table

| Isolation Level | Dirty Reads | Non-Repeatable Reads | Phantom Reads |
|---|---|---|---|
| Read Uncommitted | Possible | Possible | Possible |
| Read Committed | Prevented | Possible | Possible |
| Repeatable Read | Prevented | Prevented | Possible |
| Serializable | Prevented | Prevented | Prevented |

---

# Advantages

- Maintains consistency
- Controls concurrency
- Prevents transaction anomalies

---

# Disadvantages

- Higher isolation reduces performance
- Increased locking overhead

---
