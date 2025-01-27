
## Lesson 05 — Foundations of Data Cleaning and Validation

**Lesson Overview**

* **Learning Objective:** Students will gain foundational skills in data cleaning, focusing on handling missing data, transforming data types, identifying/removing duplicates, and introducing simple feature engineering and validation techniques. By the end of the lesson, students will be able to clean raw datasets for meaningful analysis.

**Topics**

1. Identifying and Understanding Missing Data
2. Basic Data Transformation
3. Identifying and Removing Duplicates
4. Introduction to Feature Engineering
5. Basic Validation Techniques
6. Understanding Data Profiling

### 5.1 Identifying and Understanding Missing Data

**Overview**

Missing data can occur due to human error, system failures, or incomplete data collection. Before addressing missing values, it’s crucial to understand their patterns and impacts.

**Key Concepts**

* **Identifying Missing Data**
    * Use `isna()` to find missing values.
    * Count missing values in rows and columns with `isna().sum()`.
    * Visualize missing data patterns using seaborn or missingno.
* **Analyzing Patterns**
    * Determine if data is:
        * MCAR (Missing Completely at Random): No relationship between missing values and other data.
        * MAR (Missing at Random): Missingness depends on observed data.
        * MNAR (Missing Not at Random): Missingness depends on unobserved data.

**Code Example: Visualizing Missing Data**

```python
import pandas as pd
import seaborn as sns
import missingno as msno

# Sample DataFrame
data = {'Name': ['Alice', 'Bob', None, 'David'],
        'Age': [24, None, 22, 35],
        'Score': [85, None, 88, 76]}
df = pd.DataFrame(data)

# Visualize missing data
sns.heatmap(df.isna(), cbar=False, cmap="viridis")
msno.matrix(df)
```

**Why Analyze Missing Data?**

* Understand the extent and potential causes of missing data.
* Decide on the most appropriate method to handle it (e.g., removal, imputation).

### 5.2 Basic Data Transformation

**Overview**

Data transformation ensures that data is uniform and ready for analysis. This includes handling inconsistent formats, changing types, and scaling numerical values.

**Key Techniques**

* **Type Conversion:** Using `astype()` or `pd.to_numeric()`.
* **Formatting Dates:** Use `pd.to_datetime()` for proper date handling.
* **Scaling and Normalization:**
    * Min-Max Scaling: Rescales data to a range of 0–1.
    * Z-Score Normalization: Centers data around 0 with a standard deviation of 1.

**Expanded Example: Scaling and Normalization**

```python
import pandas as pd
from sklearn.preprocessing import MinMaxScaler, StandardScaler

# Sample DataFrame
data = {'Name': ['Alice', 'Bob', 'Charlie'],
        'Income': [45000, 54000, 32000],
        'Age': [25, 30, 22]}
df = pd.DataFrame(data)

# Min-Max Scaling
scaler = MinMaxScaler()
df['Scaled_Income'] = scaler.fit_transform(df[['Income']])

# Z-Score Normalization
z_scaler = StandardScaler()
df['Normalized_Age'] = z_scaler.fit_transform(df[['Age']])

print(df)
```

### 5.3 Identifying and Removing Duplicates

**Overview**

Duplicate rows can arise from data entry errors or merging datasets. Cleaning duplicates ensures accurate metrics and results.

**Key Techniques**

* **Identifying Duplicates**
    * Use `duplicated()` to check for duplicate rows or specific columns.
    * Count duplicates with `duplicated().sum()`.
* **Removing Duplicates**
    * Use `drop_duplicates()` to remove duplicates while keeping the first or last occurrence.

**Expanded Example: Advanced Duplicate Handling**

```python
data = {'Name': ['Alice', 'Bob', 'Alice', 'David'],
        'Age': [24, 27, 24, 35],
        'Score': [85, 92, 85, 76]}
df = pd.DataFrame(data)

# Identify duplicates
print("Duplicate Rows:")
print(df[df.duplicated()])

# Remove duplicates based on Name and keep the highest Score
df_cleaned = df.sort_values('Score', ascending=False).drop_duplicates(subset='Name')
print(df_cleaned)
```

