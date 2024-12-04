---
layout: default
title: "Day 14: Data Visualization with Matplotlib and Seaborn "
permalink: /day14/
---

# Day 14: Data Visualization with Matplotlib and Seaborn

Data visualization is a crucial step in the data analysis process, enabling us to interpret and communicate insights effectively. Python offers powerful libraries like Matplotlib and Seaborn for creating visual representations of data. Let's explore these libraries in detail.

---

## Table of Contents
- [Why Data Visualization?](#Why-Data-Visualization)
- [Matplotlib: The Basics](#Matplotlib)
- [Seaborn: Statistical Data Visualization](#Seaborn)
- [Comparison: Matplotlib vs. Seaborn](#Comparison)
- [Combining Matplotlib and Seaborn](#Combining)
- [Real-World Use Cases](#Use-Cases)
- [Hands-On Practice](#Practice)
- [Wrap-Up](#Wrap-Up)
- <a href="{{ site.baseurl }}/day13/" style="font-size: 16px;">  Day 13: Pandas – Data Manipulation and Analysis </a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day15/" style="font-size: 16px;">  Day 15: Exploratory Data Analysis (EDA) – Extracting Insights from Data (Upcoming) </a>

---

## Why Data Visualization? <a name="Why-Data-Visualization"></a>

- **Understand Data:** Visualization helps identify patterns, trends, and outliers.

- **Communication:** It simplifies complex data for easy interpretation.

- **Decision Making:** Visual insights guide informed decision-making.

----

## Matplotlib: The Basics <a name="Matplotlib"></a>

Matplotlib is a versatile library for creating static, interactive, and animated visualizations. It gives fine-grained control over plots but requires more code compared to Seaborn.

#### Installation
```python
pip install matplotlib
```

### Commonly Used Functions

- **plot():** Create line plots.

- **scatter():** Generate scatter plots.

- **bar():** Make bar charts.

- **hist():** Display histograms.

- **pie():** Plot pie charts.

- **xlabel() / ylabel():** Add axis labels.

- **title():** Add a title to the plot.

- **legend():** Add a legend.

#### Example: Line Plot
```python
import matplotlib.pyplot as plt

# Data
years = [2015, 2016, 2017, 2018, 2019]
sales = [200, 250, 300, 400, 500]

# Plot
plt.plot(years, sales, marker='o', color='blue', label='Sales')
plt.title('Yearly Sales')
plt.xlabel('Year')
plt.ylabel('Sales (in units)')
plt.legend()
plt.grid(True)
plt.show()
```

---

## Seaborn: Statistical Data Visualization <a name="Seaborn"></a

Seaborn is built on top of Matplotlib and simplifies statistical data visualization. It includes themes and advanced plot types, making it more concise and visually appealing.

### Installation

```python
pip install seaborn
```

### Commonly Used Functions

- **scatterplot():** Create scatter plots.

- **lineplot():** Generate line plots.

- **histplot():** Display histograms.

- **boxplot():** Create box plots.

- **heatmap():** Visualize correlation matrices.

- **pairplot():** Plot pairwise relationships.

- **violinplot():** Combine box plot and KDE plot.

#### Example: Scatter Plot with Regression
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample Data
data = sns.load_dataset('iris')

# Scatter Plot
sns.scatterplot(data=data, x='sepal_length', y='sepal_width', hue='species', style='species')
plt.title('Sepal Dimensions by Species')
plt.show()
```

---

## Comparison: Matplotlib vs. Seaborn <a name="Comparison"></a>

| Feature           | Matplotlib                  | Seaborn                            |
|-------------------|-----------------------------|-------------------------------------|
| Customization     | High (fine-grained control) | Moderate (simplified syntax)       |
| Plot Aesthetics   | Basic                       | Advanced (predefined styles)       |
| Ease of Use       | Requires more code          | Concise and beginner-friendly      |
| Statistical Plots | Limited                     | Built-in support for complex plots |


---

## Combining Matplotlib and Seaborn <a name="Combining"></a>

You can use Matplotlib’s functions to enhance Seaborn plots.

#### Example: Annotated Heatmap
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Sample Data
flights = sns.load_dataset('flights')

# Pivot Data
pivot_data = flights.pivot('month', 'year', 'passengers')

# Heatmap
plt.figure(figsize=(10, 6))
sns.heatmap(pivot_data, annot=True, fmt="d", cmap="YlGnBu")
plt.title('Monthly Passengers (1949-1960)')
plt.show()
```

---

## Real-World Use Cases <a name="Use-Cases"></a>

- **Business Analysis:** Analyze sales trends and customer demographics.

- **Healthcare:** Visualize patient data and track disease spread.

- **Finance:** Explore stock market trends and correlations.

- **Education:** Compare student performance across subjects.

- **Science:** Interpret experimental results and visualize relationships.

---

## Hands-On Practice <a name="Practice"></a>

**Task 1: Analyze Tips Dataset**

- Load the tips dataset using Seaborn.

- Visualize the distribution of tips using histplot.

- Create a scatter plot of total_bill vs. tip with hue as time.

**Task 2: Correlation Heatmap**

- Use the iris dataset.

- Create a heatmap to visualize correlations between numeric features.

---

## Wrap-Up <a name="Wrap-Up"></a>

- **Matplotlib:** Ideal for detailed and customizable plots.

- **Seaborn:** Simplifies statistical visualization with beautiful defaults.

- Combine both libraries for advanced visualizations.

---

**Next Steps:** Practice creating different types of plots using your datasets. Experiment with customizations to enhance clarity and aesthetics.

---

- <a href="{{ site.baseurl }}/day13/" style="font-size: 16px;">  Day 13: Pandas – Data Manipulation and Analysis </a>
- <a href="{{ site.baseurl }}/">Back to Home</a>
- <a href="{{ site.baseurl }}/day15/" style="font-size: 16px;">  Day 15: Exploratory Data Analysis (EDA) – Extracting Insights from Data (Upcoming) </a>
