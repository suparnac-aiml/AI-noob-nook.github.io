---
layout: default
title: "Day 3: Control Flow – Making Decisions in Python"
permalink: /day3/
---

# Table of Contents
- [Day 3: Control Flow – Making Decisions in Python](#Control-Flow)
- [Why Control Flow?](#Why-Control-Flow)
- [If-Else Statements](#If-Else)
- [Elif (Else If)](#Else-If)
- [Logical Operators](#Logical-Operators)
- [Loops – Repeating Actions](#Loops)
- [For Loop](#For-Loop)
- [While Loop](#While-Loop)
- [Break and Continue](#Break-and-Continue)
- [Quick Practice](#practice)
- [Wrap-up](#Wrap-Up)
- <a href="{{ site.baseurl }}/day2/" style="font-size: 16px;"> Day 2: Types and Variables</a>
- <a href="{{ site.baseurl }}/day4/" style="font-size: 16px;"> Day 4: Functions – Modularize Your Code with Python</a>
- <a href="{{ site.baseurl }}/" style="font-size: 16px;">Back to Home</a>

---

### Day 3: Control Flow – Making Decisions in Python <a name="Control-Flow"></a>
Welcome to Day 3!  
Now that we know about variables and data types, let’s learn how to make programs smarter by controlling their flow. With control flow, we can make decisions, repeat actions, and manage the behavior of our code.

### Why Control Flow? <a name="Why-Control-Flow"></a>
Control flow allows your program to respond to different situations. For example:

- If it’s raining, take an umbrella.
- If a number is even, print it; otherwise, skip it.

In Python, we achieve this using **if-else statements** and **loops.**

### 1. If-Else Statements <a name="If-Else"></a>  
An **if-else statement** allows your program to execute code based on a condition.

**Syntax:**  
``` python
if condition:
    # Code to execute if condition is True
else:
    # Code to execute if condition is False
```

**Example:**  
```python
temperature = 30

if temperature > 25:
    print("It's hot outside!")
else:
    print("It's cool today.")
```

💡 Conditions are expressions that evaluate to True or False. Common operators include:

- **>: Greater than**
- **<: Less than**
- **==: Equals**
- **!=: Not equals**

### 2. Elif (Else If)  <a name="Else-If"></a>  
When you have multiple conditions, use **elif.**

**Example:**  
```python
marks = 85

if marks >= 90:
    print("Grade: A")
elif marks >= 75:
    print("Grade: B")
else:
    print("Grade: C")
```

### 3. Logical Operators  <a name="Logical-Operators"></a>  
Combine multiple conditions using:  

- **and: Both conditions must be True.**
- **or: At least one condition must be True.**
- **not: Reverses the condition.**

**Example:**  
```python
age = 20
has_id = True

if age >= 18 and has_id:
    print("You can vote!")
else:
    print("You cannot vote.")
```

### 4. Loops – Repeating Actions <a name="Loops"></a>  
Loops allow you to repeat code multiple times. Python has two main loops:

### A. For Loop <a name="For-Loop"></a>  
Used to iterate over a sequence (like a list or range).

**Example:**  
```python
for number in range(1, 6):
    print(number)
```

Here, range(1, 6) generates numbers from 1 to 5.

💡 You can also loop through strings:
```python
for char in "Python":
    print(char)
```

### B. While Loop <a name="While-Loop"></a>  
Repeats as long as a condition is True.

**Example:**
```python
count = 0

while count < 5:
    print("Count:", count)
    count += 1
```

### 5. Break and Continue  <a name="Break-and-Continue"></a>  
- **break:** Stops the loop entirely.
- **continue:** Skips the rest of the loop and moves to the next iteration.  
**Example – Break:**  
```python
for number in range(1, 10):
    if number == 5:
        break
    print(number)
```

**Example – Continue:**  
```python
for number in range(1, 10):
    if number % 2 == 0:
        continue
    print(number)  # Prints only odd numbers
```

**Quick Practice**  <a name="practice"></a>   
1. Write a program to check if a number is positive, negative, or zero.  
2. Use a loop to print all even numbers between 1 and 20.  
3. Write a guessing game: the user has to guess a number, and the program gives hints until they guess it correctly.  

**Wrap-Up**  <a name="Wrap-Up"></a>  
Today, you learned:  

- How to make decisions in Python using if-else and elif.  
- How to repeat actions using for and while loops.  
- How to control loops with break and continue.  
- Practice these concepts and try to solve real-world problems, like creating a calculator or a number guessing game. Tomorrow, we’ll dive into functions, which will make your programs even more modular and reusable!

**Keep coding, and happy learning! 🚀**

<a href="{{ site.baseurl }}/day2/" style="font-size: 16px;"> Day 2: Types and Variables</a>     
<a href="{{ site.baseurl }}/day4/" style="font-size: 16px;"> Day 4: Functions – Modularize Your Code with Python</a>   
<a href="{{ site.baseurl }}/">Back to Home</a>   