### 5.4 Introduction to Feature Engineering

**Overview**

Feature engineering creates new features or transforms existing ones to improve the dataset’s utility and insights.

**Key Techniques**

* **Combining Features:** Derive new metrics from existing columns (e.g., `Revenue = Units Sold * Price`).
* **Binning:** Convert continuous variables into discrete groups with `pd.cut()` or `pd.qcut()`.
* **Extracting Components:** Break down dates into Year, Month, and Day.

**Expanded Example: Advanced Feature Engineering**

```python
# Sample DataFrame
data = {'Name': ['Alice', 'Bob', 'Charlie'],
        'JoinDate': ['2023-01-15', '2022-12-20', '2023-03-01']}
df = pd.DataFrame(data)

# Convert JoinDate to datetime and extract Year, Month
df['JoinDate'] = pd.to_datetime(df['JoinDate'])
df['Year'] = df['JoinDate'].dt.year
df['Month'] = df['JoinDate'].dt.month

print(df)
```

### 5.5 Basic Validation Techniques

**Overview**

Validation ensures that the data meets expected formats, ranges, and categories.

**Key Techniques**

* **Validating Ranges:** Ensure numerical values fall within specified bounds.
* **Validating Categories:** Verify categorical columns against allowed values.
* **Cross-Column Validation:** Check logical consistency across columns (e.g., `EndDate > StartDate`).

**Expanded Example: Cross-Column Validation**

```python
data = {'StartDate': ['2023-01-01', '2023-03-01', '2023-02-01'],
        'EndDate': ['2023-02-01', '2023-01-15', '2023-02-15']}
df = pd.DataFrame(data)

# Convert to datetime
df['StartDate'] = pd.to_datetime(df['StartDate'])
df['EndDate'] = pd.to_datetime(df['EndDate'])

# Validate EndDate is after StartDate
df['ValidDates'] = df['EndDate'] > df['StartDate']
print(df)
```

### 5.6 Understanding Data Profiling

**Overview**

Data profiling provides a summary of the dataset, helping identify issues like missing data, outliers, and data distribution.

**Techniques**

* **Descriptive Statistics:** Use `.describe()` for summary statistics.
* **Visual Profiling:** Visualize distributions with `hist()` or `sns.pairplot()`.
* **Automated Tools:** Use libraries like pandas-profiling for detailed reports.

**Example: Data Profiling with pandas-profiling**

```python
from pandas_profiling import ProfileReport

# Create a profile report
profile = ProfileReport(df, title="Data Profiling Report", explorative=True)
profile.to_file("data_report.html")
```

**Check for Understanding**

* **Which method removes duplicates based on specific columns?**
    * A) `duplicated(subset=...)`
    * B) `drop_duplicates(subset=...)`
    * C) `isna()`
    * D) `fillna()`
    * **Answer: B) `drop_duplicates(subset=...)`**

* **What does `pd.cut()` do?**
    * A) Converts text to lowercase
    * B) Categorizes continuous data into discrete bins
    * C) Removes duplicates from a DataFrame
    * D) Detects missing data
    * **Answer: B) Categorizes continuous data into discrete bins**

* **What library provides detailed automated profiling reports?**
    * A) pandas
    * B) pandas-profiling
    * C) seaborn
    * D) numpy
    * **Answer: B) pandas-profiling**

**Summary**

In this lesson, you learned:

* How to identify, analyze, and handle missing data.
* How to transform data types, scale numerical values, and handle dates.
* How to identify and remove duplicates effectively.
* The basics of feature engineering for deriving insights.
* Data validation techniques and data profiling for comprehensive analysis.

These foundational skills will set the stage for advanced cleaning techniques in Lesson 6.
```
