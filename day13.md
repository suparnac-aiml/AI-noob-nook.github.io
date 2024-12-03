---
layout: default
title: "Day 13: Pandas – Data Manipulation and Analysis"
permalink: /day13/
---

# Day 13: Pandas – Data Manipulation and Analysis

Pandas is one of the most powerful and widely-used Python libraries for data manipulation and analysis. It provides data structures and functions needed to work on structured data seamlessly. Pandas makes it easy to read, write, and manipulate data with powerful and flexible tools, making it a crucial library for data science.

## Table of Contents

1. [Introduction to Pandas](#introduction-to-pandas)
2. [Pandas Data Structures](#pandas-data-structures)
3. [Loading Data into Pandas](#loading-data-into-pandas)
4. [Basic Operations with Pandas](#basic-operations-with-pandas)
5. [Data Selection and Filtering](#data-selection-and-filtering)
6. [Data Cleaning and Preprocessing](#data-cleaning-and-preprocessing)
7. [Merging and Joining DataFrames](#merging-and-joining-dataframes)
8. [Aggregation and Grouping Data](#aggregation-and-grouping-data)
9. [Data Visualization with Pandas](#data-visualization-with-pandas)
10. [Real-Time Use Case Example](#real-time-use-case-example)
11. [Wrap-Up](#Wrap-Up)
- <a href="{{ site.baseurl }}/day12/" style="font-size: 16px;">  Day 12: NumPy Basics – Powerful Numerical Computing </a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day14/" style="font-size: 16px;">  Day 14: Data Visualization with Matplotlib and Seaborn  (Upcoming) </a>


---

## Introduction to Pandas <a name=""></a>

Pandas provides two primary data structures:

- **Series**: A one-dimensional labeled array.
- **DataFrame**: A two-dimensional table of data with labeled axes (rows and columns).

Both these structures are built on top of NumPy arrays and allow for powerful data manipulation and analysis.

## Pandas Data Structures <a name=""></a>

### Series
A **Series** is similar to a column in an Excel spreadsheet or a database table. It consists of an ordered sequence of values and an associated array of data labels (index). It can hold various data types such as integers, strings, or floating point numbers.

#### Example:
```python
import pandas as pd

# Creating a simple Series
data = [1, 2, 3, 4, 5]
series = pd.Series(data)
print(series)
```
### DataFrame

A **DataFrame** is a two-dimensional labeled data structure with columns of potentially different types. It's similar to a table or an Excel sheet, where each column can have a different data type.

#### Example:
```python
import pandas as pd

# Creating a DataFrame from a dictionary
data = {'Name': ['John', 'Anna', 'Peter', 'Linda'],
        'Age': [28, 24, 35, 32],
        'City': ['New York', 'Paris', 'Berlin', 'London']}

df = pd.DataFrame(data)
print(df)
```
## Loading Data into Pandas <a name="loading-data-into-pandas"></a>

You can load data into Pandas from various file formats, including CSV, Excel, JSON, and SQL databases.

#### Example – Loading CSV File:
```python
# Load a CSV file into a DataFrame
df = pd.read_csv('data.csv')
print(df.head())  # Shows first 5 rows
```

## Basic Operations with Pandas <a name="basic-operations-with-pandas"></a>

Pandas offers a wide range of operations that can be performed on Series and DataFrames, such as:

- Sorting: Sorting data by a column or index.
- Filtering: Extracting subsets of data based on conditions.
- Descriptive Statistics: Summarizing data using functions like mean(), std(), sum(), etc.

#### Example – Sorting and Descriptive Statistics:

```python
# Sorting by a column
df_sorted = df.sort_values(by='Age')

# Summary statistics
print(df.describe())
```
## Data Selection and Filtering <a name="data-selection-and-filtering"></a> 

Pandas makes it easy to select specific rows, columns, or subsets of data using various indexing methods like .loc[] and .iloc[].

#### Example – Selecting Specific Data:
```python
# Selecting a specific column
age_column = df['Age']

# Selecting rows based on conditions
young_people = df[df['Age'] < 30]
print(young_people)
```

## Data Cleaning and Preprocessing <a name="data-cleaning-and-preprocessing)"></a>

Before working with data, it is essential to clean and preprocess it. Pandas provides functions to handle missing data, duplicate values, and incorrect data types.

#### Example – Handling Missing Data:
```python
# Fill missing values with the mean
df['Age'].fillna(df['Age'].mean(), inplace=True)

# Drop rows with missing values
df.dropna(inplace=True)
```

## Merging and Joining DataFrames <a name="merging-and-joining-dataframes)"></a>

You can combine multiple DataFrames using operations like merging and joining. These operations allow you to align data from different sources into a single DataFrame.

#### Example – Merging DataFrames:
```python
# Merge two DataFrames on a common column 'ID'
df_merged = pd.merge(df1, df2, on='ID')
```

## Aggregation and Grouping Data <a name="aggregation-and-grouping-data"></a>

Pandas allows you to group data by one or more columns and perform aggregation operations (e.g., sum, average, count) on them.

#### Example – Grouping and Aggregation:
```python
# Group by 'City' and calculate the average age
grouped = df.groupby('City')['Age'].mean()
print(grouped)
```
## Data Visualization with Pandas <a name="data-visualization-with-pandas"></a>

Pandas integrates well with visualization libraries like Matplotlib and Seaborn, allowing you to create plots and charts directly from DataFrames.

#### Example – Plotting:
```python
import matplotlib.pyplot as plt

# Plotting a histogram of ages
df['Age'].plot(kind='hist', bins=10, title='Age Distribution')
plt.show()
```

## Real-Time Use Case Example <a name="real-time-use-case-example"></a>

Let's analyze a real dataset, the Iris dataset, which contains data about different species of flowers, including their measurements.

#### Example Code: Analyzing and Visualizing the Iris Dataset
```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.datasets import load_iris

# Load Iris dataset
iris = load_iris()
df_iris = pd.DataFrame(data=iris.data, columns=iris.feature_names)

# Add the target column
df_iris['species'] = iris.target

# Display basic stats
print(df_iris.describe())

# Visualizing the data
sns.pairplot(df_iris, hue='species')
plt.show()

# Grouping by species and calculating mean values
grouped = df_iris.groupby('species').mean()
print(grouped)
```

This code demonstrates how to load the Iris dataset, perform some basic statistical analysis, and visualize the data using a pair plot.

## Wrap-Up <a name="Wrap-Up"></a>

Pandas is a key library in data science for data manipulation and analysis. Whether you're cleaning data, performing calculations, or visualizing insights, Pandas provides powerful and efficient tools. The integration with libraries like Matplotlib and Seaborn further strengthens its use for data visualization.

By the end of this day, you'll be comfortable with performing data manipulation, cleaning, and analysis with Pandas, a critical skill for any data scientist or analyst.

***Keep practicing and explore more advanced Pandas features to sharpen your data analysis skills!*** 

- <a href="{{ site.baseurl }}/day12/" style="font-size: 16px;">  Day 12: NumPy Basics – Powerful Numerical Computing </a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day14/" style="font-size: 16px;">  Day 14: Data Visualization with Matplotlib and Seaborn  (Upcoming) </a>
