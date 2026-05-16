# Aggregations and Filters in SQL Queries

## Introduction

Aggregation and filtering are essential concepts in SQL used for analyzing and extracting meaningful information from databases. Aggregation functions summarize large datasets into smaller results, while filtering helps retrieve only relevant records based on specified conditions.

These operations are heavily used in business intelligence, analytics, financial reporting, and enterprise database systems.

---

# Aggregation Functions

Aggregation functions perform calculations on multiple rows and return a single summarized value.

---

## COUNT()

The COUNT() function returns the number of rows.

### Example

```sql
SELECT COUNT(*) AS total_employees
FROM employees;
```

---

## SUM()

The SUM() function calculates the total of numeric values.

### Example

```sql
SELECT SUM(salary) AS total_salary
FROM employees;
```

---

## AVG()

The AVG() function calculates the average value.

### Example

```sql
SELECT AVG(salary) AS average_salary
FROM employees;
```

---

## MAX()

Returns the maximum value.

### Example

```sql
SELECT MAX(salary)
FROM employees;
```

---

## MIN()

Returns the minimum value.

### Example

```sql
SELECT MIN(salary)
FROM employees;
```

---

# GROUP BY Clause

The GROUP BY clause groups rows having similar values into summary rows.

### Example

```sql
SELECT department_id, COUNT(*) AS employee_count
FROM employees
GROUP BY department_id;
```

This query groups employees based on department.

---

# HAVING Clause

The HAVING clause filters grouped data after aggregation.

### Example

```sql
SELECT department_id, AVG(salary)
FROM employees
GROUP BY department_id
HAVING AVG(salary) > 50000;
```

---

# WHERE Clause

The WHERE clause filters rows before aggregation occurs.

### Example

```sql
SELECT *
FROM employees
WHERE salary > 50000;
```

---

# Difference Between WHERE and HAVING

| Feature | WHERE | HAVING |
|---|---|---|
| Filters | Individual rows | Grouped rows |
| Used Before GROUP BY | Yes | No |
| Supports Aggregate Functions | No | Yes |

---

# Real-World Applications

Aggregation and filtering are used in:

- Sales reporting
- Financial analysis
- Attendance tracking
- Data analytics
- Dashboard generation

---

# Advantages

- Simplifies data analysis
- Supports reporting systems
- Enables statistical calculations
- Improves decision-making

---
