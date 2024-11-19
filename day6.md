---
layout: default
title: Day 6: File Handling in Python – Manage and Process Data Efficiently
permalink: /day6/
---

# Day 6: File Handling in Python – Manage and Process Data Efficiently

# Table of Contents
- [What is File Handling?](#what-is-file-handling)
- [Types of Files in Python](#types-of-files-in-python)
- [Opening and Closing Files](#opening-and-closing-files)
- [File Modes](#file-modes)
- [Reading from a File](#reading-from-a-file)
- [Writing to a File](#writing-to-a-file)
- [Appending to a File](#appending-to-a-file)
- [Working with Binary Files](#working-with-binary-files)
- [Best Practices for File Handling](#best-practices-for-file-handling)
- [Quick Practice](#quick-practice)
- [Wrap-Up](#wrap-up)
- <a href="{{ site.baseurl }}/day5/" style="font-size: 16px;">Day 5: Exploring Data Structures in Python</a>  
- <a href="{{ site.baseurl }}/">Back to Home</a>  
- <a href="{{ site.baseurl }}/day7/" style="font-size: 16px;">Day 7: Error and Exception Handling in Python – Build Resilient Code</a>    

---

### What is File Handling? <a name="what-is-file-handling"></a>
File handling in Python allows you to manage and process data stored in files, whether they are text or binary. This is essential for tasks like reading data from files, storing results, or logging application activities.  

---

### Types of Files in Python <a name="types-of-files-in-python"></a>  
Python supports working with two main types of files:  

1. **Text Files**: Contains plain text, readable by humans. Example: `.txt`, `.csv`.  
2. **Binary Files**: Contains data in binary format, readable by machines. Example: `.jpg`, `.exe`.  

---

### Opening and Closing Files <a name="opening-and-closing-files"></a>  
To work with files in Python, you first need to open them. After the operation, you should always close the file to free resources.

**Syntax:**
```python
file = open("filename", "mode")  # Open the file
file.close()  # Close the file
```

**Example:**
```python
file = open("example.txt", "r")
# Perform operations
file.close()
```

### File Modes <a name="file-modes"></a>  
When opening a file, you specify the mode:  

| Mode  | Description                      |
|-------|----------------------------------|
| `'r'` | Read-only mode (default).        |
| `'w'` | Write mode (overwrites file).    |
| `'a'` | Append mode (adds to file).      |
| `'rb'`| Read-only binary mode.           |
| `'wb'`| Write binary mode.               |
| `'r+'`| Read and write mode.             |


### Reading from a File <a name="reading-from-a-file"></a>  
You can read data using methods like read(), readline(), or readlines().  

**Example:**
```python
file = open("example.txt", "r")

# Read entire content
content = file.read()
print(content)

# Read line by line
file.seek(0)  # Reset pointer
for line in file:
    print(line)

file.close()
```

### Writing to a File <a name="writing-to-a-file"></a>  
Use the write() method to write data to a file. If the file doesn't exist, it will be created.  

**Example:**
```python
file = open("example.txt", "w")
file.write("Hello, AI Noob Nook!\n")
file.close()
```

### Appending to a File <a name="appending-to-a-file"></a>
Use the a mode to add new content without overwriting existing data.

**Example:**
```python
file = open("example.txt", "a")
file.write("Let's learn Python file handling.\n")
file.close()
```

### Working with Binary Files <a name="working-with-binary-files"></a>
Binary files store data in binary format. Use 'rb' or 'wb' for reading or writing.

**Example:**
```python
# Writing binary data
with open("binaryfile.bin", "wb") as file:
    file.write(b'\x48\x65\x6c\x6c\x6f')

# Reading binary data
with open("binaryfile.bin", "rb") as file:
    data = file.read()
    print(data)
```

### Best Practices for File Handling <a name="best-practices-for-file-handling"></a>
**1. Use with Statement:** Automatically closes files after operation.  
```python
with open("example.txt", "r") as file:
    content = file.read()
```

**2. Handle Exceptions:**  Use try-except blocks to handle errors 
```python
try:
    with open("example.txt", "r") as file:
        content = file.read()
except FileNotFoundError:
    print("File not found!")
```

### Quick Practice <a name="quick-practice"></a>
1. Write a program to read a file and print the number of lines, words, and characters.
2. Create a file and write a list of numbers to it, then read and calculate their sum.
3. Write a program to copy a binary file.

### Wrap-Up <a name="wrap-up"></a>  
Today, we learned about:

- Opening and closing files.  
- Different modes for file operations.  
- Reading, writing, and appending files.  
- Handling binary data.  
- Best practices for file handling.  
- Mastering file handling is crucial for working with real-world data. Practice these examples and explore how Python simplifies file management.

<a href="{{ site.baseurl }}/day5/" style="font-size: 16px;">Day 5: Exploring Data Structures in Python</a>  
<a href="{{ site.baseurl }}/">Back to Home</a>    
<a href="{{ site.baseurl }}/day7/" style="font-size: 16px;">Day 7: Error and Exception Handling in Python – Build Resilient Code</a>  
