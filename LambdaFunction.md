---
layout: default
title: "Lambda Function"
permalink: /LambdaFunction/
---

# Table of Contents
- [Lambda Function](#Lambda-Function)
- [Syntax](#syntax)
- [Use Cases](#Use-Cases)
- <a href="{{ site.baseurl }}/day4/" style="font-size: 16px;"> Day 4: Functions – Modularize Your Code with Python</a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
## Lambda Function  <a name="Lambda-Function"></a>
A lambda function in Python is a small, anonymous function that is defined using the **"lambda"** Keyword. Unlike a regular function that is defined with a *'def'* keyword a Lambda function *can have only **one expression*** and doen't required a name.

### Characteristics of Lambda Function:-

**1. Anomymous:** Lambda functions donot have a name, hence the term "anonymous".

**2. Single Expression:** They are restricted to a single expression. This expression is evaluated and returned when the function is called.

**3. Concise:** Lambda functions are typically used for short, simple operations that are passed as arguments to higher-order functions like **map(), filter(), sorted().**

### **Syntax:**  <a name="syntax"></a>
```python
lambda <arguments>:<expression>
```

**arguments:** A comma-seperated list of arguments  

**expression:** A single expression that is evaluated and returned.  

**Example:**
```python
add = lambda x, y: x + y  
print(add(3, 5))  # Output: 8
```

### Use Cases: <a name="Use-Cases"></a>
**1. In Higher-Order Functions:**  
Lambda functions are often used in combination with functions like map(), filter(), and sorted() that take other functions as arguments.  

**map():** applies a function to every item of an iterable (like a list) and returns an iterable of the results.  
**Example:**
```python
nums = [1, 2, 3, 4]  
squares = map(lambda x: x**2, nums)  
print(list(squares))  # Output: [1, 4, 9, 16]
```

**filter():** filters elements of an iterable based on a function that returns a boolean value.  
**Example:**
```python
nums = [1, 2, 3, 4, 5, 6]  
evens = filter(lambda x: x % 2 == 0, nums)  
print(list(evens))  # Output: [2, 4, 6]
```

**sorted():** sorts elements of a sequence based on a key function.  
**Example:**
```python
tuples = [(1, 'one'), (2, 'two'), (3, 'three')]  
sorted_tup = sorted(tuples, key=lambda x: x[1])  
print(sorted_tup)  # Output: [(1, 'one'), (3, 'three'), (2, 'two')]
```

**2. As a Quick Throwaway Function:**  
Lambda functions are useful when you need a small function for a short period of time and don't want to formally define it with a *def* statement.


- <a href="{{ site.baseurl }}/day4/" style="font-size: 16px;"> Day 4: Functions – Modularize Your Code with Python</a>  
- <a href="{{ site.baseurl }}/">Back to Home</a>
