---
layout: default
title: "Day 11: Python for Data Science – Let’s Analyze and Visualize Data!"
permalink: /day11/
---

# Day 11: Python for Data Science – Let’s Analyze and Visualize Data!

Data science is one of the most exciting and rapidly growing fields in technology today. Python, with its powerful libraries, makes it a preferred language for data analysis and visualization. Today, we’ll dive into the basics of data science using Python, focusing on its fundamental tools and techniques.

---

## Table of Contents
- [What is Data Science?](#DS)
- [Key Python Libraries for Data Science](#PyLib)
- [Steps in Data Analysis](#DA)
- [Real-World Example: Analyzing a Dataset](#iris)
- [Check out the Data_Visualization.ipynb file](#file)
- [Practical Use Cases](#Use-Case)
- [Key Takeaways](#KT)
- <a href="{{ site.baseurl }}/day10/" style="font-size: 16px;">  Day 10: Exploring Python Libraries and Frameworks – Powering Up Your Development </a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day12/" style="font-size: 16px;">  Day 12: NumPy Basics – Powerful Numerical Computing  </a>

---

## **1. What is Data Science?**  <a name="DS"></a>
Data science involves extracting meaningful insights from data through processes like:  
- Collecting and cleaning data.  
- Analyzing data to identify patterns.  
- Visualizing data for better understanding.  
- Making data-driven decisions.  

Python provides numerous libraries to assist in each step of this process, such as **NumPy**, **Pandas**, **Matplotlib**, and **Seaborn**.

---

## **2. Key Python Libraries for Data Science**  <a name="PyLib"></a>
Here’s an overview of the core Python libraries we'll use:  

| Library        | Description                                | Use Case Example                               |
|----------------|--------------------------------------------|-----------------------------------------------|
| `NumPy`        | Enables numerical computations and array manipulation. | Handling multidimensional arrays, performing mathematical operations. |
| `Pandas`       | Provides powerful tools for data manipulation and analysis. | Handling tabular data, cleaning, and transforming datasets. |
| `Matplotlib`   | Visualization library for creating static plots. | Creating line charts, bar graphs, and scatter plots. |
| `Seaborn`      | High-level interface for statistical graphics. | Visualizing data distributions, creating heatmaps. |

---

## **3. Steps in Data Analysis** <a name=""DA></a>
Let’s break down a typical data science workflow:

### **Step 1: Importing Necessary Libraries**
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

### **Step 2: Working with Data**
**a) Loading Data**  
You can load data from CSV, Excel, or other file formats using Pandas.  
```python
# Loading a CSV file
data = pd.read_csv('data.csv')

# Display the first 5 rows
print(data.head())
```
**b) Exploring the Data**  
Understanding the dataset is crucial before analysis.  
```python
# Display the structure of the dataset
print(data.info())

# Check for missing values
print(data.isnull().sum())

# Basic statistics
print(data.describe())
```


### **Step 3: Cleaning Data**  
Data cleaning ensures the dataset is accurate and ready for analysis.  
```python
# Filling missing values
data['Column_Name'].fillna(data['Column_Name'].mean(), inplace=True)

# Removing duplicates
data.drop_duplicates(inplace=True)

# Renaming columns
data.rename(columns={'OldName': 'NewName'}, inplace=True)
```


### **Step 4: Data Manipulation**  
Use Pandas to transform and manipulate the dataset.  
```python
# Filtering rows based on a condition
filtered_data = data[data['Column_Name'] > 10]

# Adding a new column
data['New_Column'] = data['Existing_Column'] * 2

# Grouping data
grouped_data = data.groupby('Category_Column').mean()
print(grouped_data)
```

### **Step 5: Data Visualization**  
**a) Matplotlib**  
Matplotlib is used for basic plots.  
```python
# Line plot
plt.plot(data['X_Column'], data['Y_Column'])
plt.title('Line Plot Example')
plt.xlabel('X Axis')
plt.ylabel('Y Axis')
plt.show()

# Bar plot
data['Category_Column'].value_counts().plot(kind='bar')
plt.title('Bar Plot Example')
plt.show()

```

**b) Seaborn**  
Seaborn simplifies creating aesthetically pleasing visualizations.  
```python
# Histogram
sns.histplot(data['Numerical_Column'], bins=20, kde=True)
plt.title('Histogram Example')
plt.show()

# Heatmap
correlation_matrix = data.corr()
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')
plt.title('Correlation Heatmap')
plt.show()
```

---

## **4. Real-World Example: Analyzing a Dataset**  <a anme="iris"></a>
Let’s analyze IRIS dataset:  

**Iris Dataset Overview**  
The Iris dataset is a classic dataset in the field of machine learning and statistics. It was introduced by the British biologist and statistician R.A. Fisher in 1936. The dataset consists of measurements of 150 iris flowers, categorized into three different species: Setosa, Versicolor, and Virginica.  

Each sample in the dataset contains four features (attributes):

- Sepal Length – Length of the sepal in centimeters.
- Sepal Width – Width of the sepal in centimeters.
- Petal Length – Length of the petal in centimeters.
- Petal Width – Width of the petal in centimeters.

The dataset is widely used in machine learning for classification problems, as it provides a clean and simple set of data that can be used to apply classification algorithms and evaluate their performance.

**Structure of the Iris Dataset**  
- Samples: 150
- Features: 4 continuous attributes (sepal length, sepal width, petal length, petal width)
- Classes: 3 species of Iris flowers
  - Iris Setosa
  - Iris Versicolor
  - Iris Virginica
    
Each flower is labeled with its species, making it a **supervised learning problem**.

Here, we are importing the dataset directly from the ***sklearn*** library.  
The scikit-learn (sklearn) library provides a variety of datasets that are easy to use for practicing machine learning techniques. The Iris dataset is one of the datasets available directly in scikit-learn, making it very convenient for beginners to explore and use.  

Let's dive in:   

```python
# importing libraries

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.datasets import load_iris  ##to import the IRIS data from sklearn.datasets

# Load the Iris dataset
iris = load_iris()

# Print out basic information about the dataset
print(iris.keys())  # Outputs the keys of the dataset dictionary (data, target, etc.)

# Convert the dataset into a pandas DataFrame for easier analysis
df = pd.DataFrame(data=iris.data, columns=iris.feature_names)
df['species'] = pd.Categorical.from_codes(iris.target, iris.target_names)

# Display the first 5 rows
print(df.head())

# Display basic info about the dataset
print(df.info())

# Show the first few rows of the dataset
print(df.head())

# Statistical summary of the dataset
print(df.describe())
```
**Data Visualization**

```python
# Pair plot for all features to visualize relationships
sns.pairplot(df, hue="species")
plt.suptitle('Pair Plot of Iris Dataset', y=1.02)
plt.show()

# Correlation matrix and heatmap
corr = df.drop('species', axis=1).corr()  # Dropping the target column ('species')
sns.heatmap(corr, annot=True, cmap="coolwarm", fmt=".2f")
plt.title('Correlation Heatmap')
plt.show()

# Boxplot for sepal length distribution by species
plt.figure(figsize=(8,6))
sns.boxplot(x='species', y='sepal length (cm)', data=df)
plt.title('Sepal Length Distribution by Species')
plt.show()

# Boxplot for petal length distribution by species
plt.figure(figsize=(8,6))
sns.boxplot(x='species', y='petal length (cm)', data=df)
plt.title('Petal Length Distribution by Species')
plt.show()

# Violin plot for petal width by species
plt.figure(figsize=(8,6))
sns.violinplot(x='species', y='petal width (cm)', data=df)
plt.title('Petal Width Distribution by Species')
plt.show()

# Scatter plot of sepal length vs sepal width
plt.figure(figsize=(8,6))
sns.scatterplot(x='sepal length (cm)', y='sepal width (cm)', hue='species', data=df)
plt.title('Sepal Length vs Sepal Width')
plt.show()
```

### ***Check out the Data_Visualization.ipynb file [here](https://colab.research.google.com/drive/1Uycq6Z0yfc-9VxPn4niYa_LkH4z52t7N?usp=sharing)***   <a name="file"></a>

---

## **5. Practical Use Cases** <a name="Use-Case"></a>
- **Retail**: Analyzing sales trends to identify top-performing products.
- **Finance:** Studying stock market trends or customer spending patterns.
- **Healthcare:** Visualizing patient data for insights into diseases.
- **Social Media:** Analyzing user behavior to improve engagement.

## **6. Key Takeaways** <a name="KT"></a>
- NumPy is essential for numerical computations.
- Pandas is your go-to tool for data manipulation.
- Matplotlib and Seaborn help visualize insights effectively.
- Practice with real datasets to master these libraries.

In the next session, we’ll dive deeper into NumPy, learning how to perform advanced numerical computations that power data science workflows.

**Stay curious, keep exploring, and power up your data science journey with Python!**


- <a href="{{ site.baseurl }}/day10/" style="font-size: 16px;">  Day 10: Exploring Python Libraries and Frameworks – Powering Up Your Development </a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day12/" style="font-size: 16px;">  Day 12: NumPy Basics – Powerful Numerical Computing  </a>
