---
layout: default
title: "Day 12: NumPy Basics – Powerful Numerical Computing"
permalink: /day12/
---

# Day 12: NumPy Basics – Powerful Numerical Computing 🚀 <a name="introduction-to-numpy"></a>

NumPy (Numerical Python) is a fundamental library in Python for numerical computations. It's widely used for handling arrays, performing mathematical operations, and serving as a backbone for libraries like Pandas, TensorFlow, and scikit-learn.


## Table of Contents

1. [Introduction to NumPy](#introduction-to-numpy)
2. [Why NumPy?](#why-numpy)
3. [Key Features](#key-features)
4. [Importing NumPy](#importing-numpy)
5. [Creating Arrays](#creating-arrays)
6. [Array Properties](#array-properties)
7. [Basic Operations](#basic-operations)
8. [Indexing and Slicing](#indexing-and-slicing)
9. [Broadcasting](#broadcasting)
10. [Real-world Example: Temperature Conversion](#real-world-example-temperature-conversion)
11. [Advantages of NumPy over Python Lists](#advantages-of-numpy-over-python-lists)
12. [Wrap-Up](#Wrap-Up)
- <a href="{{ site.baseurl }}/day11/" style="font-size: 16px;">  Day 11: Python for Data Science – Let’s Analyze and Visualize Data! </a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day13/" style="font-size: 16px;">  Day 13: Pandas – Data Manipulation and Analysis (Upcoming) </a>


---


## Why NumPy? <a name="why-numpy"></a>

- **Efficient:** NumPy arrays (ndarray) are faster and use less memory than traditional Python lists.
- **Versatile:** It offers a variety of mathematical functions, random number generation, linear algebra tools, and more.
- **Interoperable:** Integrates seamlessly with other libraries and systems.

---

## Key Features <a name="key-features"></a>

- Multi-dimensional arrays (ndarray).
- Broadcasting for operations on arrays with different shapes.
- Mathematical and statistical functions.
- Efficient memory storage and manipulation.
- Tools for linear algebra, Fourier transforms, and random number generation.

---

## Importing NumPy <a name="importing-numpy"></a>

To get started, import the library:

```python
import numpy as np
```

---

## Creating Arrays   <a name="creating-arrays"></a>

**1. From a List**

```python
arr = np.array([1, 2, 3, 4])
print(arr)
```

**2. Using Built-in Functions**

```python
zeros = np.zeros((2, 3))  # Creates a 2x3 array of zeros
ones = np.ones((3, 3))    # Creates a 3x3 array of ones
range_array = np.arange(1, 10, 2)  # Array from 1 to 9 with step 2
linspace_array = np.linspace(0, 1, 5)  # 5 equally spaced values from 0 to 1

```


**3. Random Arrays**

```python
rand_array = np.random.rand(3, 3)  # 3x3 array with random values between 0 and 1
rand_ints = np.random.randint(1, 10, size=(3, 3))  # 3x3 array with random integers from 1 to 9

```

---

## Array Properties <a name="array-properties"></a>

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])
print(arr.shape)  # (2, 3) - rows and columns
print(arr.size)   # 6 - total elements
print(arr.dtype)  # Data type of elements

```

---

## Basic Operations  <a name="basic-operations"></a>

**1. Element-wise Operations**

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])
print(a + b)  # [5, 7, 9]
print(a * b)  # [4, 10, 18]

```


**2. Matrix Multiplication**

```python
a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])
print(np.dot(a, b))  # Matrix multiplication

```


**3. Statistical Operations**

```python
data = np.array([1, 2, 3, 4, 5])
print(data.mean())  # Average
print(data.sum())   # Total sum
print(data.std())   # Standard deviation

```

---

## Indexing and Slicing <a name="indexing-and-slicing"></a>

**1. Basic Indexing**

```python
arr = np.array([10, 20, 30, 40])
print(arr[2])  # 30

```


**2. Slicing**

```python
arr = np.array([10, 20, 30, 40, 50])
print(arr[1:4])  # [20, 30, 40]

```


**3. Boolean Indexing**

```python
arr = np.array([10, 20, 30, 40])
print(arr[arr > 20])  # [30, 40]

```

---

## Broadcasting   <a name="Broadcasting"></a>

Broadcasting allows operations on arrays of different shapes:

```python
a = np.array([[1, 2], [3, 4]])
b = np.array([10, 20])
print(a + b)
# Output:
# [[11, 22],
#  [13, 24]]

```

---

## Real-world Example: Temperature Conversion  <a name="real-world-example-temperature-conversion"></a>

Convert a list of temperatures in Celsius to Fahrenheit: 

```python
celsius = np.array([0, 20, 30, 40])
fahrenheit = (celsius * 9/5) + 32
print(fahrenheit)  # [32., 68., 86., 104.]

```

---

## Advantages of NumPy over Python Lists <a name="advantages-of-numpy-over-python-lists"></a>

| Feature          | NumPy                           | Python List                     |
|------------------|---------------------------------|---------------------------------|
| Speed            | Faster                          | Slower                          |
| Memory Usage     | Optimized                       | Higher                          |
| Functionality    | Rich mathematical operations   | Limited                         |
| Multi-dimensional| Supports n-dimensional arrays  | No direct support               |


---

## Wrap-Up <a name=""></a>  

NumPy is a powerhouse for numerical computing in Python, offering speed, efficiency, and extensive functionalities. Whether you're a beginner or an expert, mastering NumPy is crucial for data analysis, machine learning, and scientific computing.

Stay tuned for Day 13 as we dive deeper into Pandas – the ultimate data manipulation library! 🚀

- <a href="{{ site.baseurl }}/day11/" style="font-size: 16px;">  Day 11: Python for Data Science – Let’s Analyze and Visualize Data! </a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day13/" style="font-size: 16px;">  Day 13: Pandas – Data Manipulation and Analysis (Upcoming) </a>

