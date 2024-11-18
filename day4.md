---
layout: default
title: "Day 4: Functions – Modularize Your Code with Python"
permalink: /day4/
---

# Table of Contents
- [Day 4: Functions – Modularize Your Code with Python](#day4)
- [What is a Function?](#What-is-a-Function)
- [Defining a Function](#Defining-a-Function)
- [Function Arguments](#Function-Arguments)
- [Return Statement](#Return-Statement)
- [Scope of Variables](#Scope-of-Variables)
- [Lambda Functions](#Lambda-Functions)
- <a href="{{ site.baseurl }}/LambdaFunction/" style="font-size: 16px;"> Learn more about Lambda Function</a>
- [Recursion](#Recursion)
- [Quick Practice](#practice)
- [Wrap-Up](#Wrap-Up)
- <a href="{{ site.baseurl }}/day3/" style="font-size: 16px;"> Day 3: Control Flow – Making Decisions in Python</a>   
- <a href="{{ site.baseurl }}/day5/" style="font-size: 16px;">Day 5: Exploring Data Structures in Python </a> 
- <a href="{{ site.baseurl }}/">Back to Home</a>

## Day 4: Functions – Modularize Your Code with Python <a name="day4"></a>  
Welcome to Day 4!  
Today we are going to explore Functions in Python. Functions help you organize your code by breaking it into smaller, reusable chunks. Let’s learn how to define, use, and optimize functions.

### What is a Function? <a name="What-is-a-Function"></a>  
A function is a block of reusable code that performs a specific task. Functions help reduce redundancy and make your code more organized and readable.

**Example:**
```python
def greet(name):
    print("Hello, " + name + "!")
```
You can call the function as:  
```python
great("Alice")
```

### Defining a Function <a name="Defining-a-Function"></a>  
To define a function, we use the def keyword, followed by the function name, parentheses, and a colon. The function body contains the code that will execute when the function is called.

**Syntax:**
```python
def function_name(parameters):
    # Code to execute
```

**Example:**  
```python
def add_numbers(a, b):
    return a + b
```

### Function Arguments <a name="Function-Arguments"></a>  
Functions can accept parameters (or arguments) that allow you to pass data to them.

### Types of Arguments:

### 1. Positional Arguments:  
These are arguments passed based on their position.

```python
def multiply(x, y):
    return x * y

result = multiply(2, 3)  # x = 2, y = 3
```

### 2. Keyword Arguments:  
These are arguments passed by specifying the name of the parameter.   

```python
def introduce(name, age):
    print(f"My name is {name} and I am {age} years old.")
introduce(name="John", age=25)
```

### 3. Default Arguments:  
You can assign default values to parameters.

```python
def greet(name="Guest"):
    print(f"Hello, {name}!")
greet()  # Uses default value
greet("Alice")  # Overrides default value
```

### Return Statement <a name="Return-Statement"></a>  
A function can return a value using the return statement. This allows you to pass data back to the caller.

**Example:**  
```python
def square(number):
    return number ** 2

result = square(4)  # result will be 16  
```

### Scope of Variables <a name="Scope-of-Variables"></a>  
**1. Local Variables:** Variables defined inside a function are local to that function.   
**2. Global Variables:** Variables defined outside of any function are global and can be accessed throughout the program.  

**Example:**
```python
x = 10  # Global variable

def example_function():
    x = 5  # Local variable
    print("Local x:", x)  # Output: 5
    print("Global x:", globals()['x'])  # Output: 10

example_function()
```

### Lambda Functions <a name="Lambda-Functions"></a>  
A lambda function is a small anonymous function that is defined with the lambda keyword. It can take any number of arguments but can only have one expression.

***Syntax:**
```python
lambda arguments: expression
```

**Example:**
```python
square = lambda x: x ** 2
result = square(5)  # Output: 25
```

### <a href="{{ site.baseurl }}/LambdaFunction/" style="font-size: 16px;">Learn more about Lambda Function here</a>

### Recursion <a name="Recursion"></a>  
Recursion occurs when a function calls itself. It is useful for problems that can be broken down into smaller sub-problems.

**Example (Factorial):**
```python
def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n - 1)

print(factorial(5))  # Output: 120
```

### Quick Practice <a name="practice"></a>
1. Write a function to check whether a number is prime.  
2. Create a function to calculate the Fibonacci sequence up to a given number.  
3. Write a function that accepts a string and returns the reversed string.  

### Wrap-Up <a name="Wrap-Up"></a>  
Today, we learned:

How to define and use functions in Python.  
The importance of function arguments and return values.  
The difference between local and global variables.  
The power of lambda functions and recursion.  
In the next lesson, we’ll explore Data Structures in Python, which will help you organize and manipulate data more effectively.  

**Keep coding, and stay curious! 🚀**

<a href="{{ site.baseurl }}/day3/" style="font-size: 16px;"> Day 3: Control Flow – Making Decisions in Python</a>   
- <a href="{{ site.baseurl }}/day5/" style="font-size: 16px;">Day 5: Exploring Data Structures in Python </a>     
<a href="{{ site.baseurl }}/">Back to Home</a>    
