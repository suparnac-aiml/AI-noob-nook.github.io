---
layout: default
title: "Day 16: SQL Basics – Querying and Managing Databases"
permalink: /day16/
---

# Day 16: SQL Basics – Querying and Managing Databases

## Introduction  
Structured Query Language (SQL) is a powerful tool for managing and querying relational databases. It’s an essential skill for anyone working in data-related fields, enabling you to retrieve, manipulate, and analyze data stored in structured formats.  

In this guide, we’ll cover the foundational concepts of SQL, common commands, and practical examples to get you started on your SQL journey.  

---

## Table of Contents

- [Why Learn SQL?](#Why)
- [Key SQL Concepts](#Concepts)
- [Basic SQL Syntax](#Syntax)
- [Common SQL Commands](#SQLCommands)
- [Practical SQL Use Cases](#UseCases)
- [Best Practices for SQL](#BestPractices)
- [Practice](#Practice)
- [Wrap-Up](#Wrap-Up)

- <a href="{{ site.baseurl }}/day15/" style="font-size: 16px;">  Day 15: Exploratory Data Analysis (EDA) – Extracting Insights from Data </a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day17/" style="font-size: 16px;"> Day 17: Advanced SQL Queries & Data Manipulation (Upcoming) </a>


---

## Why Learn SQL?  <a name="Why"></a>
- **Universal Language for Data**: SQL is used across industries for database interaction.    
- **Efficient Data Management**: Easily retrieve, update, and manipulate data.    
- **Data Analysis**: Extract insights directly from databases.    
- **Integration**: Works seamlessly with other tools like Python and BI platforms.    

---

## Key SQL Concepts   <a name="Concepts"></a>
- **Database**: An organized collection of data.    
- **Table**: A structured format consisting of rows (records) and columns (fields).    
- **Query**: A request to retrieve or manipulate data from a database.    

---

## Basic SQL Syntax   <a name="Syntax"></a>

```sql
-- General structure of a query
SELECT column1, column2 
FROM table_name 
WHERE condition;
```

---

## Common SQL Commands <a name="SQLCommands"></a>
**1. Creating a Database and Table**  

```sql
-- Create a new database
CREATE DATABASE example_db;

-- Use the database
USE example_db;

-- Create a table
CREATE TABLE employees (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50),
    department VARCHAR(50),
    salary DECIMAL(10, 2)
);
```

**2. Inserting Data**

```sql
-- Insert records into the table
INSERT INTO employees (name, department, salary) 
VALUES 
('Alice', 'HR', 50000),
('Bob', 'IT', 60000),
('Charlie', 'Finance', 55000);
```

**3. Retrieving Data**

```sql
-- Retrieve all columns
SELECT * FROM employees;

-- Retrieve specific columns
SELECT name, salary FROM employees;

-- Retrieve data with conditions
SELECT * FROM employees WHERE department = 'IT';
```

**4. Updating Data**

```sql
-- Update salary for an employee
UPDATE employees 
SET salary = 65000 
WHERE name = 'Bob';
```

**5. Deleting Data**

```sql
-- Delete a record
DELETE FROM employees 
WHERE name = 'Charlie';
```

**6. Filtering Data**

```sql
-- Use logical operators
SELECT * FROM employees 
WHERE salary > 50000 AND department = 'IT';

-- Use wildcard for pattern matching
SELECT * FROM employees 
WHERE name LIKE 'A%';
```

**7. Sorting Data**

```sql
-- Sort in ascending order
SELECT * FROM employees 
ORDER BY salary ASC;

-- Sort in descending order
SELECT * FROM employees 
ORDER BY salary DESC;
```

**8. Aggregating Data**

```sql
-- Count the number of employees
SELECT COUNT(*) AS total_employees FROM employees;

-- Find the average salary
SELECT AVG(salary) AS average_salary FROM employees;

-- Find the highest salary
SELECT MAX(salary) AS highest_salary FROM employees;
```

**9. Grouping Data**

```sql
-- Group employees by department and calculate the average salary
SELECT department, AVG(salary) AS average_salary 
FROM employees 
GROUP BY department;

-- Filter groups using HAVING
SELECT department, COUNT(*) AS total_employees 
FROM employees 
GROUP BY department 
HAVING total_employees > 1;
```

**10. Joining Tables**

```sql
-- Create another table
CREATE TABLE departments (
    department_id INT PRIMARY KEY AUTO_INCREMENT,
    department_name VARCHAR(50)
);

-- Insert data into departments
INSERT INTO departments (department_name) 
VALUES ('HR'), ('IT'), ('Finance');

-- Inner Join example
SELECT employees.name, departments.department_name 
FROM employees 
INNER JOIN departments 
ON employees.department = departments.department_name;

```

---

## **Practical SQL Use Cases**  <a name="UseCases"></a>
1. **Employee Management:** Query employee details based on roles, salaries, or departments.   
2. **Sales Analysis:** Analyze sales data by regions or products.   
3. **Customer Insights:** Extract customer data for marketing or service improvements.

---

## **Best Practices for SQL** <a name="BestPractices"></a>
1. **Keep Queries Readable:** Use proper formatting and comments.   
2. **Optimize Performance:** Avoid unnecessary joins and large SELECT * queries.    
3. **Secure Your Database:** Use parameterized queries to prevent SQL injection.   
4. **Backup Your Data:** Regularly backup databases to prevent data loss.

---

## **Practice** <a name="Practice"></a>
- Create a small database with tables (e.g., Students, Courses).  
- Perform CRUD operations (Create, Read, Update, Delete).  
- Use aggregate functions to extract insights.

---

## **Wrap-Up** <a name="Wrap-Up"></a>
SQL is the backbone of relational database management. By learning the basics, you can effectively query and manipulate data for analysis or integration into applications. As you practice, you’ll find SQL to be an invaluable skill in your data journey.

**Keep practicing, keep querying!**

---

- <a href="{{ site.baseurl }}/day15/" style="font-size: 16px;">  Day 15: Exploratory Data Analysis (EDA) – Extracting Insights from Data </a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day17/" style="font-size: 16px;"> Day 17: Advanced SQL Queries & Data Manipulation (Upcoming) </a>
