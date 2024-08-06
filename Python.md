## Summary of "Python Crash Course, 3rd Edition" by Eric Matthes (Chapters 3-11)

---

### Chapter 3: Introducing Lists

#### Key Concepts
- **List Definition:** Collection of items in a specific order.
  - Syntax: `bicycles = ['trek', 'cannondale', 'redline', 'specialized']`
  
- **Accessing Elements:** Lists are zero-indexed.
  - Example: `print(bicycles[0])` outputs `trek`

#### Code Snippets
```python
# Accessing elements
print(bicycles[0])  # Output: trek

# Modifying elements
bicycles[0] = 'giant'

# Adding elements
bicycles.append('giant')
bicycles.insert(0, 'giant')

# Removing elements
del bicycles[0]
popped_bicycle = bicycles.pop()
bicycles.remove('trek')
```

#### Annotations
- Use `append` to add to the end, `insert` to add at a specific position.
- `pop()` removes the last item, `del` removes by index, and `remove` removes by value.

#### Important Notes
- **Avoiding Index Errors:** Ensure indices are within range to prevent `IndexError`.

---

### Chapter 4: Working with Lists

#### Key Concepts
- **Looping Through Lists:** Use `for` loop.
  - Example: 
    ```python
    for bicycle in bicycles:
        print(bicycle)
    ```
  
- **Numerical Lists:** Generate with `range()`.
  - Example: `numbers = list(range(1, 6))`

#### Code Snippets
```python
# Looping through a list
for bicycle in bicycles:
    print(bicycle)

# List comprehension
squares = [value**2 for value in range(1, 11)]

# Slicing lists
print(bicycles[0:3])

# Copying lists
new_bicycles = bicycles[:]
```

#### Annotations
- List comprehensions are a concise way to generate lists.
- Slicing creates sublists, and using `[:]` creates a copy.

---

### Chapter 5: if Statements

#### Key Concepts
- **Conditional Tests:** Equality (`==`), Inequality (`!=`), Comparisons (`<`, `>`, `<=`, `>=`).
- **if-elif-else Statements:** For multiple conditions.
- **Boolean Expressions:** True/False values.

#### Code Snippets
```python
# Conditional tests
if bicycle == 'trek':
    print("It's a Trek!")

# if-elif-else statement
if age < 4:
    print("You are a baby.")
elif age < 13:
    print("You are a kid.")
else:
    print("You are an adult.")
```

#### Annotations
- Use `and`/`or` to combine conditions.
- `in` and `not in` to check membership in a list.

---

### Chapter 6: Dictionaries

#### Key Concepts
- **Dictionary Definition:** Key-value pairs.
  - Syntax: `alien = {'color': 'green', 'points': 5}`
  
- **Accessing and Modifying:** Use keys.
  - Example: `alien['color']`

#### Code Snippets
```python
# Accessing dictionary values
print(alien['color'])  # Output: green

# Modifying dictionary values
alien['color'] = 'yellow'

# Looping through a dictionary
for key, value in alien.items():
    print(f"{key}: {value}")
```

#### Annotations
- Use `del` to remove key-value pairs.
- Nest dictionaries within lists, lists within dictionaries for complex data structures.

---

### Chapter 7: User Input and while Loops

#### Key Concepts
- **User Input:** `input()` function.
  - Example:
    ```python
    message = input("Tell me something: ")
    print(message)
    ```
  
- **while Loops:** Repeat as long as a condition is true.
  - Example:
    ```python
    current_number = 1
    while current_number <= 5:
        print(current_number)
        current_number += 1
    ```

#### Code Snippets
```python
# User input
name = input("What is your name? ")
print(f"Hello, {name}!")

# while loop
current_number = 1
while current_number <= 5:
    print(current_number)
    current_number += 1
```

#### Annotations
- Use `while` for unknown iteration counts, `for` for known counts.
- Use `input()` for interactive programs.

---

### Chapter 8: Functions

#### Key Concepts
- **Defining Functions:** Reusable blocks of code.
  - Example:
    ```python
    def greet_user():
        print("Hello!")
    ```

- **Arguments and Return Values:**
  - Example:
    ```python
    def get_formatted_name(first_name, last_name):
        return f"{first_name} {last_name}"
    ```

#### Code Snippets
```python
# Function definition
def greet_user():
    print("Hello!")

# Function with arguments
def greet_user(username):
    print(f"Hello, {username}!")

# Function with return value
def get_formatted_name(first_name, last_name):
    return f"{first_name} {last_name}"
```

#### Annotations
- Define functions with `def`.
- Use `return` to send back a result from a function.

---

### Chapter 9: Classes

#### Key Concepts
- **Class Definition:** Blueprint for creating objects.
  - Example:
    ```python
    class Dog:
        def __init__(self, name, age):
            self.name = name
            self.age = age
        def sit(self):
            print(f"{self.name} is now sitting.")
    ```

- **Instances and Inheritance:**
  - Example:
    ```python
    class SARDog(Dog):
        def __init__(self, name, age):
            super().__init__(name, age)
    ```

#### Code Snippets
```python
# Class definition
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def sit(self):
        print(f"{self.name} is now sitting.")

# Creating an instance
my_dog = Dog('Willie', 6)
my_dog.sit()  # Output: Willie is now sitting.

# Inheritance
class SARDog(Dog):
    def __init__(self, name, age):
        super().__init__(name, age)
```

#### Annotations
- Use classes to model real-world objects.
- Inheritance allows for code reuse and extension.

---

### Chapter 10: Files and Exceptions

#### Key Concepts
- **File Operations:** Reading and writing files.
  - Example:
    ```python
    with open('pi_digits.txt') as file_object:
        contents = file_object.read()
        print(contents)
    ```

- **Exception Handling:**
  - Example:
    ```python
    try:
        print(5/0)
    except ZeroDivisionError:
        print("You can't divide by zero!")
    ```

#### Code Snippets
```python
# Reading from a file
with open('pi_digits.txt') as file_object:
    contents = file_object.read()
    print(contents)

# Writing to a file
with open('programming.txt', 'w') as file_object:
    file_object.write("I love programming.")

# Handling exceptions
try:
    print(5/0)
except ZeroDivisionError:
    print("You can't divide by zero!")

# Using json for data storage
import json

numbers = [2, 3, 5, 7, 11]
with open('numbers.json', 'w') as f:
    json.dump(numbers, f)
```

#### Annotations
- Use `with open()` for file operations to ensure proper resource management.
- Handle exceptions gracefully to prevent program crashes.

---

### Chapter 11: Testing Your Code

#### Key Concepts
- **Automated Testing:** Ensures code correctness.
  - Example:
    ```python
    def get_formatted_name(first, last):
        return f"{first} {last}"

    def test_get_formatted_name():
        formatted_name = get_formatted_name('janis', 'joplin')
        assert formatted_name == 'Janis Joplin'
    ```

#### Code Snippets
```python
# Simple function for testing
def get_formatted_name(first, last):
    return f"{first} {last}"

# Test function
def test_get_formatted_name():
    formatted_name = get_formatted_name('janis', 'joplin')
    assert formatted_name == 'Janis Joplin'

# Running tests with pytest
# In the command line:
# $ pytest test_names.py
```

#### Annotations
- Use `assert` statements to validate function output.
- Regularly run tests to catch and fix issues early.

---