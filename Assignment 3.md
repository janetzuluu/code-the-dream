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
   - Load data from a JSON file (`sample_data.json`) 
    
   - Print the DataFrame loaded from the JSON file and CSV.

3. **Data Inspection**
   - Use the `head()` method to print the first 5 rows of the DataFrame created from the dictionary.
   - Use the `tail(2)` method to print the last 2 rows of the DataFrame.
   - Use the `info()` method to print a concise summary of the DataFrame.

### **Submission:**
Submit your completed Python code, including all tasks, in a `.py` file or a Jupyter notebook. Make sure to include comments explaining your code where necessary.

