---
layout: page
title: Day 1 - Introduction to Python
permalink: /day1/
---

# Table of Contents
- [Day 1: Introduction to Python - Let’s Begin Your Coding Journey!](#Introduction-to-Python)
- [Setting Up Python with Google Colab](#google-colab)
- [Your First Python Code!](#first-code)
- [Variables and Data Types in Python](#Variables-and-data-types)
- [Basic Calculations in Python](#basic-calculations)

---

## Day 1: Introduction to Python - Let’s Begin Your Coding Journey!<a name="Introduction-to-Python"></a>
Welcome to the exciting world of Python programming! Whether you're learning to build AI models, create websites, or just understand the basics of programming, Python is the perfect language to start with. In this guide, we'll introduce you to Python, walk you through how to set up your environment, and help you write your very first Python code.

### What is Python?
Python is a high-level, easy-to-learn programming language that’s widely used across many fields, including data science, web development, automation, and AI. The reason Python is so popular, especially for beginners, is because of its simple syntax—meaning it's easy to read and write, making programming feel more intuitive.

### Why Learn Python?
Here are a few reasons why Python is a great choice for beginners:
1. **Simplicity**: Python's syntax closely resembles the English language, making it easy to read and write code.
2. **Wide Usage**: Python is used in many industries like data science, AI, web development, and more.
3. **Supportive Community**: Python has a large community, meaning you’ll always find support, tutorials, and resources online.
4. **Powerful Libraries**: Python offers a rich set of libraries (like NumPy, Pandas, TensorFlow, and more) that make solving complex problems easier.

## Setting Up Python with Google Colab <a name="google-colab"></a>
You don’t need to install anything on your computer to get started with Python! Google Colab is a free, cloud-based tool that lets you run Python code directly in your web browser, which makes it perfect for beginners.

### How to Use Google Colab
1. **Open Google Colab:**
- Go to [Google Colab](https://colab.research.google.com/).
- Sign in using your Google account (if you're not already signed in).

2. **Create a New Notebook:**
- Once logged in, **click File > New Notebook in Drive.**
- A new tab will open with an empty notebook where you can start writing Python code.

## Your First Python Code!  <a name="first-code"></a>
Now, let’s write your first Python program. In the Google Colab notebook, type the following code:

```python 
print("Hello, World!")
```

Then, press Shift + Enter (or click the Run button). You should see:

```
"Hello, World!"
```

### What Did We Do?
- **print():** This is a built-in Python function that displays whatever is inside the parentheses on the screen. Here, we printed the string "Hello, World!".
- **String:** In Python, text is enclosed in quotation marks, like "Hello, World!". This is called a **string**.
You just wrote and ran your very first Python program! 🎉


## Variables and Data Types in Python <a name="Variables-and-data-types"></a>
Now that you've seen how easy it is to write your first program, let's dive into variables and data types. In Python, a variable is like a container where you can store values. For example, you might want to store a number, a name, or a true/false value.

**Creating Variables**
In Python, creating a variable is simple. You choose a name for your variable and assign it a value using the equals sign (=). Here’s how you do it:

```python
x = 5
name = "Alice"
```

In this example:
- **x** is a variable that stores the number **5.**
- **name** is a variable that stores the string **"Alice".**

### Common Data Types
Python supports several types of data:
1. **Integer (int):** Whole numbers, such as 5, -2, or 100.
2. **Floating-point number (float):** Numbers with decimals, like 3.14, 0.99, or -5.0.
3. **String (str):** Text, enclosed in quotation marks, such as "Hello" or "Python".
4. **Boolean (bool):** Represents either True or False.

Python automatically detects the type of data based on the value you assign. For example:

```python
age = 25           # Integer
height = 5.9       # Float
name = "Alice"     # String
is_student = True  # Boolean
```

## Basic Calculations in Python <a name="basic-calculations"></a>
Python is not just for printing text—it’s also a powerful tool for performing calculations! Let’s look at how to do some basic math with Python:

**Mathematical Operators**
Here are the basic operators you can use for calculations:

1. **Addition (+):** Adds two numbers.  
Example: 5 + 3 results in 8.
2. **Subtraction (-):** Subtracts one number from another.  
Example: 10 - 4 results in 6.
3. **Multiplication (*):** Multiplies two numbers.  
Example: 3 * 4 results in 12.
4. **Division (/):** Divides one number by another. This always gives a float.  
Example: 8 / 2 results in 4.0.
5. **Floor Division (//):** Divides and returns the integer part of the result (no decimals).  
Example: 7 // 2 results in 3.
6. **Modulo (%):** Gives the remainder after division.  
Example: 7 % 3 results in 1.
7. **Exponentiation** (**): Raises a number to the power of another.  
Example: 2 ** 3 results in 8.

Let’s try a few calculations in Google Colab:

```python
x = 10
y = 5

#Addition
sum_result = x + y
print("Sum:", sum_result)

#Subtraction
difference = x - y
print("Difference:", difference)

#Multiplication
product = x * y
print("Product:", product)

#Division
quotient = x / y
print("Quotient:", quotient)

#Floor Division
floor_division = x // y
print("Floor Division:", floor_division)

#Modulo
remainder = x % y
print("Remainder:", remainder)

#Exponentiation
power = x ** y
print("Power:", power)
```

You’ll get the following output:
```
Sum: 15
Difference: 5
Product: 50
Quotient: 2.0
Floor Division: 2
Remainder: 0
Power: 100000
```

## Using Variables in Calculations
You can also use variables in calculations. For example, let’s calculate the area of a rectangle:

```python
length = 5
width = 3

area = length * width
print("Area of the rectangle:", area)
```

Here, we used two variables (length and width) to store the dimensions of the rectangle and then multiplied them to find the area.


## Wrap-Up
Today, we’ve covered some of the core concepts of Python programming:
- **Variables:** How to store data in variables and assign them values.
- **Data Types:** Different types of data such as integers, floats, strings, and booleans.
- **Basic Calculations:** How to use Python to perform mathematical operations like addition, subtraction, multiplication, and more.
- 
As you move forward, these basics will serve as the foundation for more complex topics. Take some time to experiment with these concepts by changing the values of the variables and performing your own calculations.

In the next guide, we’ll dive into control flow—learning how to make decisions in your program with if statements, loops, and more!

**Keep coding, and happy learning!**
