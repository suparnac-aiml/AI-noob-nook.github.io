---
layout: default
title: "Day 7: Error and Exception Handling in Python – Build Resilient Code"
permalink: /day7/
---

# Day 7: Error and Exception Handling in Python – Build Resilient Code
Welcome to Day 7! Today, we'll dive into error and exception handling, an essential aspect of programming that ensures your code doesn't crash unexpectedly. Let's explore how Python helps manage errors gracefully.

# Table of Contents
- [What are Errors and Exceptions?](#What-are-Errors-and-Exceptions)
- [Common Errors in Python](#Common-Errors-in-Python)
- [What is Exception Handling?](#What-is-Exception-Handling)
- [The try-except Block](#The-try-except-Block)
- [Catching Specific Exceptions](#Catching-Specific-Exceptions)
- [Using else and finally](#Using-else-and-finally)
- [Raising Exceptions](#Raising-Exceptions)
- [Custom Exceptions](#Custom-Exceptions)
- [Quick Practice](#Practice)
- [Wrap-Up](#Wrap-Up)
- <a href="{{ site.baseurl }}/day6/" style="font-size: 16px;"> Day 6: File Handling in Python – Manage and Process Data Efficiently </a>    
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day8/" style="font-size: 16px;"> Day 8: Object-Oriented Programming (OOP) in Python – Organizing Code for Better Reusability and Structure (Upcoming) </a>

### What are Errors and Exceptions?  <a name="What-are-Errors-and-Exceptions"></a>  
**Errors:** Issues in code that prevent execution (e.g., syntax errors).  
**Exceptions:** Errors that occur during execution but can be handled (e.g., dividing by zero).  

### Common Errors in Python <a name="Common Errors in Python"></a>
| Error Type          | Description                           | Example                       |
|---------------------|---------------------------------------|-------------------------------|
| `SyntaxError`       | Incorrect Python syntax               | `print("Hello` (missing `)`)` |
| `TypeError`         | Operation on incompatible types       | `5 + "string"`                |
| `ValueError`        | Function gets inappropriate input     | `int("hello")`                |
| `IndexError`        | Accessing out-of-range list index     | `lst[10]` (list of size 5)    |
| `KeyError`          | Key not found in dictionary           | `dict['missing_key']`         |
| `ZeroDivisionError` | Division by zero                      | `10 / 0`                      |


### What is Exception Handling? <a name="What-is-Exception-Handling"></a>   
Exception handling in Python uses the try-except block to catch and handle exceptions gracefully, avoiding program crashes.  

### The try-except Block  <a name="The-try-except-Block"></a>  

**Syntax:**
```python
try:  
    # Code that might raise an exception  
except ExceptionType:  
    # Code to execute if an exception occurs  
```

**Example:**  

```python
try:  
    num = int(input("Enter a number: "))  
    print(10 / num)  
except ZeroDivisionError:  
    print("Cannot divide by zero!")  
except ValueError:  
    print("Invalid input. Please enter a number.")  
```

### Catching Specific Exceptions <a name="Catching-Specific-Exceptions"></a>  
Handling multiple exceptions separately helps identify the issue precisely.   

**Example:**  

```python
try:  
    lst = [1, 2, 3]  
    print(lst[5])  
except IndexError:  
    print("Index out of range!")  
except Exception as e:  
    print(f"An error occurred: {e}")  
```

### Using else and finally <a name="Using-else-and-finally"></a>  

**else Block:** Executes if no exception is raised.  
**finally Block:** Executes no matter what (cleanup code).  

**Example:**

```python
try:  
    file = open("data.txt", "r")  
    print(file.read())  
except FileNotFoundError:  
    print("File not found!")  
else:  
    print("File read successfully.")  
finally:  
    print("Closing the file.")  
    file.close()  
````

### Raising Exceptions <a name="Raising-Exceptions"></a>  
You can raise exceptions intentionally using the raise keyword.  

**Example:**

```python
def check_age(age):  
    if age < 18:  
        raise ValueError("Age must be at least 18.")  
    return "Access granted."  

try:  
    print(check_age(15))  
except ValueError as e:  
    print(e)  
```

### Custom Exceptions <a name="Custom-Exceptions"></a>
Define custom exceptions by creating a class that inherits from Exception.

**Example:**
```python
class NegativeNumberError(Exception):  
    pass  

def square_root(num):  
    if num < 0:  
        raise NegativeNumberError("Cannot calculate square root of a negative number.")  
    return num ** 0.5  

try:  
    print(square_root(-4))  
except NegativeNumberError as e:  
    print(e)  
```

### Quick Practice <a name="Practice"></a>  

1. Write a program that asks for two numbers and divides them, handling ZeroDivisionError and ValueError.  
2. Create a function that raises an exception if the input string is empty.  
3. Write a custom exception class for invalid email addresses and implement it  

### Wrap-Up <a name="Wrap-Up"></a>

Today, you learned:  
- How to handle common Python errors and exceptions.  
- The importance of the try-except block for resilient code.  
- Advanced exception handling with else, finally, raising exceptions, and custom exceptions.  
- Practice exception handling to make your Python programs robust and user-friendly. Tomorrow, we’ll explore object-oriented programming (OOP) to bring structure and scalability to your code.  

**Happy coding! 🚀**  

- <a href="{{ site.baseurl }}/day6/" style="font-size: 16px;"> Day 6: File Handling in Python – Manage and Process Data Efficiently </a>    
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day8/" style="font-size: 16px;"> Day 8: Object-Oriented Programming (OOP) in Python – Organizing Code for Better Reusability and Structure (Upcoming) </a>
