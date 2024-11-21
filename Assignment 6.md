Assignment: Advanced Data Cleaning and Validation Tasks
Complete the tasks below to demonstrate your understanding of data cleaning and validation techniques. Submit your code and outputs for each task.

Task 1: Clean Address Data
Create a list called text_data containing the following address strings:
" 123 Main St"
"456 Elm St."
"789 Pine Avenue"
Write a script using the re module to:
Remove any extra spaces between words.
Strip leading and trailing spaces.
Store the cleaned addresses in a new list called cleaned_data.
Print the cleaned addresses.
Task 2: Handle Outliers in a DataFrame
Create a dictionary named data_with_outliers with two columns:
Name: A list of names (['Alice', 'Bob', 'Charlie']).
Age: A list of ages ([25, 130, 35]).
Convert the dictionary into a DataFrame called df_outliers.
Identify and replace outliers in the Age column:
Define outliers as ages greater than 100.
Replace these outliers with the median value of the Age column.
Print the updated DataFrame.
Task 3: Impute Missing Values
Create a dictionary with the following data:
Name: A list of names (['Alice', 'Bob', 'Charlie']).
Age: A list of ages with a missing value ([25, None, 35]).
Convert the dictionary into a DataFrame called df_nan.
Calculate the median value of the Age column.
Fill the missing value in the Age column with the calculated median.
Print the updated DataFrame.
Submission
Submit your completed code for each task.
Include the output for each step.
Ensure your code is well-documented with comments explaining your approach.
