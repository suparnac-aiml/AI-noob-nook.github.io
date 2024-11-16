---
layout: default
title: "Day 2 - Types and Variables"
permalink: /day2/
---

# Table of Contents
- [Day 2: Types and Variables - Master the Building Blocks of Python!](#Types-and-Variables)
- [What Are Variables?](#Variables)
- [Common Data Types](#Common-Data-Types)
- [Playing with Variables](#Playing-with-Variables)
- [Quick Practice](#practice)
- [Wrap-up](#Wrap-Up)
- <a href="{{ site.baseurl }}/day3/" style="font-size: 16px;">Day 3: Control Flow – Making Decisions in Python</a>  
- <a href="{{ site.baseurl }}/day1/" style="font-size: 16px;">Day 1: Introduction to Python</a>
- <a href="{{ site.baseurl }}/">Back to Home</a>

---
## Day 2: Types and Variables - Master the Building Blocks of Python!<a name="Types-and-Variables"></a>
Welcome back, future Python pro! Yesterday, we introduced Python and wrote our first program. Today, we’re diving deeper into data types and variables—the fundamental building blocks of every program.

### What Are Variables? <a name="Variables"></a>
A variable is like a container where you store data. Think of it as a labeled box where you can put a value and use it later.

Here’s how to create variables in Python:
```Python
name = "AI Noob Nook"  # A string
age = 25              # An integer
height = 5.7          # A float
is_coder = True       # A boolean
```

💡 Python automatically detects the type of data based on the value you assign to it!

### Common Data Types <a name="Common-Data-Types"></a>
Python supports several data types. Let’s explore the most common ones:

1. **Strings (str)**: Text data enclosed in quotes.

```python
message = "Hello, World!"
```

- Strings can contain letters, numbers, and symbols.
- You can combine strings using the + operator.

```python
greeting = "Hello" + " " + "Python!"
print(greeting)  # Output: Hello Python!
```

2. **Integers (int):** Whole numbers (positive or negative).
```python
count = 42
```
- Useful for counting, indexing, or calculations.

3. **Floats (float):** Numbers with decimals.
```pthon
price = 19.99
```

4. **Booleans (bool):** True or False values.
```python
is_python_easy = True
```

Often used in decision-making (more on this in Day 3!).

### Playing with Variables <a name="Playing-with-Variables"></a>
Variables can interact with each other:

```python
x = 10
y = 5
z = x + y  # Add two variables
print(z)   # Output: 15
```

You can even change the value of a variable anytime:

```python
x = 20
print(x)  # Output: 20
```

### Checking Data Types
Want to know the type of a variable? Use the type() function:
```python
value = 42
print(type(value))  # Output: <class 'int'>
```

### Input from Users
Make your program interactive by asking for user input:
```python
name = input("What's your name? ")
print("Hello, " + name + "!")
```

💡 By default, input is stored as a string. You can convert it using int() or float() if needed:

```python
age = int(input("Enter your age: "))
print("You are", age, "years old.")
```

### Quick Practice <a name="practice"></a>
Try these mini exercises to test your knowledge:

1. Create variables for your name, age, and favorite number, then print them.
2. Ask the user for two numbers and print their sum.
3. Check the data type of each variable you create.

### Wrap-Up <a name="Wrap-Up"></a>
Today, you learned:

- How to create variables and assign values.
- The key data types in Python: strings, integers, floats, and booleans.
- How to perform basic operations with variables.
- How to interact with users using input.
- Take a moment to play with these concepts. Experiment, make mistakes, and learn! Tomorrow, we’ll unlock the power of control flow and see how programs can make decisions.

**Happy coding! 🚀**

<a href="{{ site.baseurl }}/day1/" style="font-size: 16px;">Day 1: Introduction to Python</a>   
<a href="{{ site.baseurl }}/day3/" style="font-size: 16px;">Day 3: Control Flow – Making Decisions in Python</a>     
<a href="{{ site.baseurl }}/">Back to Home</a> 
