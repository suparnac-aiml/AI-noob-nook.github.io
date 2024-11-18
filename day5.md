---
layout: default
title: "Day 5: Exploring Data Structures in Python"
permalink: /day5/
---

# Table of Contents
- [What are Data Structures?](#what-are-data-structures)
- [Lists – Ordered and Mutable](#lists)
- [Tuples – Immutable Collections](#tuples)
- [Sets – Unique and Unordered](#sets)
- [Dictionaries – Key-Value Pairs](#dictionaries)
- [Quick Comparison of Data Structures](#comparison)
- [Practice Problems](#practice)
- [Wrap-Up](#wrap-up)
- <a href="{{ site.baseurl }}/day4/" style="font-size: 16px;"> Day 4: Functions – Modularize Your Code with Python </a>   
- Day 6: File Handling in Python – Manage and Process Data Efficiently (Upcoming)  
- <a href="{{ site.baseurl }}/">Back to Home</a>


Welcome to Day 5!  
Data structures are the building blocks of efficient programming, and Python provides a rich set of built-in structures to handle various data manipulation tasks. Today, we’ll dive into Python’s key data structures: **lists, tuples, sets, and dictionaries.**    

### What are Data Structures? <a name="what-are-data-structures"></a>
Data structures are formats used to organize and store data so it can be accessed and modified efficiently.   
In Python, common built-in data structures include:

**1. List:** Ordered, mutable sequence.  
**2. Tuple:** Ordered, immutable sequence.  
**3. Set:** Unordered collection of unique items.  
**4. Dictionary:** Key-value mapping for quick lookups.  

### 1. Lists – Ordered and Mutable <a name="lists"></a>  
A list is a collection that is:  
**Ordered:** Items maintain their insertion order.  
**Mutable:** Items can be added, removed, or modified    
Defined using square brackets **[ ].**

**Syntax:**  
```python
my_list = [item1, item2, item3]
```

**Examples:**  
```python
fruits = ["apple", "banana", "cherry"]
print(fruits[0])  # Accessing the first item
fruits.append("orange")  # Adding an item
print(fruits)  # ['apple', 'banana', 'cherry', 'orange']
fruits.remove("banana")  # Removing an item
print(fruits)  # ['apple', 'cherry', 'orange']
```

**Common Methods:**

- **append(x):** Adds an item to the end of the list.  
- **insert(i, x):** Inserts an item at a specific index.  
- **remove(x):** Removes the first occurrence of an item.  
- **pop(i):** Removes and returns an item at index i.  
- **sort():** Sorts the list in ascending order.  

### 2. Tuples – Immutable Collections <a name="tuples"></a>  
A tuple is similar to a list but:  
**Immutable:** Once created, it cannot be modified.  
**Ordered:** Items maintain their order.  
Defined using parentheses **( ).**  

**Syntax:**
```python
my_tuple = (item1, item2, item3)
```

**Examples:**  
```python
coordinates = (10, 20, 30)
print(coordinates[1])  # Accessing the second item: 20
# coordinates[1] = 25  # ❌ This will raise an error because tuples are immutable.
```

**Why Use Tuples?**

- To ensure data integrity.  
- They are faster than lists for operations that don't require modification.

### 3. Sets – Unique and Unordered <a name="sets"></a>  
A set is a collection of unique, unordered items.  
**No Duplicates:** Automatically removes duplicate elements.  
**Unordered:** Items do not maintain a specific order.  
Defined using curly braces **{ }.**  

**Syntax:**
```python
my_set = {item1, item2, item3}
```

**Examples:**  
```python
numbers = {1, 2, 3, 4, 4, 5}  # Duplicate '4' will be removed
print(numbers)  # {1, 2, 3, 4, 5}

numbers.add(6)  # Adding an item
numbers.remove(3)  # Removing an item
print(numbers)  # {1, 2, 4, 5, 6}
```

**Use Cases:**

- Removing duplicates from a list.  
- Performing set operations like union, intersection, and difference.

**Set Operations:**  
```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}

print(set1.union(set2))  # {1, 2, 3, 4, 5}
print(set1.intersection(set2))  # {3}
print(set1.difference(set2))  # {1, 2}
```

### 4. Dictionaries – Key-Value Pairs <a name="dictionaries"></a>  
A dictionary stores data as key-value pairs, allowing for fast lookups.  
Defined using curly braces **{ } with key-value pairs separated by colons :**  

**Syntax:**  
```python
my_dict = {key1: value1, key2: value2}
```

**Examples:**    
```python
student = {"name": "John", "age": 21, "grade": "A"}
print(student["name"])  # Access value by key: John

student["age"] = 22  # Modify value
student["subject"] = "Math"  # Add new key-value pair
print(student)  # {'name': 'John', 'age': 22, 'grade': 'A', 'subject': 'Math'}
```

**Common Methods:**

- **keys():** Returns all keys.  
- **values():** Returns all values.  
- **items():** Returns all key-value pairs.  

**Use Cases:**  

- Storing structured data (e.g., user profiles).  
- Fast lookups using keys.

### Quick Comparison of Data Structures <a name="comparison"></a>  

| **Data Structure** | **Ordered** | **Mutable** | **Duplicates Allowed** | **How to define** | **Use Case**                         |
|--------------------|-------------|-------------|------------------------|-------------------|--------------------------------------|
| **List**           | Yes         | Yes         | Yes                    | `[ ]`             | General-purpose, dynamic collection. |
| **Tuple**          | Yes         | No          | Yes                    | `( )`             | Immutable data, safe from changes.   |
| **Set**            | No          | Yes         | No                     | `{ }`             | Unique values, set operations.       |
| **Dictionary**     | No          | Yes         | Keys: No, Values: Yes  | `{ } with :`      | Key-value storage, fast lookups.     |



### Practice Problems <a name="practice"></a>  
1. Create a list of numbers and remove all duplicates using a set.  
2. Write a program to count the frequency of each character in a string using a dictionary.  
3. Given a tuple of student names, check if a specific name is in the tuple.  
4. Perform union, intersection, and difference operations on two sets of numbers.  

### Wrap-Up <a name="wrap-up"></a>
Today, you explored the foundational data structures in Python:  

- Lists for ordered, mutable data.  
- Tuples for immutable sequences.  
- Sets for unique, unordered elements.  
- Dictionaries for key-value mappings.  
- These structures form the core of Python programming and are used extensively in real-world applications. Practice using them in your projects to build your confidence.

<a href="{{ site.baseurl }}/day4/" style="font-size: 16px;"> Day 4: Functions – Modularize Your Code with Python </a>     
Day 6: File Handling in Python – Manage and Process Data Efficiently (Upcoming)    
<a href="{{ site.baseurl }}/">Back to Home</a>  
