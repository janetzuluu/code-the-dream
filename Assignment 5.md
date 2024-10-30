

## **Assignment: Data Cleaning and Validation with Pandas**

### **Objective:**
This assignment focuses on exploring fundamental data cleaning and validation techniques using the Pandas library in Python. You will learn how to handle missing data, transform data types, remove duplicates, manage outliers, standardize data, encode categorical variables, and validate data ranges.

### **Tasks:**

### **Task 1: Handling Missing Data**
1. **Create a DataFrame using the provided data:**
   - The DataFrame contains columns for 'Name', 'Age', 'Salary', 'Join_Date', and 'City', with some missing values.
   - Print the original DataFrame.

2. **Perform the following operations on the DataFrame:**
   - **Remove rows with missing values** using the `dropna()` method and print the updated DataFrame.
   - **Replace missing values** using the `fillna()` method:
     - Replace missing 'Name' values with `'Unknown'`.
     - Replace missing 'Age' values with the **mean** of the 'Age' column.
     - Replace missing 'Salary' values with the **median** of the 'Salary' column.
     - Replace missing 'Join_Date' values with `'2020-01-01'`.
   - Print the updated DataFrame after replacing missing values.

### **Task 2: Data Transformation**
1. **Convert Data Types:**
   - Convert the 'Age' column to **integer** type using `astype(int)`.
   - Convert the 'Join_Date' column to **datetime** format using `pd.to_datetime()`.
   - Print the updated DataFrame.

### **Task 3: Removing Duplicates**
1. **Identify and remove duplicate records:**
   - Use the `duplicated()` method to identify duplicate rows in the DataFrame.
   - Use the `drop_duplicates()` method to remove duplicate rows.
   - Print the updated DataFrame.

### **Task 4: Handling Outliers**
1. **Identify and replace outliers in the 'Age' column:**
   - Consider outliers as values greater than 100 or less than 0.
   - Replace outliers with the **median** of the 'Age' column.
   - Print the updated DataFrame after handling outliers.

### **Task 5: Standardizing Data**
1. **Standardize the 'Name' column:**
   - Convert all names to lowercase and trim any leading or trailing whitespace using `str.lower()` and `str.strip()`.
   - Print the updated DataFrame.

2. **Standardize inconsistent entries in the 'City' column:**
   - Replace variations like 'new york' with 'New York' and 'la' or 'los angeles' with 'Los Angeles'.
   - Print the updated DataFrame.

### **Task 7: Validating Data Ranges**
1. **Ensure the 'Age' column contains values within the valid range (18 to 65):**
   - Replace invalid ages (less than 18 or greater than 65) with `NaN`.
   - Fill the missing values with the **median** of the 'Age' column.
   - Print the updated DataFrame.

### **Submission:**
- Save your completed code in a `.py` file or Jupyter Notebook.
- Ensure each task is correctly implemented and include comments explaining each step.


