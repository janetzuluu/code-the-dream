
# **Lesson 08 — Advanced SQL and Database Integration**

## **Lesson Overview**
**Learning objective:** Students will deepen their understanding of SQL by learning advanced techniques such as subqueries, complex `JOIN`s, aggregation with functions, and using `HAVING` for conditional filtering.

---

## **8.1 Understanding Subqueries**

### **Overview**
Subqueries are nested SQL queries used to perform intermediate calculations or selections before the main query executes.

### **Key Concepts:**
- Use subqueries to fetch results dynamically within another query.
- Common use cases include finding maximum, minimum, or aggregated values.

### **Example:**
Find the highest-paid employee in each department using a subquery.
```sql
SELECT department_id, employee_id, salary
FROM Employees AS e
WHERE salary = (
    SELECT MAX(salary)
    FROM Employees
    WHERE department_id = e.department_id
);
```

### **Implementation in Python:**
```python
# Example using SQLite
conn = sqlite3.connect("company.db")
cursor = conn.cursor()

# Execute the query
query = """
SELECT department_id, employee_id, salary
FROM Employees AS e
WHERE salary = (
    SELECT MAX(salary)
    FROM Employees
    WHERE department_id = e.department_id
);
"""
cursor.execute(query)
print(cursor.fetchall())

conn.close()
```

---

## **8.2 Complex JOINs**

### **Overview**
Complex `JOIN`s allow you to retrieve data from multiple related tables.

### **Steps:**
1. Create a `Projects` table and insert sample data.
2. Use a `JOIN` to combine employee and project information through the department field.

### **Key Concepts:**
- `INNER JOIN`: Retrieves records with matching values in both tables.
- `LEFT JOIN`: Retrieves all records from the left table and matching records from the right.

### **SQL Example: Create and Populate a Projects Table**
```sql
CREATE TABLE Projects (
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    department TEXT NOT NULL
);

INSERT INTO Projects (name, department) VALUES
('Project A', 'HR'),
('Project B', 'IT'),
('Project C', 'Finance');
```

### **SQL Example: Complex JOIN**
List employees working in departments responsible for a specific project:
```sql
SELECT Employees.name, Projects.name AS project_name
FROM Employees
JOIN Projects ON Employees.department = Projects.department
WHERE Projects.name = 'Project A';
```

---

## **8.3 Aggregation**

### **Overview**
Aggregation functions like `MIN()`, `MAX()`, `COUNT()`, and `AVG()` allow you to summarize data across groups.

### **Task:**
Calculate the minimum and maximum salaries and the number of employees in each department.

### **SQL Example:**
```sql
SELECT department_id, 
       MIN(salary) AS min_salary, 
       MAX(salary) AS max_salary, 
       COUNT(employee_id) AS num_employees
FROM Employees
GROUP BY department_id;
```

### **Key Notes:**
- Use `GROUP BY` to organize results by department.
- Ensure fields in the `SELECT` clause are either aggregated or part of the `GROUP BY`.

---

## **8.4 Aggregation with HAVING**

### **Overview**
The `HAVING` clause filters aggregated results after the `GROUP BY` operation.

### **Task:**
List all departments where the average salary exceeds 70,000 and display the department manager.

### **SQL Example:**
```sql
SELECT d.department_name, 
       d.manager_id, 
       AVG(e.salary) AS avg_salary
FROM Departments AS d
JOIN Employees AS e ON d.department_id = e.department_id
GROUP BY d.department_id
HAVING AVG(e.salary) > 70000;
```

### **Key Notes:**
- Use `HAVING` instead of `WHERE` to filter aggregated results.
- Combine `JOIN`s and `GROUP BY` for advanced aggregations.

---

## **Implementation Tips**

1. **Test Queries Separately:**
   - Write and test each query independently in your script or database interface before integrating into Python.

2. **Iterative Debugging:**
   - Verify intermediate outputs (e.g., after `JOIN` or subquery execution).

3. **Error Handling in Python:**
   - Use `try-except` blocks to handle database connection errors.

### **Example Python Script:**
```python
import sqlite3

# Connect to the database
conn = sqlite3.connect("company.db")
cursor = conn.cursor()

# Aggregation with HAVING
query = """
SELECT d.department_name, 
       d.manager_id, 
       AVG(e.salary) AS avg_salary
FROM Departments AS d
JOIN Employees AS e ON d.department_id = e.department_id
GROUP BY d.department_id
HAVING AVG(e.salary) > 70000;
"""

# Execute and fetch results
cursor.execute(query)
results = cursor.fetchall()
print(results)

conn.close()
```

---

## **Summary**

In this lesson, you’ve learned:
1. How to use subqueries to dynamically fetch values for other queries.
2. How to use complex `JOIN`s to integrate data from multiple tables.
3. How to use aggregation functions to summarize data across groups.
4. How to apply `HAVING` for conditional filtering on aggregated data.

For further exploration, refer to the [SQLite Documentation](https://www.sqlite.org/docs.html) and Python's `sqlite3` library documentation.
```
