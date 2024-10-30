

## Lesson 1: Python Basics

### Variables and Data Types

Python is a dynamically-typed language, meaning you don't need to declare variable types explicitly. Variables are created when you first assign a value to them.

```python
# Variable assignment
x = 5
y = "Hello"
z = 3.14

# Multiple assignment
a, b, c = 1, 2, 3

# Type checking
print(type(x))  # <class 'int'>
print(type(y))  # <class 'str'>
print(type(z))  # <class 'float'>
```

Python also supports complex data types:

- Lists: Ordered, mutable sequences
- Tuples: Ordered, immutable sequences
- Sets: Unordered collections of unique elements
- Dictionaries: Key-value pairs

```python
my_list = [1, 2, 3]
my_tuple = (1, 2, 3)
my_set = {1, 2, 3}
my_dict = {"a": 1, "b": 2, "c": 3}
```

### Operators

Python supports various types of operators:

1. Arithmetic operators:
   ```python
   print(10 + 3)  # Addition: 13
   print(10 - 3)  # Subtraction: 7
   print(10 * 3)  # Multiplication: 30
   print(10 / 3)  # Division: 3.3333...
   print(10 // 3) # Floor division: 3
   print(10 % 3)  # Modulus: 1
   print(10 ** 3) # Exponentiation: 1000
   ```

2. Comparison operators:
   ```python
   print(10 == 3)  # Equal to: False
   print(10 != 3)  # Not equal to: True
   print(10 > 3)   # Greater than: True
   print(10 < 3)   # Less than: False
   print(10 >= 3)  # Greater than or equal to: True
   print(10 <= 3)  # Less than or equal to: False
   ```

3. Logical operators:
   ```python
   x = True
   y = False
   print(x and y)  # Logical AND: False
   print(x or y)   # Logical OR: True
   print(not x)    # Logical NOT: False
   ```

4. Assignment operators:
   ```python
   x = 10
   x += 3  # Equivalent to x = x + 3
   x -= 3  # Equivalent to x = x - 3
   x *= 3  # Equivalent to x = x * 3
   x /= 3  # Equivalent to x = x / 3
   ```

## Control Flow

### Conditional Statements

Conditional statements allow you to execute different code blocks based on certain conditions.

```python
age = 18
if age < 13:
    print("Child")
elif 13 <= age < 20:
    print("Teenager")
else:
    print("Adult")
```

You can also use the ternary operator for simple conditional assignments:

```python
is_adult = True if age >= 18 else False
```

### Loops

#### For Loop

For loops are used to iterate over a sequence (like a list, tuple, or string) or other iterable objects.

```python
# Iterating over a list
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)

# Using range() function
for i in range(5):
    print(i)  # Prints 0, 1, 2, 3, 4

# Enumerate for index and value
for index, fruit in enumerate(fruits):
    print(f"Index {index}: {fruit}")
```

#### While Loop

While loops repeat a block of code as long as a condition is true.

```python
count = 0
while count < 5:
    print(count)
    count += 1

# Using break and continue
while True:
    user_input = input("Enter 'q' to quit: ")
    if user_input.lower() == 'q':
        break
    if user_input.isdigit():
        continue
    print("You entered:", user_input)
```

## Functions

Functions are reusable blocks of code that perform a specific task. They help in organizing code and promoting reusability.

```python
def greet(name, greeting="Hello"):
    """
    This function greets a person with a custom greeting.
    
    Args:
    name (str): The name of the person to greet
    greeting (str): The greeting to use (default is "Hello")
    
    Returns:
    str: The full greeting message
    """
    return f"{greeting}, {name}!"

# Function call
message = greet("Alice")
print(message)  # Output: Hello, Alice!

# Using keyword arguments
message = greet(greeting="Hi", name="Bob")
print(message)  # Output: Hi, Bob!
```

Functions can also have variable-length arguments:

```python
def sum_all(*args):
    return sum(args)

print(sum_all(1, 2, 3, 4))  # Output: 10
```

## Error Handling

Error handling is crucial for writing robust Python programs. The try-except block is used to catch and handle exceptions.

```python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Error: Division by zero!")
except (TypeError, ValueError) as e:
    print(f"Error: {e}")
else:
    print("Operation successful!")
finally:
    print("This always executes")
```

You can also raise your own exceptions:

```python
def validate_age(age):
    if age < 0:
        raise ValueError("Age cannot be negative")
    return age

try:
    validate_age(-5)
except ValueError as e:
    print(f"Validation error: {e}")
```

## Basic Debugging

Debugging is an essential skill for any programmer. Here are some techniques:

1. Using print statements:
   ```python
   def calculate_area(radius):
       print(f"Calculating area for radius: {radius}")  # Debug print
       area = 3.14 * radius ** 2
       print(f"Calculated area: {area}")  # Debug print
       return area
   ```

2. Using the `pdb` module for interactive debugging:
   ```python
   import pdb

   def complex_function(x, y):
       result = x + y
       pdb.set_trace()  # Breakpoint
       return result * 2

   complex_function(3, 4)
   ```

3. Using logging instead of print statements:
   ```python
   import logging

   logging.basicConfig(level=logging.DEBUG)

   def divide(x, y):
       logging.debug(f"Dividing {x} by {y}")
       try:
           result = x / y
       except ZeroDivisionError:
           logging.error("Division by zero!")
           raise
       return result

   divide(10, 2)
   ```

4. Using assertions for sanity checks:
   ```python
   def calculate_average(numbers):
       assert len(numbers) > 0, "List is empty"
       return sum(numbers) / len(numbers)

   calculate_average([])  # Raises AssertionError
   ```


