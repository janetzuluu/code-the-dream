**Assignment: Python Operators, Control Flow, Calculator Implementation, and Data Manipulation with Pandas**

**Objective:** In this assignment, you will practice using Python operators, control flow statements, implementing a simple calculator with a loop, and manipulating data using the Pandas library. Complete the tasks below, modifying the provided code where needed and adding your own implementations.

### **Task 1: Arithmetic Operations**
1. Create a function called `perform_operations` that takes two arguments (`a` and `b`).

2. Implement the following arithmetic operations inside the function and print the results:
   - Addition
   - Subtraction
   - Multiplication
   - Division (handle the case where `b` is zero)
   - Floor Division (handle the case where `b` is zero)
   - Modulus (handle the case where `b` is zero)
   - Exponentiation

3. Call the function with example values `a = 10` and `b = 3` and print the results.

### **Task 2: Comparison Operations**
1. Create a function called `compare_numbers` that takes two arguments (`a` and `b`).

2. Implement the following comparison operations inside the function and print the results:
   - Equality (`==`)
   - Inequality (`!=`)
   - Greater than (`>`)
   - Less than (`<`)
   - Greater than or equal to (`>=`)
   - Less than or equal to (`<=`)

3. Call the function with example values `a = 10` and `b = 3` and print the results.

### **Task 3: Calculator with User Input**
1. Create a function called `calculator` that continuously asks the user for two numbers and an operation until they decide to quit.

2. Implement the following features inside the function:
   - Ask the user to input two numbers (`num1` and `num2`).
   - Ask the user to input an operation (`+`, `-`, `*`, `/`) or `q` to quit the calculator.
   - Perform the requested operation and print the result.
   - Handle division by zero when the user inputs `/` and `num2` is zero.
   - Handle invalid inputs using a `try-except` block to ensure the user inputs valid numbers.

3. Call the `calculator` function to allow the user to perform calculations.

### **Task 4: Data Manipulation with Pandas**
1. **Creating and Manipulating DataFrames**
   - Create a DataFrame from a dictionary containing the following data:
     - `Name`: ['Alice', 'Bob', 'Charlie']
     - `Age`: [25, 30, 35]
     - `City`: ['New York', 'Los Angeles', 'Chicago']
   - Print the DataFrame.
   - Add a new column called `Salary` with values `[70000, 80000, 90000]` and print the updated DataFrame.
   - Modify the `Age` column by incrementing each value by 1 and print the updated DataFrame.

2. **Loading Data from CSV and JSON Files**
   - Load data from a CSV file (`sample_data.csv`) into a DataFrame and print it. (You can create the CSV file using the data from the previous step).
   - Load data from a JSON file (`sample_data.json`) containing the following data:
     ```json
     [
       {"Name": "Eve", "Age": 28, "City": "Miami"},
       {"Name": "Frank", "Age": 40, "City": "Seattle"}
     ]
     ```
   - Print the DataFrame loaded from the JSON file.

3. **Data Inspection**
   - Use the `head()` method to print the first 5 rows of the DataFrame created from the dictionary.
   - Use the `tail(2)` method to print the last 2 rows of the DataFrame.
   - Use the `info()` method to print a concise summary of the DataFrame.

4. **Data Selection: Indexing and Slicing DataFrames**
   - Use indexing to select the `Name` column from the DataFrame and print it.
   - Select multiple columns (`Name` and `Salary`) and print them.
   - Slice the first three rows of the DataFrame using `iloc` and print them.

5. **Data Aggregation: Grouping Data Using groupby() and Aggregation Functions**
   - Group the DataFrame by the `Age` column and aggregate the `Salary` column using `mean`, `sum`, and `count` functions. Print the resulting DataFrame.

6. **Merging and Joining DataFrames**
   - Create another DataFrame similar to the one created in Task 4.1 with different names and values.
   - Merge the two DataFrames on the `Name` column using an outer join and print the merged DataFrame.
   - Set the `Name` column as the index for both DataFrames and join them using the `join()` method. Print the resulting DataFrame.

7. **Data Saving**
   - Save the modified DataFrame (created in Task 4.1) to a new CSV file named `modified_data.csv`.
   - Save the DataFrame (loaded from JSON) to a new JSON file named `output_data.json`.

8. **Advanced Data Manipulation**
   - **Data Selection**: Using the sample DataFrame created earlier (`df1`), perform the following:
     - Select the `Name` column and print it.
     - Select the `Name` and `Salary` columns and print them.
     - Slice the first three rows of the DataFrame using `iloc` and print them.
   
   - **Data Aggregation**: Group the sample DataFrame (`df1`) by the `Age` column and calculate the mean, sum, and count of the `Salary` column. Print the resulting DataFrame.
   
   - **Merging and Joining DataFrames**:
     - Create a second sample DataFrame (`df2`) with different values.
     - Merge `df1` and `df2` on the `Name` column using an outer join and print the result.
     - Set the `Name` column as the index for both DataFrames and join them using the `join()` method. Print the resulting DataFrame.

### **Submission:**
Submit your completed Python code, including all tasks, in a `.py` file or a Jupyter notebook. Make sure to include comments explaining your code where necessary.

