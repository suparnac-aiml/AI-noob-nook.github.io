---
layout: default
title: "Day 17: Advanced SQL Queries & Data Manipulation"
permalink: /day17/
---

# Day 17: Advanced SQL Queries & Data Manipulation  

SQL offers powerful tools to handle complex data manipulation and querying tasks. Today's focus is on advanced SQL techniques, enabling you to extract insights, manage large datasets, and optimize query performance.  

---

## Table of Contents
- [Advanced Filtering with Subqueries](#Advanced-Filtering-with-Subqueries)
- [Joins: Combining Tables](#Joins-Combining-Tables)
- [Set Operations](#Set-Operations)
- [Common Table Expressions (CTEs)](#Common-Table-Expressions)
- [Working with Built-in Functions](#Working-with-Built-in-Functions)
- [Window Functions](#Window-Functions)
- [Transactions and Data Integrity](#Transactions-and-Data-Integrity)
- [Indexing for Performance Optimization](#Indexing-for-Performance-Optimization)
- [Practice](#Practice)

- <a href="{{ site.baseurl }}/day16/" style="font-size: 16px;">  Day 16: SQL Basics – Querying and Managing Databases </a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day18/" style="font-size: 16px;"> Day 18: Database Management & Optimization  </a>


---


## **1. Advanced Filtering with Subqueries**   <a name="Advanced-Filtering-with-Subqueries"></a>
Subqueries (or nested queries) allow you to write queries inside other queries, making it possible to handle complex filtering and comparisons.  

### **Key Concepts**
- **Subquery in `WHERE` Clause**: Filters data based on conditions defined in another query.
- **Subquery in `FROM` Clause**: Acts as a temporary table.
- **Subquery in `SELECT` Clause**: Calculates derived values.

### **Example**  
Retrieve employees earning more than the average salary of their department:  

```sql
SELECT name, salary, department
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
    GROUP BY department
    HAVING department = employees.department
);
```

---

## **2. Joins: Combining Tables**  <a name="Joins-Combining-Tables"></a>
Joins allow combining rows from two or more tables based on related columns.

### **Types of Joins**
- **Inner Join:** Returns rows with matching values in both tables.  
- **Left Join:** Returns all rows from the left table, with matching rows from the right table.  
- **Right Join:** Returns all rows from the right table, with matching rows from the left table.  
- **Full Outer Join:** Returns all rows with matches from either table.  
- **Self Join:** Joins a table with itself.

### **Example**
List employees and their managers:
```sql
SELECT e.name AS Employee, m.name AS Manager
FROM employees e
INNER JOIN employees m
ON e.manager_id = m.id;
```

---

## **3. Set Operations  <a name="Set-Operations"></a>
Combine results of two or more queries using set operations.

**Types of Set Operations**
- **UNION:** Combines results, removing duplicates.  
- **UNION ALL:** Combines all results, including duplicates.  
- **INTERSECT:** Returns only common rows.  
- **EXCEPT (or MINUS):** Returns rows in the first query but not in the second.  

### **Example**
Combine employees from IT and HR departments:  

```sql
SELECT name FROM employees WHERE department = 'IT'
UNION
SELECT name FROM employees WHERE department = 'HR';

```

---

## 4. Common Table Expressions (CTEs)  <a name="Common-Table-Expressions"></a>
CTEs simplify complex queries by allowing you to define temporary result sets.

**Syntax**

```sql
WITH CTE_name AS (
    SELECT column1, column2
    FROM table
    WHERE condition
)
SELECT * FROM CTE_name;

```

### **Example**
Find top earners in each department:

```sql
WITH DepartmentSalaries AS (
    SELECT department, name, salary,
           RANK() OVER (PARTITION BY department ORDER BY salary DESC) AS rank
    FROM employees
)
SELECT * FROM DepartmentSalaries WHERE rank = 1;
```

---

## **5. Working with Built-in Functions**  <a name="Working-with-Built-in-Functions"></a>
Leverage SQL's powerful built-in functions for data manipulation and aggregation.  

**String Functions**  
- **CONCAT(), SUBSTRING(), UPPER(), LOWER().**    
- **Example**  
-  ```sql
   SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM employees;  
   ```

**Date Functions**  
- **CURRENT_DATE, DATEADD(), DATEDIFF().**  
- **Example:**  
-  ```sql
   SELECT name, DATEDIFF(CURRENT_DATE, hire_date) AS days_worked FROM employees;
   ```

**Aggregate Functions**  
- **SUM(), AVG(), COUNT(), MAX(), MIN().**  
- **Example:**  
- ```sql
     SELECT department, AVG(salary) AS avg_salary FROM employees GROUP BY department;  
   ```

---


## **6. Window Functions**  <a name="Window-Functions"></a>
Analyze data across rows without collapsing them into aggregates.  

**Key Functions**
- **ROW_NUMBER(), RANK(), DENSE_RANK(), LEAD(), LAG().**  
- **Example**  
  Rank employees by salary within each department

  ```sql
  SELECT name, department, salary,
       RANK() OVER (PARTITION BY department ORDER BY salary DESC) AS rank
  FROM employees;
  ```

---

## **7. Transactions and Data Integrity**  <a name="Transactions-and-Data-Integrity"></a>
Transactions ensure a sequence of SQL operations are executed as a single unit, maintaining data consistency.

**ACID Properties**  
- **Atomicity:** All or nothing.  
- **Consistency:** Keeps the database in a valid state.  
- **Isolation:** Transactions don’t interfere.  
- **Durability:** Changes are permanent.  
- **Example**  
  Transfer funds between accounts:
  
  ```sql
  BEGIN;
  UPDATE accounts SET balance = balance - 1000 WHERE account_id = 1;
  UPDATE accounts SET balance = balance + 1000 WHERE account_id = 2;
  COMMIT;
  ```

---

## **8. Indexing for Performance Optimization**  <a name="Indexing-for-Performance-Optimization"></a>
Indexes improve query performance by allowing faster data retrieval.  

**Creating Indexes**  

```sql
CREATE INDEX idx_salary ON employees(salary);
```

**Using ```sql EXPLAIN ``` for Query Analysis**  
Analyze query execution plans to identify bottlenecks.

---

## **Tasks for Practice** <a name="Practice"></a>
Write a query using subqueries and joins to find employees earning above the department average.
Use set operations to combine data from multiple tables.
Create a CTE to calculate cumulative sales by month.
Analyze query performance before and after adding an index.

---

Mastering these advanced SQL techniques empowers you to handle complex data operations with efficiency. Dive in and explore the possibilities! 🚀


- <a href="{{ site.baseurl }}/day16/" style="font-size: 16px;">  Day 16: SQL Basics – Querying and Managing Databases </a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day18/" style="font-size: 16px;"> Day 18: Database Management & Optimization </a>
