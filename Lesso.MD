Certainly! I'll modify the assignment to use a different example for the if statement. Here's the updated markdown with a new scenario for Task 2:

```markdown
# Python Basics Assignment

## Objective
Apply fundamental Python programming concepts, including variables, data types, operators, control flow, functions, and basic error handling.

## Task 1: Variables and Data Types

Create a Python script that:

1. Defines variables for a city name (string), its population (integer), and its area in square kilometers (float).
2. Prints each variable on a separate line.
3. Creates a list of three famous landmarks in the city.
4. Prints the list of landmarks.

Example (do not use this exact code in your solution):

```python
city = "Paris"
population = 2161000
area = 105.4

print("City:", city)
print("Population:", population)
print("Area (sq km):", area)

landmarks = ["Eiffel Tower", "Louvre Museum", "Notre-Dame Cathedral"]
print("Famous landmarks:", landmarks)
```

## Task 2: Operators and Control Flow

Write a program that:

1. Asks the user to input a temperature in Celsius.
2. Converts the temperature to Fahrenheit and prints the result.
3. Uses an if-elif-else statement to categorize the temperature (freezing, cold, moderate, warm, or hot).
4. Uses a for loop to print a weather-related message as many times as the Celsius temperature.

Example (do not use this exact code in your solution):

```python
celsius = float(input("Enter temperature in Celsius: "))
fahrenheit = (celsius * 9/5) + 32
print(f"{celsius}°C is equal to {fahrenheit}°F")

if celsius < 0:
    print("It's freezing!")
elif celsius < 10:
    print("It's cold")
elif celsius < 20:
    print("It's moderate")
elif celsius < 30:
    print("It's warm")
else:
    print("It's hot!")

for _ in range(int(celsius)):
    print("Check the weather forecast!")
```

## Task 3: Functions

Create two functions:

1. A function called `calculate_bmi(weight, height)` that takes weight (in kg) and height (in meters) and returns the Body Mass Index (BMI).
2. A function called `is_palindrome(word)` that takes a word as input and returns True if the word is a palindrome, and False if it's not.
3. Call both functions with example inputs and print the results.

Example (do not use this exact code in your solution):

```python
def calculate_bmi(weight, height):
    bmi = weight / (height ** 2)
    return round(bmi, 1)

def is_palindrome(word):
    return word.lower() == word.lower()[::-1]

# Test the functions
print(calculate_bmi(70, 1.75))
print(is_palindrome("racecar"))
```

## Task 4: Simple Error Handling

Modify your program from Task 2 to:

1. Use a try-except block to handle the case where the user enters non-numeric input for the temperature.
2. Print an error message if the input is invalid.

Example (do not use this exact code in your solution):

```python
try:
    celsius = float(input("Enter temperature in Celsius: "))
    # Your code for temperature conversion and conditionals here
except ValueError:
    print("Error: Please enter a valid number for temperature")
```

## Task 5: Basic Debugging

Add print statements throughout your code to help debug:

1. Print the values of variables after they are assigned or modified.
2. Print messages at the beginning and end of each function to show when they are called and when they finish.

Example (do not use this exact code in your solution):

```python
def calculate_area(length, width):
    print(f"Calculating area for length={length} and width={width}")  # Debug
    area = length * width
    print(f"Calculated area: {area}")  # Debug
    return area

# Additional debugging
print("Input values:")
print(f"Length: {length}, Width: {width}")
```

## Submission Guidelines
- Submit your Python script (.py file) containing solutions to all tasks.
- Ensure your code is well-commented and follows Python naming conventions.
- Test your code thoroughly before submission.
- Do not use the exact examples provided in the assignment. Create your own unique solutions.

Good luck, and enjoy coding!
```

In this updated version, Task 2 now uses a temperature conversion scenario instead of age and current year. This provides a different context for using if-elif-else statements and loops, while still covering the same programming concepts.
