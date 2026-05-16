# Triggers in Databases

## Introduction

Triggers are special stored procedures that automatically execute when specific events occur in a database table.

Triggers are commonly used for:

- Auditing
- Validation
- Logging
- Automation
- Security enforcement

---

# Types of Triggers

## BEFORE Trigger

Executes before an operation occurs.

### Example

```sql
CREATE TRIGGER before_insert
BEFORE INSERT
ON employees
FOR EACH ROW
EXECUTE FUNCTION validate_salary();
```

---

## AFTER Trigger

Executes after an operation completes.

### Example

```sql
CREATE TRIGGER after_update
AFTER UPDATE
ON employees
FOR EACH ROW
EXECUTE FUNCTION audit_changes();
```

---

# Trigger Events

Triggers can execute on:

- INSERT
- UPDATE
- DELETE

---

# Example of Audit Trigger

```sql
CREATE TABLE employee_log (
    employee_id INT,
    action_time TIMESTAMP
);
```

Trigger:

```sql
CREATE TRIGGER log_employee_insert
AFTER INSERT
ON employees
FOR EACH ROW
EXECUTE FUNCTION log_insert();
```

---

# Advantages of Triggers

- Automation
- Improved integrity
- Centralized business logic
- Automatic auditing

---

# Disadvantages of Triggers

- Harder debugging
- Increased complexity
- Hidden execution flow
- Performance overhead

---

# Real-World Applications

Triggers are used in:

- Audit logging systems
- Banking applications
- Security monitoring
- Inventory tracking
- Automatic notifications

---
