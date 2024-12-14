---
layout: default
title: "Day 18: Database Normalization, Transactions, Indexing, and Performance Tuning"
permalink: /day18/
---


# Day 18: Database Normalization, Transactions, Indexing, and Performance Tuning  

Efficient database design and management are crucial for handling large datasets effectively. Today’s focus is on normalization, transactions, indexing, and performance tuning to ensure data consistency, reduce redundancy, and optimize database operations.

---

## Table of Contents  
1. [Database Normalization](#database-normalization)  
   - Goals of Normalization
   - Normal Forms
2. [Transactions and ACID Properties](#transactions-and-acid-properties)  
   - Understanding Transactions
   - ACID Properties
   - Examples of Transactions
3. [Indexing in Databases](#indexing-in-databases)  
   - Types of Indexes
   - When to Use Indexes
   - Analyzing Query Performance
4. [Performance Tuning](#performance-tuning)  
   - Optimizing Queries
   - Database Partitioning
   - Best Practices
5. [Practice Tasks](#practice-tasks)  


- <a href="{{ site.baseurl }}/day17/" style="font-size: 16px;">  Day 17: Advanced SQL Queries & Data Manipulation </a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day19/" style="font-size: 16px;"> Day 19: SQL for analytics, pivoting, window functions, and automation with stored procedures. (Upcoming) </a>

---

## **1. Database Normalization**  <a name="database-normalization"></a>
Normalization is the process of organizing data to minimize redundancy and improve integrity.

### **Goals of Normalization**  
- Eliminate duplicate data.  
- Ensure logical data storage.  
- Enhance data integrity.  

### **Normal Forms**  
Normalization involves applying a series of rules called *normal forms (NF)*:  

#### **1NF (First Normal Form)**  
- Ensure that each column contains atomic values.  
- Example:

**Original Table:**  
| CustomerID | PhoneNumbers    |  
|------------|-----------------|  
| 1          | 12345, 67890    |  

**Normalized Table:**  
| CustomerID | PhoneNumber     |  
|------------|-----------------|  
| 1          | 12345           |  
| 1          | 67890           |  

#### **2NF (Second Normal Form)**   
- Data must be in 1NF and all non-key attributes must depend on the primary key.   

#### **3NF (Third Normal Form)**   
- Data must be in 2NF and all attributes must only depend on the primary key (no transitive dependency).  

#### **Boyce-Codd Normal Form (BCNF)**   
- Stronger version of 3NF. Every determinant must be a candidate key.   

---

## **2. Transactions and ACID Properties**  <a name="transactions-and-acid-properties"></a>

### **Understanding Transactions**   
A transaction is a sequence of database operations performed as a single logical unit.   

### **ACID Properties**   
1. **Atomicity**: All operations are completed, or none are.   
2. **Consistency**: Maintains database integrity.   
3. **Isolation**: Transactions do not interfere with each other.   
4. **Durability**: Committed changes are permanent.   

### **Examples of Transactions**  
#### Transfer Money Between Accounts:  

```sql
BEGIN;
UPDATE accounts SET balance = balance - 500 WHERE account_id = 1;
UPDATE accounts SET balance = balance + 500 WHERE account_id = 2;
COMMIT;
```

#### Rollback in Case of Error:

```sql
BEGIN;
UPDATE inventory SET quantity = quantity - 10 WHERE product_id = 101;
-- Simulate an error
ROLLBACK;
```

---

## **3. Indexing in Databases** <a name="indexing-in-databases"></a>

### **Types of Indexes**  

- **Single-Column Index:** For a single column.  
- **Composite Index:** For multiple columns.  
- **Unique Index:** Ensures unique values in a column.  
- **Full-Text Index:** For text searches.  


### **When to Use Indexes**

- Use for columns frequently queried in WHERE, ORDER BY, or GROUP BY clauses.  
- Avoid indexing columns with high update frequency.  
- Analyzing Query Performance  
- Use the EXPLAIN keyword to analyze query execution plans:  

```sql
EXPLAIN SELECT * FROM employees WHERE salary > 50000;
```

---


## **4. Performance Tuning** <a name="performance-tuning"></a>

### **Optimizing Queries**  

1. Use SELECT only required columns:  

```sql
SELECT name FROM employees;  -- Instead of SELECT *  
```

2. Avoid Complex Joins: Simplify where possible.  
3. Index Key Columns:  

```sql
CREATE INDEX idx_salary ON employees(salary);
```

**Database Partitioning**  
Partitioning divides a large table into smaller, more manageable pieces.  
 
- **Horizontal Partitioning:** Divides rows.    
- **Vertical Partitioning:** Divides columns.    


**Best Practices**  
- Regularly update statistics for query optimizers.    
- Archive old data to reduce table size.    
- Avoid using functions on indexed columns in queries.    


---

##  **5. Practice Tasks** <a name="practice-tasks"></a>

1. Normalize a sample dataset to 3NF.  
2. Write a transaction for transferring funds between accounts, ensuring rollback on failure.    
3. Create an index on a frequently queried column and analyze its performance.    
4. Partition a large dataset and demonstrate its query benefits.        

---

Mastering these techniques ensures a robust, efficient, and optimized database design. Practice these concepts to take your SQL skills to the next level! 🚀


- <a href="{{ site.baseurl }}/day17/" style="font-size: 16px;">  Day 17: Advanced SQL Queries & Data Manipulation </a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day19/" style="font-size: 16px;"> Day 19: SQL for analytics, pivoting, window functions, and automation with stored procedures. (Upcoming) </a>
