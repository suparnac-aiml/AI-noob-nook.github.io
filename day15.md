---
layout: default
title: " Day 15: Exploratory Data Analysis (EDA) – Extracting Insights from Data"
permalink: /day15/
---

# Day 15: Exploratory Data Analysis (EDA) – Extracting Insights from Data

## Introduction
Exploratory Data Analysis (EDA) is a crucial step in the data science workflow. It involves examining datasets to summarize their main characteristics, often with visual methods. EDA helps you uncover patterns, detect anomalies, test hypotheses, and check assumptions through descriptive statistics and graphical representations.

In this guide, we’ll cover the fundamentals of EDA, tools you can use, and key techniques to extract valuable insights from your data.

---

## Table of Contents
- [Why EDA Matters?](#Why)
- [Tools for EDA](#Tools)
- [Key Steps in EDA](#Steps)
- [Visualizing Data](#Visualizing)
- [Tips for Effective EDA](#Tips)
- [Advanced EDA Tools](#Advanced-Tools)
- [Wrap-Up](#Wrap-Up)
- [Practice](#Practice)
- <a href="{{ site.baseurl }}/day14/" style="font-size: 16px;">  Day 14: Data Visualization with Matplotlib and Seaborn </a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day16/" style="font-size: 16px;">  Day 16: SQL Basics – Querying and Managing Databases </a>



---


## Why EDA Matters? <a name="Why"></a>
1. **Understanding the Data**: EDA helps you comprehend the structure, distribution, and relationships within the data.
2. **Data Cleaning**: Identifying missing values, outliers, or errors in the data.
3. **Feature Engineering**: Discovering relationships between variables to create meaningful features for machine learning.
4. **Hypothesis Generation**: Formulating hypotheses for further analysis or modeling.

---

## Tools for EDA <a name="Tools"></a>
### Python Libraries
- **Pandas**: Data manipulation and basic analysis.
- **Matplotlib** and **Seaborn**: For visualizations.
- **NumPy**: Numerical operations.
- **Plotly**: Interactive visualizations.
- **SciPy**: Advanced statistical analysis.

---

## Key Steps in EDA <a name="Steps"></a>
### 1. **Data Loading**
Start by loading your dataset into a Pandas DataFrame. Ensure you can access and view the data structure.

```python
import pandas as pd

# Load dataset
df = pd.read_csv('data.csv')

# View the first few rows
print(df.head())
```
---

### 2. Data Overview
Understand the structure of your data:

- Check the dimensions (rows and columns).  
- Look at data types, column names, and non-null counts.

```python
# Basic overview
print(df.info())

# Summary statistics
print(df.describe())
```

### 3. Handling Missing Values
Identify and handle missing data:

- Remove rows or columns with excessive missing values.  
- Impute missing data using mean, median, or mode.

```python
# Checking for missing values
print(df.isnull().sum())

# Fill missing values with mean
df['column_name'] = df['column_name'].fillna(df['column_name'].mean())
```

### 4. Data Cleaning
- Remove duplicates.  
- Fix inconsistencies (e.g., typos, wrong formats).  

```python
# Remove duplicates
df = df.drop_duplicates()

# Convert column to lowercase
df['column_name'] = df['column_name'].str.lower()
```

### 5. Univariate Analysis
Examine individual variables to understand their distribution:

- For numerical data: histograms, box plots.  
- For categorical data: bar plots, pie charts.

```python
import matplotlib.pyplot as plt
import seaborn as sns

# Histogram for numerical data
sns.histplot(df['numerical_column'], kde=True)
plt.show()

# Bar plot for categorical data
df['categorical_column'].value_counts().plot(kind='bar')
plt.show()
```

### 6. Bivariate Analysis
Analyze relationships between two variables:

- Numerical-Numerical: Scatter plots, correlation matrix.    
- Categorical-Numerical: Box plots, violin plots.    
- Categorical-Categorical: Crosstab analysis  

```python
  # Scatter plot
sns.scatterplot(x='var1', y='var2', data=df)
plt.show()

 # Correlation heatmap
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.show()
```

### 7. Multivariate Analysis
Examine relationships involving three or more variables:

- Pair plots for overall relationships.  
- 3D scatter plots for interactive analysis.  

```python
# Pair plot
sns.pairplot(df)
plt.show()
```

### 8. Outlier Detection
Identify data points that deviate significantly from others:

-  Box plots and IQR for univariate outliers.  
- Z-score or DBSCAN for multivariate outliers.

```python
# Box plot for outliers
sns.boxplot(x=df['numerical_column'])
plt.show()

# Z-score for outliers
from scipy.stats import zscore
df['z_score'] = zscore(df['numerical_column'])
outliers = df[df['z_score'].abs() > 3]
print(outliers)
```

### 9. Feature Relationships
Study interactions between features to improve modeling:

- Interaction terms.  
- Feature scaling (normalization or standardization).

```python
# Feature scaling
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
df['scaled_column'] = scaler.fit_transform(df[['numerical_column']])
```

---

## Visualizing Data <a name="Visualizing"></a>
Visualization is key to EDA. Use the following for impactful insights:  

1. **Histograms:** Show the distribution of numerical data.  
2. **Boxplots:** Highlight the spread and outliers.  
3. **Heatmaps:** Display correlations.  
4. **Scatter plots:** Reveal relationships.

---

## Tips for Effective EDA <a name="Tips"></a>
- **Ask Questions:** What patterns are evident? Are there anomalies? How do variables interact?  
- **Iterate:** EDA is not a one-time process. Revisit as you learn more.   
- **Automate:** Use libraries like pandas-profiling or sweetviz for automated EDA.  

---

## Advanced EDA Tools <a name="Advanced-Tools"></a>
- **Pandas Profiling:** Generates a detailed EDA report.  
- **Sweetviz:** Offers quick and interactive visualizations.  
- **Autoviz:** Automates data visualization for EDA.

```python
# Example: Pandas Profiling
from pandas_profiling import ProfileReport

profile = ProfileReport(df)
profile.to_file("eda_report.html")
```


---

## Wrap-Up <a name="Wrap-Up"></a>
EDA is a fundamental process for uncovering the hidden story behind your data. By mastering EDA techniques, you can build robust models, make better predictions, and generate actionable insights. Make it a habit to thoroughly explore your data before diving into modeling.

---

## Practice <a name="Practice"></a>
- Load a dataset of your choice (e.g., Titanic, Iris, or a custom dataset).  
- Perform the above steps for EDA.  
- Visualize at least 5 insights and document your observations.

---

- <a href="{{ site.baseurl }}/day14/" style="font-size: 16px;">  Day 14: Data Visualization with Matplotlib and Seaborn </a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day16/" style="font-size: 16px;">  Day 16: SQL Basics – Querying and Managing Databases </a>
