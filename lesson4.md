
# **Lesson 04 — Data Wrangling and Aggregation**

## **Lesson Overview**
**Learning objective:** Students will learn how to efficiently select, aggregate, and combine data in Pandas to enable deeper insights and streamlined analysis.

### **Topics:**
1. Data Selection: Indexing and slicing DataFrames.
2. Data Aggregation: Grouping data using `groupby()` and aggregation functions like `sum()`, `mean()`, `count()`.
3. Merging and Joining: Combining multiple DataFrames with `merge()` and `join()`.

---

## **4.1 Data Selection**

### **Overview**
Indexing and slicing allow you to extract specific rows or columns from a DataFrame, making it easier to analyze subsets of your data.

### **Key Methods:**
- `.loc[]`: Select rows and columns by labels.
- `.iloc[]`: Select rows and columns by integer position.

### **Why Use Data Selection?**
Data selection helps you:
- Filter relevant data for analysis.
- Access specific values or ranges for visualization or calculation.
- Preprocess data by selecting subsets of interest.

### **Getting Started**
Before proceeding, ensure Pandas is installed:

```bash
pip install pandas
```

### **Example: Using `.loc[]` and `.iloc[]`**
```python
import pandas as pd

# Sample DataFrame
data = {'Name': ['Alice', 'Bob', 'Charlie', 'David'],
        'Age': [24, 27, 22, 32],
        'Score': [85, 92, 88, 76]}
df = pd.DataFrame(data)

# Select the 'Name' column
print(df['Name'])

# Select rows and specific columns
print(df.loc[0:2, ['Name', 'Age']])

# Select rows by position
print(df.iloc[:2])  # First two rows
```

---

## **4.2 Data Aggregation**

### **Overview**
Aggregating data involves summarizing it by groups, enabling insights at a higher level (e.g., total sales by region, average score by category).

### **Key Method:**
- `groupby()`: Groups data by one or more columns.
- Aggregation functions: `sum()`, `mean()`, `count()`, etc.

### **Why Use Aggregation?**
Aggregation simplifies data analysis by:
- Summarizing patterns across categories.
- Providing key metrics like totals, averages, and counts.
- Reducing data complexity.

### **Example: Using `groupby()`**
```python
# Group data by a column and calculate the sum
data = {'Category': ['A', 'B', 'A', 'B', 'C'],
        'Values': [10, 20, 30, 40, 50]}
df = pd.DataFrame(data)

# Group by 'Category' and calculate the sum
grouped = df.groupby('Category').sum()
print(grouped)

# Calculate the mean for each group
mean_values = df.groupby('Category')['Values'].mean()
print(mean_values)
```

---

## **4.3 Merging and Joining**

### **Overview**
Combine multiple DataFrames using shared keys (columns or indices). 

### **Key Methods:**
- `merge()`: Combines DataFrames on common columns.
- `join()`: Combines DataFrames based on their indices.

### **Why Use Merging and Joining?**
- Combine related datasets for comprehensive analysis.
- Handle data stored across multiple sources.
- Maintain relationships between data records.

### **Example: Using `merge()`**
```python
# Sample DataFrames
df1 = pd.DataFrame({'ID': [1, 2, 3], 'Name': ['Alice', 'Bob', 'Charlie']})
df2 = pd.DataFrame({'ID': [1, 2, 4], 'Score': [85, 92, 88]})

# Merge on the 'ID' column
merged_df = pd.merge(df1, df2, on='ID', how='inner')
print(merged_df)  # Inner join
```

### **Example: Using `join()`**
```python
# Join DataFrames by index
df1 = pd.DataFrame({'Name': ['Alice', 'Bob', 'Charlie']}, index=[1, 2, 3])
df2 = pd.DataFrame({'Score': [85, 92, 88]}, index=[1, 2, 4])

joined_df = df1.join(df2, how='outer')
print(joined_df)
```

---

## **Check for Understanding**

1. **How can you select rows where the "Age" column is greater than 25?**
   - A) `df.loc[df['Age'] > 25]`
   - B) `df.iloc[df['Age'] > 25]`
   - C) `df[['Age'] > 25]`
   - D) `df[df['Age'] > 25]`

2. **Which method is used to combine two DataFrames on their indices?**
   - A) `join()`
   - B) `merge()`
   - C) `groupby()`
   - D) `concat()`

**Answer Key:**
1. A  
2. A  

---

## **Summary**

In this lesson, you’ve learned:
- How to select and slice subsets of data using `.loc[]` and `.iloc[]`.
- How to use `groupby()` for aggregations like `sum()` and `mean()`.
- How to combine DataFrames using `merge()` and `join()`.

Use these techniques to perform advanced data analysis in Pandas. For further exploration, refer to the [Pandas Documentation](https://pandas.pydata.org/docs/) and Python's [official documentation](https://docs.python.org/3/).
```
